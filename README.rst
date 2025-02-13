.. Github doesn't render images unless absolute URL
.. Do not know of a conditional tag, "only: github" nor "github display" works

.. image:: https://img.shields.io/badge/License-LGPL%20v3-blue.svg
    :target: https://www.gnu.org/licenses/lgpl-3.0]
.. image:: https://img.shields.io/badge/License-Artistic%202.0-0298c3.svg
    :target: https://opensource.org/licenses/Artistic-2.0
.. image:: https://repology.org/badge/tiny-repos/verilator.svg?header=distro%20packages
    :target: https://repology.org/project/verilator/versions
.. image:: https://api.codacy.com/project/badge/Grade/fa78caa433c84a4ab9049c43e9debc6f
    :target: https://www.codacy.com/gh/verilator/verilator
.. image:: https://codecov.io/gh/verilator/verilator/branch/master/graph/badge.svg
    :target: https://codecov.io/gh/verilator/verilator
.. image:: https://github.com/verilator/verilator/workflows/build/badge.svg
    :target: https://github.com/verilator/verilator/actions?query=workflow%3Abuild


Welcome to Verilator
====================

----------

**⚠ Deprecated**: this fork from Verilator would not be updated anymore as version v5.006 fixed the VPI callback `VPI: simulation time callbacks should be one-time #2778 <https://github.com/verilator/verilator/issues/2778#issuecomment-886149648>`_

----------

----------

**⚠ Verilator fork that with VPI callbacks patch required for CoCoTB simulations** `VPI: simulation time callbacks should be one-time #2778 <https://github.com/verilator/verilator/issues/2778#issuecomment-886149648>`_

- patch at `branch: v5.002-vpi-callback-patch <https://github.com/Eideticom/verilator/tree/v5.002-vpi-callback-patch>`_ (:code:`git checkout v5.002-vpi-callback-patch`)
- cocotb_ver="1.7.1"
- cocotb_bus_ver="v0.1.0" (if using `alexforencich/cocotbext-axi <https://github.com/alexforencich/cocotbext-axi>`_, `Simulation gets stuck with SIM=verilator 4.106 #35 <https://github.com/alexforencich/cocotbext-axi/issues/35>`_)

----------

.. list-table::

   * - **Welcome to Verilator, the fastest Verilog/SystemVerilog simulator.**
        * Accepts Verilog or SystemVerilog
        * Performs lint code-quality checks
        * Compiles into multithreaded C++, or SystemC
        * Creates XML to front-end your own tools
     - |Logo|
   * - |verilator multithreaded performance|
     - **Fast**
        * Outperforms many closed-source commercial simulators
        * Single- and multi-threaded output models
   * - **Widely Used**
        * Wide industry and academic deployment
        * Out-of-the-box support from Arm, and RISC-V vendor IP
     - |verilator usage|
   * - |verilator community|
     - **Community Driven & Openly Licensed**
        * Guided by the `CHIPS Alliance`_ and `Linux Foundation`_
        * Open, and free as in both speech and beer
        * More simulation for your verification budget
   * - **Commercial Support Available**
        * Commercial support contracts
        * Design support contracts
        * Enhancement contracts
     - |verilator support|


What Verilator Does
===================

Verilator is invoked with parameters similar to GCC or Synopsys's VCS.  It
"Verilates" the specified Verilog or SystemVerilog code by reading it,
performing lint checks, and optionally inserting assertion checks and
coverage-analysis points. It outputs single- or multi-threaded .cpp and .h
files, the "Verilated" code.

These Verilated C++/SystemC files are then compiled by a C++ compiler
(gcc/clang/MSVC++), optionally along with a user's own C++/SystemC wrapper
file to instantiate the Verilated model. Executing the resulting executable
performs the design simulation. Verilator also supports linking Verilated
generated libraries, optionally encrypted, into other simulators.

Verilator may not be the best choice if you are expecting a full featured
replacement for a closed-source Verilog simulator, need SDF annotation,
mixed-signal simulation, or are doing a quick class project (we recommend
`Icarus Verilog`_ for classwork.)  However, if you are looking for a path
to migrate SystemVerilog to C++/SystemC, or want high speed simulation of
synthesizable designs containing limited verification constructs, Verilator
is the tool for you.


Performance
===========

Verilator does not directly translate Verilog HDL to C++ or SystemC. Rather,
Verilator compiles your code into a much faster optimized and optionally
thread-partitioned model, which is in turn wrapped inside a C++/SystemC
module. The results are a compiled Verilog model that executes even on a
single-thread over 10x faster than standalone SystemC, and on a single
thread is about 100 times faster than interpreted Verilog simulators such
as `Icarus Verilog`_. Another 2-10x speedup might be gained from
multithreading (yielding 200-1000x total over interpreted simulators).

Verilator has typically similar or better performance versus the
closed-source Verilog simulators (Carbon Design Systems Carbonator,
Modelsim/Questa, Cadence Incisive/NC-Verilog, Synopsys VCS, VTOC, and
Pragmatic CVer/CVC). But, Verilator is open-sourced, so you can spend on
computes rather than licenses. Thus Verilator gives you the best
cycles/dollar.


Installation & Documentation
============================

For more information:

- `Verilator installation and package directory structure
  <https://verilator.org/install>`_

- `Verilator manual (HTML) <https://verilator.org/verilator_doc.html>`_,
  or `Verilator manual (PDF) <https://verilator.org/verilator_doc.pdf>`_

- `Subscribe to verilator announcements
  <https://github.com/verilator/verilator-announce>`_

- `Verilator forum <https://verilator.org/forum>`_

- `Verilator issues <https://verilator.org/issues>`_


Support
=======

Verilator is a community project, guided by the `CHIPS Alliance`_ under the
`Linux Foundation`_.

We appreciate and welcome your contributions in whatever form; please see
`Contributing to Verilator
<https://github.com/verilator/verilator/blob/master/docs/CONTRIBUTING.rst>`_.
Thanks to our `Contributors and Sponsors
<https://verilator.org/guide/latest/contributors.html>`_.

Verilator also supports and encourages commercial support models and
organizations; please see `Verilator Commercial Support
<https://verilator.org/verilator_commercial_support>`_.


Related Projects
================

- `GTKwave <http://gtkwave.sourceforge.net/>`_ - Waveform viewer for
  Verilator traces.

- `Icarus Verilog`_ - Icarus is a full featured interpreted Verilog
  simulator. If Verilator does not support your needs, perhaps Icarus may.


Open License
============

Verilator is Copyright 2003-2022 by Wilson Snyder. (Report bugs to
`Verilator Issues <https://verilator.org/issues>`_.)

Verilator is free software; you can redistribute it and/or modify it under
the terms of either the GNU Lesser General Public License Version 3 or the
Perl Artistic License Version 2.0. See the documentation for more details.

.. _CHIPS Alliance: https://chipsalliance.org
.. _Icarus Verilog: http://iverilog.icarus.com
.. _Linux Foundation: https://www.linuxfoundation.org
.. |Logo| image:: https://www.veripool.org/img/verilator_256_200_min.png
.. |verilator multithreaded performance| image:: https://www.veripool.org/img/verilator_multithreaded_performance_bg-min.png
.. |verilator usage| image:: https://www.veripool.org/img/verilator_usage_400x200-min.png
.. |verilator community| image:: https://www.veripool.org/img/verilator_community_400x125-min.png
.. |verilator support| image:: https://www.veripool.org/img/verilator_support_400x125-min.png

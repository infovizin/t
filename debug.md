![](synopsys_color.gif)

VC VIP USB SystemVerilog/UVM QuickStart
=======================================

Debug
-----

------------------------------------------------------------------------

**[Basic Example](index_basic.html)**: [Basic Example
Architecture](architecture.html) \| [Interfaces](interfaces.html) \|
[Instantiate VIP](instantiate.html) \| [Configure VIP](configure.html)
\| [Sequences](sequences.html) \|
[[Objections](objections.html)]{.style1} \|[ [Tests](tests.html) \|
[Start and End Simulation](simulation.html) ]{.style1}\| Debug \|
[Additional Examples](additional_egs.html) \| [Advanced
Topics](advanced.html)

**[Intermediate
Example](../../../tb_usb_svt_uvm_intermediate_sys/doc/tb_usb_svt_uvm_intermediate_sys/index_intermediate.html)**

------------------------------------------------------------------------

This section describes the following debug features supported by VIP:

Protocol Analyzer
-----------------

USB VIP supports the Verdi Protocol Analyzer. The Protocol Analyzer is
an interactive graphical application which provides the
protocol-oriented analysis and debugging capabilities.

Using Native Protocol Analyzer for Debugging
--------------------------------------------

This feature enables you to invoke Protocol Analyzer from Verdi GUI. You
can synchronize the Verdi wave window, smart log and the source code
with the Protocol Analyzer transaction view. Protocol Analyzer can be
enabled in an interactive and post-processing mode. The new features
available in Native Protocol Analyzer includes layer based grouping of
the transactions, Quick filter, Call stack, horizontal zoom, and reverse
debug with the interactive support.

### Prerequisites

Protocol Analyzer uses transaction-level dump database. You can use the
following settings to dump the transaction database:

#### Compile Time Options:

-   `-lca  `
-   `-kdb // dumps the work.lib++ data for source coding view  `
-   `+define+SVT_FSDB_ENABLE // enables FSDB dumping  `
-   `-debug_access  `

For more information on how to set the FSDB dumping libraries, see
Appendix B section in Linking Novas Files with Simulators and Enabling
FSDB Dumping guide available at: `$VERDI_HOME/doc/linking_dumping.pdf`.

You can dump the transaction database either by setting the
`pa_format_type` configuration variable or by passing the following
runtime switch:

#### Configuration Variable Setting:

Set `enable_frame_line_pa_xml_gen` a parameter of USB configuration
class: `svt_usb_configuration` to enable generation of PA files.

For example,

`src_cfg.enable_frame_line_pa_xml_gen = 1;  `

`sink_cfg.enable_frame_line_pa_xml_gen =1;`

Runtime Switch:

`+svt_enable_pa=fsdb  `

Enables FSDB output of transaction and memory information for display in
Verdi.

### Invoking Protocol Analyzer

Perform the following steps to invoke Protocol Analyzer in interactive
or post-processing mode:

1.  Post-processing mode
    a.  Load the transaction dump data and issue the following command
        to invoke the GUI:\
        `verdi -ssf        -lib work.lib++`
    b.  In Verdi, navigate to Tools \> Transaction Debug \> Transaction
        and Protocol Analyzer.
2.  Interactive Mode
    a.  Issue the following command to invoke Protocol Analyzer in an
        interactive mode:\
        `<sim>  -gui=verdi    `

    **Note:** Protocol Analyzer can be invoked using the Verdi. The
    Protocol Analyzer transaction view gets updated during the
    simulation.

### Documentation

The documentation for Protocol Analyzer is available at:
`$VERDI_HOME/doc/Verdi_Transaction_and_Protocol_Debug.pdf`.

### Messages

USB VIP issues UVM Fatal, Error, Warning and Info messages.

### Protocol Checks

USB VIP supports protocol checks. The protocol checks help you to
validate the protocol correctness of the DUT, and help to debug the DUT
errors. By default, the protocol checks are enabled. For more
information on Protocol Checks, see the [VC VIP USB UVM Class
Reference.](../../../../../doc/usb_svt_uvm_class_reference/html/index.html)

------------------------------------------------------------------------

[[Examples Home](index_basic.html) \|
[SolvNet](https://solvnet.synopsys.com) \|
[Support](https://solvnet.synopsys.com/EnterACall) \| [Running
Examples](running_egs.html) \|
[Accellera](http://www.accellera.org/)]{style="background-color: rgb(255, 255, 255);"}

------------------------------------------------------------------------

┬⌐ 2018 Synopsys, Inc. All Rights Reserved.

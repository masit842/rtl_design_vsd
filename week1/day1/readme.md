Synthesizer

Tool used for converting RTL (Register Transfer Level) to Netlist.

Yosys is the synthesizer used in this course.

Basic Flow
read_verilog (Design) 
       ↓
       Yosys  ----->  Netlist File -----> write_verilog
       ↑
read_liberty (.lib)

Verification of Synthesis

Netlist + Testbench → Simulated with iverilog → VCD file → viewed in gtkwave.

Output should match RTL simulation output.

Primary Inputs/Outputs remain same between RTL and synthesized netlist → same testbench can be reused.

RTL Design

Behavioral representation of the required specification.

Example (pseudo-code):

module sample_code (
    input clk, rst,
    output result, done
);

always @(posedge clk, posedge rst)
    if (rst)
        // reset behavior
    else
        // functional behavior
endmodule

Synthesis

RTL → Gate-level translation.

Converts design into gates + connections.

Output is a Netlist file.

.lib (Library File)

Collection of logical modules (standard cells).

Includes:

Basic gates (AND, OR, NOT, etc.).

Multiple “flavors” of the same gate (slow, medium, fast).

Example:

2-input AND: slow / medium / fast

3-input AND: slow / medium / fast

Why Different Flavors of Gates?

Combinational delay in logic path determines max speed of operation.

Need both fast and slow cells:

Fast cells → meet performance (reduce delay).

Slow cells → avoid hold time violations.

Timing Equation
Tclk > Tcq_a + Tcombi + Tsetup_b

Faster vs Slower Cells

Load in circuits = Capacitance.

Faster charging/discharging = lower delay.

Faster cells:

Wide transistors → more current → low delay.

Cost: higher area + power.

Slower cells:

Narrow transistors → higher delay.

Benefit: less area + less power.

Trade-off: Faster cells improve speed but increase area/power; slower cells save area/power but may miss timing.

Selection of Cells

Synthesizer needs constraints to choose the optimal mix of cells.

Too many fast cells:

Bad circuit (high area/power).

Hold time violations.

Too many slow cells:

Circuit too sluggish, performance unmet.

Correct guidance via constraints balances speed, area, and power.

Illustration

RTL → Synthesizer (Yosys) → Netlist guided by .lib + constraints.

Netlist is verified with the same testbench using simulation tools.

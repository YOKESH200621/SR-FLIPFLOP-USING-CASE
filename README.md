## EXP NO:6

# SR-FLIPFLOP-USING-CASE
# Name: YOKESH I
# Reg no: 212224230313

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

1 Open Quartus software and create a new project.
2 Create a new VHDL file and write the code for the SR Flip Flop.
3 Compile the design by clicking on "Processing" -> "Start Compilation".
4 Create a testbench file to simulate the design.
5 Write the testbench code and add stimulus to test the SR Flip Flop.
6 Run the simulation by clicking on "Processing" -> "Start Simulation".
7 Observe the waveforms and verify the SR Flip Flop behavior.
8 Analyze the results and make any necessary changes to the design.

**PROGRAM**

```
module  ex6(s, r, clk, rst, q);
  input s, r, clk, rst;
  output reg q;

  always @(posedge clk or posedge rst)
begin
    if (rst)
    q <= 0; // Reset the flip-flop
    else
begin
      case ({s, r}) // S and R control the behavior
        2'b00: q <= q; // No change
        2'b01: q <= 0; // Reset
        2'b10: q <= 1; // Set
        2'b11: q <= 0; // Invalid state, typically treated as reset
      endcase
     end
  end
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**

![Screenshot 2025-05-07 151857](https://github.com/user-attachments/assets/69a53083-c203-4697-bc4e-04b2f40a1634)

**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot 2025-05-07 151909](https://github.com/user-attachments/assets/1b22e252-0235-468b-a85f-1103a87d5631)

**RESULTS**
Thus the SR flipflop using verilog and validating their functionality using their functional tables is implemented successfully.

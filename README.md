# D-FLIPDLOP-NEGEDGE

**AIM:**

To implement  D flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**D Flip-Flop**

D flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, D latch operates with enable signal. That means, the output of D flip-flop is insensitive to the changes in the input, D except for active transition of the clock signal. The circuit diagram of D flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/D-FLIPDLOP-NEGEDGE/assets/154305477/48c81fe8-bc3f-40e7-95e2-519fc155ad51)

This circuit has single input D and two outputs Qtt & Qtt’. The operation of D flip-flop is similar to D Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of D flip-flop.

![image](https://github.com/naavaneetha/D-FLIPDLOP-NEGEDGE/assets/154305477/e5f3fda7-68ec-4a3a-a0a4-cf6f9cc4ab55)

Therefore, D flip-flop always Hold the information, which is available on data input, D of earlier positive transition of clock signal. From the above state table, we can directly write the next state equation as Qt+1t+1 = D

![image](https://github.com/naavaneetha/D-FLIPDLOP-NEGEDGE/assets/154305477/8592c0d8-2917-4142-91b9-d6c30dd891d2)

Next state of D flip-flop is always equal to data input, D for every positive transition of the clock signal. Hence, D flip-flops can be used in registers, shift registers and some of the counters.

**Procedure**

/* write all the steps invloved */

**PROGRAM**
~~~
module sr_ff (s, r, clk, rst, q);
  input s, r, clk, rst;
  output reg q;

  always @(posedge clk or posedge rst)
 begin
    if (rst)
      q <= 0; // Reset the flip-flop
    else
 begin
      case ({s, r}) // S and R control the behavior
        2'b00: q <= q;    // No change
        2'b01: q <= 0;    // Reset
        2'b10: q <= 1;    // Set
        2'b11: q <= 0;    // Invalid state, typically treated as reset
      endcase
    end
  end
endmodule
/* Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by:prabanjan r
RegisterNumber:24900174
*/


**RTL LOGIC FOR FLIPFLOPS**
![392857581-b4b49a69-d2db-4b32-9126-b61c028d88db](https://github.com/user-attachments/assets/75925221-8ded-4877-ab6e-899b948bccf6)


**TIMING DIGRAMS FOR FLIP FLOPS**
![392857753-de6d9e0d-cf49-4f9e-9ded-5216dbef5609](https://github.com/user-attachments/assets/958c56bd-d71e-458c-bc4e-7222b8a1f951)


**RESULTS**
Program for SR flipflop was verified in quartus using Verilog programming.

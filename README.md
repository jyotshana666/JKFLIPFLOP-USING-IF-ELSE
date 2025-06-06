# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1 . Design the JK flip-flop module in Verilog with inputs J, K, clk, and outputs Q, Qbar.

2 . Use always @(posedge clk) to define flip-flop behavior based on JK input combinations.

3 . Create a testbench to apply all possible input combinations (J, K) with clock pulses.

4 . Simulate the design and observe the outputs (Q, Qbar) for each input case.

5 . Compare output behavior with the JK flip-flop truth table to validate correctness.1 . 

**PROGRAM**
```
module jk(j, k, clk, rst, q);
input j, k, clk, rst;
output reg q;
always @(posedge clk or posedge rst) begin
if (rst)
    q <= 0; // Reset the flip-flop
else if (j == 0 && k == 0)
    q <= q; // No change
else if (j == 0 && k == 1)
	 q <= 0; // Reset
else if (j == 1 && k == 0)
    q <= 1; // Set
else if (j == 1 && k == 1)
    q <= ~q; // Toggle
end 
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**

![Screenshot 2025-05-05 213119](https://github.com/user-attachments/assets/ecb97b8b-119f-484a-acb9-3ff6cd5fe69c)


**TIMING DIGRAMS FOR FLIP FLOPS**

![Screenshot 2025-05-05 213406](https://github.com/user-attachments/assets/006b1972-d03d-4d7b-8167-9ffc36a7b9f8)


**RESULTS**

The JK flip-flop was successfully implemented and verified in Verilog, with output behavior matching its functional truth table.

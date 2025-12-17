# SYNCHRONOUS-UP & DOWN-COUNTER
# Developed By: NAVEENKUMAR V
# Ref.No: 25016071
## AIM:
To implement 4 bit synchronous up and down counter and validate functionality.

## SOFTWARE REQUIRED:

Quartus prime

## THEORY:

### 4 bit synchronous UP Counter:

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

### 4 bit synchronous DOWN Counter:

In a 4-bit synchronous DOWN counter using J-K flip-flops, all flip-flops share the same clock, so they change state at the same time, eliminating ripple delay. The least significant flip-flop (Q0) toggles on every clock pulse. Each higher-order flip-flop toggles only when all preceding (lower-order) outputs are LOW (0). This is done by setting J = K = 1 for a flip-flop only when the required lower bits are 0. Because all flip-flops are clocked simultaneously and the toggle conditions are properly controlled, the counter counts downward in the correct sequence without ripple effect.

![syn down-2](https://github.com/user-attachments/assets/7ef19add-9eb1-4cbd-8ff7-a7d13fed0dc7)


![syn down-2 2](https://github.com/user-attachments/assets/213b0f0a-42b5-4e72-b39d-139a67e3c882)


A 4-bit synchronous down counter is a digital circuit that reduces its output value by one on every clock pulse. Based on the logic in the diagram, here are the key points to understand how it works: Synchronous Operation: Unlike ripple counters, all four flip-flops (DFF0–DFF3) are connected to the same common clock signal (clk). This ensures that all bits change state at exactly the same time, preventing timing glitches. The Decrement Logic: To count "down," the circuit uses the inverted outputs (usually labeled \bar{Q}) or specific logic gates (AND/XOR) to determine when the next bit should toggle. A bit toggles only when all the preceding bits (to its right) are 0. Example: To go from 1000 (8) to 0111 (7), the three lower bits must all flip because they were all zeros. Active-Low Reset (rstn): The "bubble" on the reset pin indicates it is active-low. When this signal drops to 0, the counter immediately forces the output to a starting state (usually 1111 or 15 in a down counter). Counting Range: Since it is a 4-bit counter, it has 2^4 = 16 possible states. It counts from 15 down to 0 (1111 \rightarrow 0000) and then "rolls over" back to 15 to start again. Output Bus: The output is shown as a single line with a diagonal slash and the number 4, signifying it is a 4-bit wide bus containing the values of all four flip-flops.

## Procedure:
1.   Open Quartus Prime and create a new project for the synchronous counter design.

2.   Write the Verilog HDL code for the 4-bit synchronous UP counter and DOWN counter using a common clock and reset.
   
3.   Compile the program and check for syntax errors and successful compilation.

4.   Generate and verify the RTL schematic to confirm correct counter logic implementation.

5.   Run the functional simulation, observe the timing diagrams, and verify correct up and down counting operation.

## PROGRAM:
### UP-COUNTER
```
module up(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

### DOWN-COUNTER
```
module down(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule
```


## RTL LOGIC UP COUNTER:
### UP-COUNTER
<img width="1920" height="1080" alt="DE Ex6-syn count-up-1" src="https://github.com/user-attachments/assets/86bacf28-b7f5-4c2c-bf22-c6e6475b2a75" />

### DOWN-COUNTER
<img width="1920" height="1080" alt="DE EX-6 syn count-down-1" src="https://github.com/user-attachments/assets/88179a62-bdd5-4a5f-be2d-9c2911c77241" />

## TIMING DIAGRAM FOR IP COUNTER:
### UP-COUNTER
<img width="1920" height="1080" alt="DE Ex-6-Syn count-up-2" src="https://github.com/user-attachments/assets/a0fb909a-7217-4396-9c86-f3a3e0ed9291" />

### DOWN-COUNTER
<img width="1920" height="1080" alt="DE EX-6 syn count-down-2" src="https://github.com/user-attachments/assets/079f762a-844a-462c-9e64-649281a773d0" />

## TRUTH TABLE:
<img width="1339" height="654" alt="Ex6-syn count-TT" src="https://github.com/user-attachments/assets/65b4ee52-9253-4771-949a-83003ad55d7a" />

## RESULTS:
Thus the implementation of 4 bit synchronous up counter and down counter and the validate functionality is successful.

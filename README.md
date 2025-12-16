# SYNCHRONOUS-UP-COUNTER
# Developed By: NAVEENKUMAR V
# Ref.No: 25016071
## AIM:
To implement 4 bit synchronous up counter and validate functionality.

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

## Procedure:

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

```


## RTL LOGIC UP COUNTER:
### UP-COUNTER
<img width="1920" height="1080" alt="DE Ex6-syn count-up-1" src="https://github.com/user-attachments/assets/86bacf28-b7f5-4c2c-bf22-c6e6475b2a75" />

## TIMING DIAGRAM FOR IP COUNTER:
### UP-COUNTER
<img width="1920" height="1080" alt="DE Ex-6-Syn count-up-2" src="https://github.com/user-attachments/assets/a0fb909a-7217-4396-9c86-f3a3e0ed9291" />

## TRUTH TABLE:
<img width="1339" height="654" alt="Ex6-syn count-TT" src="https://github.com/user-attachments/assets/65b4ee52-9253-4771-949a-83003ad55d7a" />

## RESULTS:
Thus the implementation of 4 bit synchronous up counter and down counter and the validate functionality is successful.

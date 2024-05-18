# MOORE_1011
# AIM
To stimulate and synthesis MOORE Sequence Detector for 1011 using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
# State Diagram
![image](https://github.com/RESMIRNAIR/MOORE_1011/assets/154305926/4c056127-254f-4b9a-88d1-5486b2577ba3)
# PROGRAM
```
module sd1011_moore(input bit clk,input logic reset,input logic din,output logic dout);
typedef enum logic [2:0] {S0, S1, S2, S3, S4} state_t;
state_t state;
always @(posedge clk or posedge reset) begin
if(reset) begin
dout <= 1'b0;
state <= S0;
end
else begin
case(state)
S0: begin
dout <=1'b0;
if(din)
state <= S1;
end
S1: begin
dout <= 1'b0;
if(~din)
state <= S2;
end
S2: begin
dout <= 1'b0;
if(din)
state <= S3;
else
state <= S0;
end
S3: begin
dout <= 1'b0;
if(din)
state <= S4;
else
state <= S2;
end
S4: begin
dout <= 1'b1;
if(din)
state <= S1;
else
state <= S0;
end
endcase
end
end
endmodule
```
# OUTPUT
![image](https://github.com/RESMIRNAIR/MOORE_1011/assets/160302888/8fb982f1-abd9-4b8f-a2e8-f7205ef8d1cc)
# RESULT
Thus the verilog program for MOORE Sequence Detector for 1011 has been simulated and verified successfully.

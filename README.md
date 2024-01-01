## Experiment-05 Implementation of flipflops using verilog
## NAME: Tanessha
 ## REGISTER NUMBER:23006086
## AIM: To implement all the flipflops using verilog and validating their functionality using their functional tables
## HARDWARE REQUIRED: – PC, Cyclone II , USB flasher SOFTWARE REQUIRED: Quartus prime
### THEORY:
## Procedure
1.Create a New Project:

Open Quartus and create a new project by selecting "File" > "New Project Wizard."
Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).
2.Create a New Design File:

Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
3.Write the Combinational Logic Code:

Open the newly created Verilog or VHDL file and write the code for your combinational logic.
4.Compile the Project:
To compile the project, click on "Processing" > "Start Compilation" in the menu.
Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.
5.Analyze and Fix Errors:

If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
Review and fix any issues in your code if necessary. View the RTL diagram.
6.Verification:

Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".

Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
## SR Flip-Flop
SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.
## PROGRAM:
module flipflops(S,R,clk,Q,Qbar);

input S,R,clk;

output reg Q;

output reg Qbar;

initial Q=0;

initial Qbar=1;

always @(posedge clk)

begin

Q=S|((~R)&Q);

Qbar=R|((~S)&(Qbar));

end

endmodule

## RTL REALIZATION:
![WhatsApp Image 2023-12-20 at 20 51 46_0243905f](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/62199ab4-4cd3-4fc8-b90c-05d94714239c)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)
## TRUTHTABLE:
![Screenshot 2023-12-20 210134](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/114ae702-3b48-4ef1-88d8-c56805bff757)

## WAVEFORM FOR SR:
![WhatsApp Image 2023-12-20 at 20 51 47_09b12a69](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/364ab21f-1102-452c-886b-c261a54ba340)


## JK Flip-Flop
## PROGRAM:
module flipflops(J,K,clk,Q,Qbar);

input J,K,clk;

output reg Q;

output reg Qbar;

initial Q=0;

initial Qbar=1;

always @(posedge clk)

begin

Q=(J&(~Q))|((~K)&Q);

Qbar=((~J)&(Qbar))|K&(~Qbar);

end

endmodule

# RTL REALIZATION:
![WhatsApp Image 2023-12-20 at 20 52 22_d891bc7e](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/24b47dc7-cd5e-4828-8715-6475a175fb41)
## TRUTHTABLE:
![Screenshot 2023-12-20 211207](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/4b125e5e-b900-4589-8094-ba922575ecc0)

## Output Waveform:
![WhatsApp Image 2023-12-20 at 20 52 22_67c00636](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/9ea4f1dd-84fe-4169-8802-29062f57983c)
## T FLIPFLOP:
module exp_5c(clk,T,q,qbar);

input clk,T;

output q,qbar;

reg q,qbar;

always @(posedge clk)

begin

q<=(T&~q)|(~T&q);

qbar<=~q;

end 

endmodule
## RTL REALIZATION:
![WhatsApp Image 2023-12-20 at 20 52 05_61a5a5ba](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/dab35cc8-87d1-474f-8955-9c8c8724a770)
## truthtable:
![image](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/b43c7e82-ac92-4c33-a21f-6a0b465906e5)
## WAVEFORM:
![WhatsApp Image 2023-12-20 at 20 52 05_8e6ca545](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/104519cf-9f8f-4425-a80d-ddd791872d8d)


## D flip flop:
module exp_5d(d,clk,q,qbar);

input d,clk;

output q,qbar;

reg q,qbar;

always @(posedge clk)

begin 

q<=d;

qbar<=~q;

end 

endmodule
## RTL REALIZATION:
![WhatsApp Image 2023-12-20 at 20 52 35_af5bfd61](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/92e0d52a-cc75-4367-9585-5ca70e1e8dd1)

## TRUTH TABLE:
![image](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/98953d7a-6fba-4c01-a974-aee0ddc52274)


## WAVEFORM:
![WhatsApp Image 2023-12-20 at 20 52 35_d79a5a41](https://github.com/23011258/Experiment--05-Implementation-of-flipflops-using-verilog/assets/139842204/08641bde-ea79-4919-baae-9acc235aaaad)



## RESULTS
By this we have verified the truth table of JK and SR using verilog.

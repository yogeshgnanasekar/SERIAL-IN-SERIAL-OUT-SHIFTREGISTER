## AIM:

To implement SISO Shift Register using verilog and validating their functionality using their functional tables

## SOFTWARE REQUIRED:

Quartus prime

## THEORY

## SISO shift Register

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

<img width="623" height="182" alt="image" src="https://github.com/user-attachments/assets/5fbcaa28-c43f-4b8a-a48e-8ff18bd7754b" />


## Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next. Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

## Procedure

1.Open Quartus Prime and create a new project for the SISO Shift Register.
2.Create a new Verilog HDL file and enter the Verilog program for the 4-bit SISO Shift Register.
3.Define the inputs CLK, SI, and CLEAR, and the serial output SO.
4.Implement the 4-bit shift register using a 4-bit register tmp.
5.Apply the CLEAR signal to reset the register to 0000.
6.On every positive edge of the clock, shift the stored data by one position and load the serial input into the first bit.
7.Assign the last bit of the register to the serial output SO.
8.Save the Verilog file and set it as the Top-Level Entity.
9.Compile the design using Start Compilation and check for errors.
10.Open the RTL Viewer to verify the generated SISO Shift Register circuit.
11.Open the Simulation Waveform Editor and add CLK, CLEAR, SI, and SO signals.
12.Apply suitable input combinations and clock pulses to verify the shifting operation.
13.Simulate the circuit and observe the output waveform.
14.Verify that the serial input data appears at the serial output after passing through the 4-bit register.
15.Compare the simulation results with the expected functional behavior and verify the operation of the SISO Shift Register.
## PROGRAM
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming.

module sisomod(clk,clear,si,so);
input clk,si,clear;
output so;
reg so;
reg [3:0] tmp;
always @(posedge clk )
begin
if (clear)
tmp <= 4'b0000;
else
tmp <= tmp << 1;
tmp[0] <= si;
so = tmp[3];
end
endmodule 


*/
```
## RTL LOGIC FOR SISO Shift Register
<img width="592" height="371" alt="image" src="https://github.com/user-attachments/assets/7c5d6fa7-fa34-4edf-8cb4-6efafaf310dd" />



## TIMING DIGRAMS FOR SISO Shift Register
<img width="823" height="80" alt="image" src="https://github.com/user-attachments/assets/2f7c76c5-22b2-4bce-a9d7-3f2f2f6949ec" />


## RESULTS 
The 4-bit Serial-In Serial-Out (SISO) Shift Register was successfully designed and implemented using Verilog HDL in Quartus Prime. The functional behavior of the circuit was validated through simulation waveforms, confirming that data shifts sequentially through the flip-flops on every positive edge of the clock signal.

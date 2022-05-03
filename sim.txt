`timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date: 03.05.2022 21:23:44
// Design Name: 
// Module Name: simulations
// Project Name: 
// Target Devices: 
// Tool Versions: 
// Description: 
// 
// Dependencies: 
// 
// Revision:
// Revision 0.01 - File Created
// Additional Comments:
// 
//////////////////////////////////////////////////////////////////////////////////


module part1_8bit_test();
    reg E;
    reg [1:0] FunSel;
    reg [7:0] I;
    reg CLK;
    
    wire [7:0] Q;
    PART1_8bit uut(.E(E),.FunSel(FunSel),.I(I),.Q(Q),.CLK(CLK));      
    initial begin
        CLK = 0;
        forever #10 CLK = ~CLK;     
    end  
    initial begin
        E = 1; FunSel = 2'b11; I = 8'b00000000; #25;
        E = 1; FunSel = 2'b10; I = 8'b00000000; #25;
        E = 0; FunSel = 2'b01; I = 8'b00000000; #25;
        E = 0; FunSel = 2'b10; I = 8'b00000010; #25;
        E = 1; FunSel = 2'b01; I = 8'b00000000; #25;
        E = 1; FunSel = 2'b01; I = 8'b00000000; #25;
        E = 1; FunSel = 2'b00; I = 8'b00000000; #25;
        E = 1; FunSel = 2'b11; I = 8'b00000000; #25;        
    end
endmodule
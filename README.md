# 16x1-mux-design
Behavioral description of 16x1 MUX using 4x1 MUX and 4x1 MUX using 2x1 
// 16x1 MUX using 5 4x1 MUX
`timescale 1ns / 1ps


module mux16x1(in,sel,out);
    input [15:0]in;
    input [3:0]sel;
    output out;

    wire [3:0]t;
    
    mux4x1 m01(in[3:0],sel[1:0],t[0]);
    mux4x1 m02(in[7:4],sel[1:0],t[1]);
    mux4x1 m03(in[11:8],sel[1:0],t[2]);
    mux4x1 m04(in[15:12],sel[1:0],t[3]);
    mux4x1 m05(t,sel[3:2],out);
endmodule

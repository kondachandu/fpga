`timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date: 20.05.2018 00:34:41
// Design Name: 
// Module Name: ioblock
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


module ioblock(inout pin,
                input ts,
                input out,
                output in,
                input ioclk
                          
    );
    reg dorreg,d;
    reg [1:0] tsmux;
    
      
     initial
     begin
      d=1'b0;
      tsmux=2'b01;
      dorreg=1'b1;
     end
    
    wire ctrl,a;
    
    mux2 m3(ctrl,ts,tsmux[1],tsmux[0]);
    buf b2(a,pin);
     dff ff1(a,d,ioclk);
    mux m4 (in,a,q,dorreg);
   
    bufif1 b1(pin,out,ctrl);   
endmodule









 


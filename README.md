# verilog_projects
module fulladd(
    input a,
    input b,
    input cin,
    output sum,
    output carry
    );
    wire s1,c1,c2;
    halfadder h1(a,b,s1,c1);
    halfadder h2(s1,cin,sum,c2);
    or(carry,c1,c2);
endmodule
module fabtb(

    );
    reg a,b,c;
    wire s,co;
    fab f1(a,b,c,s,co);
    initial begin
    a=1'b0;b=1'b0;c=1'b0;
    #10 a=1'b0;b=1'b0;c=1'b1;
    #10 a=1'b0;b=1'b1;c=1'b0;
    #10 a=1'b0;b=1'b1;c=1'b1;
    #10 a=1'b1;b=1'b0;c=1'b0;
    #10 a=1'b1;b=1'b0;c=1'b1;
    #10 a=1'b1;b=1'b1;c=1'b0;
    #10 a=1'b1;b=1'b1;c=1'b1;
    end
endmodule

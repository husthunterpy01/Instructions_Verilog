# Instructions_Verilog
Some basic instructions to do the exercises week 5 of the VHDL for Digital Desgin subject
- This instructions will mainly discuss some command to do the exercises using some structure relating to $generate, $monitor, $display and generave
## Generate
This allows generation for multiple subjects.
- Syntax
```
generate 
  [ genvar_declaration ]
  generate_scheme
    generate_block
endgenerate
```
+ This command can be comprehended as the way of for loop / if - else/ case which permits generating multiple instances of modules and primitives as well as generating multiple occurences of variables, nets, tasks, functions , continuous assignments, initial and always  procedural blocks.
+ The index variable within the loop must be a genvar variable.This variable can be declared inside the generate loop or in the module containg the generate loop
```
generate
  genvar i;
  for (i = 0; i < 10; i = i + 1)
    begin : gen
      initial $display("%d", i);
    end
endgenerate

generate
  if (A < B)
    Mult1 u1 (A, B, Q);
  else
    Mult2 u1 (A, B, Q);
endgenerate
```

## Genvar
- A genvar is a variable used in generate for loop. It stores positive integer values. It differs from other Verilog variables in that it can be assigned values and chaged during compilation and elaboration time
- The genvar must be declared within the module where it is used, but it can be declared either inside or outside of the generate loop.
Ex
```
generate
  genvar i;
  for (i = 0; i < 10; i = i + 1)
    begin : gen1
```    

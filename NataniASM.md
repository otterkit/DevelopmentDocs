```
//
// Natani Assembly Example
// Instruction Text Format
//

.with _system.io;        // Import standard library module "system.io"

.section _data:          // Data section contains all variables of a compiled file
  0x01 int := 5;         // 0x01 .. 0x64 are reserved for variable definitions
  0x02 int := 0;         // This serves as variable addresses after compilation
  0x03 int := 0;         // and can be passed as arguments to other instructions
.end _data;

.procedure _main:        // _main is the entry point of a compiled Natani program
  data.get 0x01;         // Get value from variable 0x01 and put it on the stack
  data.set 0x03;         // Set value of varible 0x03 to the first value on the stack

  
  .if 0x01 = 0:          // If value of variable 0x01 equals 0 then...
    stack.set 1;         // Set an integer of value 1 on top of the stack
    data.set 0x02;       // Set value of variable 0x02 to the first value on the stack
  .else                  // Else..
    data.get 0x01;       // Get value of variable 0x01 and set it on top of the stack
    stack.set 1;         // Set an interger of value 1 on top of the stack
    stack.sub;           // Subtract the first two values on the stack and set the result back on the stack
    data.set 0x01;       // Set value of variable 0x01 to the first value on the stack
    system.call 'main';  // "system.call" calls a procedure or subprocedure, this main procedure calls itself
    data.get 0x03;       // Get value of variable 0x03 and set it on top of the stack 
    data.get 0x03;       // Get value of variable 0x03 *again* and set it on top of the stack *again*
    stack.mul;           // Multiplies the first two values on the stack and set the result back on the stack
    data.set 0x03        // Set value of variable 0x03 to the first value on the stack
  .end;

  system.call 'print';   // "system.call" calls a procedure or subprocedure, this will call subprocedure "_print"
.end _main;              // Program stops execution

.subprocedure _print:    // _print subprocedure, can be called from the main procedure
  display 0x03;          // "system.io.display" prints to the console the value of a variable or any value passed to it, print value of variable 0x03
  display '! = ';        // "system.io.display" print a string to the console
  display 0x02;          // "system.io.display" print value of variable 0x02
end _print;
```

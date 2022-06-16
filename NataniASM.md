```
//
// Natani Assembly Example
// Instruction Text Format
//

.with _system.io;

.section _data:
  // 0x01 .. 0x64 are reserved for
  // variable definitions
  0x01 int := 5;
  0x02 int := 0;
  0x03 int := 0;
  // Type definition: 0x6a = integer
.end _data;

.procedure _main:
  // Get value from variable 0x01 and put it into the stack
  // Set value of varible 0x03 to the first value of the stack
  data.get 0x01;
  data.set 0x03;

  
  .if 0x01 = 0:
    stack.set 1;
    data.set 0x02;
  .else
    data.get 0x01;
    stack.set 1;
    stack.sub;
    data.set 0x01;
    system.call 'main';
    data.get 0x03;
    data.get 0x03;
    stack.mul;
    data.set 0x03
    num := num * fact;
  .end;

  system.call 'print';
.end _main;

.subprocedure _print:
  display 0x03;
  display '! = ';
  display 0x02;
end _print;
```

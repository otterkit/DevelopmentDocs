Natani Virtual Machine OPCodes:

|    Mnemonic   |  Hex OPCodes  |  Description                                                                                                  |
| ------------- | ------------- | ------------------------------------------------------------------------------------------------------------- |
|   ---------   | 0x01 ... 0x64 |  Reserved for variable addresses -- Total of 100 variable definitions per file                                |
|   int         |     0x6a      |  *address **int*** -- Integer type definition                                                                 |
|   float       |     0x6b      |  *address **float*** -- Float type definition                                                                 |
|   bool        |     0x6c      |  *address **bool*** -- Bool type definition                                                                   |
|   arr         |     0x6d      |  *address **arr*** -- Array type definition                                                                   |
|   struct      |     0x6e      |  *address **struct*** -- Struct type definition                                                               |
|   stack.set   |     0xa0      |  *stack.set **value*** -- Set a value on top of the stack                                                     |
|   stack.add   |     0xa1      |  *stack.add* -- Takes the first two values from the stack, adds them and sets the result on the stack         |
|   stack.sub   |     0xa2      |  *stack.sub* -- Takes the first two values from the stack, subtracts them and sets the result on the stack    |
|   stack.mul   |     0xa3      |  *stack.mul* -- Takes the first two values from the stack, multiplies them and sets the result on the stack   |
|   stack.div   |     0xa4      |  *stack.div* -- Takes the first two values from the stack, divides them and sets the result on the stack      |
|   data.get    |     0xa5      |  *data.get **variable*** -- Get value of a variable and set it on the stack                                   |
|   data.set    |     0xa6      |  *data.set **variable*** -- Set a variable's value to the first value on the stack                            |

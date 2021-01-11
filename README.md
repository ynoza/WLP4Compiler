# WLP4 Compiler

WLP4 is a subset of C++, and includes many key elements of C++ like functions, pointers, loops, and conditions! Because the inspiration for this project was derived from a Compliers course taken at UWaterloo the code cannot be public. However, if you are interested in seeing it you can email me at ynoza@uwaterloo.ca and I will send you a link.

The process for making the Complier followed all the essential steps that are quired like **Scanning, Parsing, Context-Sensitive Analysis, and of course Code Generation**.

**Scanning** consisted of tokenizing the code via the **Simplified Maximal Munch Algorithm** that involves backtracking (or possibly rejection) when input passes through accepting states. To do this the automata of **DFA** was adopted.

**Parsing** involved creating a derivation of some Context Free Grammar. It unequivocally generates a parse tree that appropriately demonstrates the structure of the code. Specifically, a **Bottom-Up Parsing** algorithm (LR(1) parser) was chosen.

**Context-Sensitive Analysis** consisted of identifying if the code passed from the previous step is WLP4 code. For example: A variable cannot be used before it is declared (keywords like extern are not part of WLP4). To do so all I had to do was go through the nodes of the parse tree given the tokenized code. 

**Code Generation** is the final step of the process and involved my favourite part Optimization! The code was compiled into MIPS code, and that was run through an emulator so that I could have a finished compiler that would be any valid WLP4 program! Some of the optimization techniques I used were **Constant Folding, Constant Propagation, Strength Reduction, and Dead Code Elimination**. The objective in mind while optimizing was not only improving the runtime of the program, but also reducing the size of the MIPS code that was generated. And this was especially difficult because of how conflicting the nature of the two goals are. However, I’m happy to say I was able to put a lot of time, effort, and brainpower into it and generate a finished product I was especially proud of!



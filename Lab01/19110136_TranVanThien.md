# 19110136, Trần Văn Thiên
# Lab 01: Buffer Overflow
# Task 1: Stack smashing by memory overwritten
## 1.1. bof1.c 
[[Ảnh 1.1.1](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.1.png)

### Idea:
#### We created a buffer with a capacity of 200 bytes as an array. We need to:
- Overflow the buffer with 200 + 8 bytes (including 4 junk bytes to overwrite the EBP register and 4 bytes of the memory address of the secretFunc function to overwrite the EIP register).
- Find the memory address of the secretFunc() function to overwrite the return address of the stack.
### Operation:
#### Step 1: Compile with GCC without stack protection and use some parameters to make the assembly code more readable.
[[Ảnh 1.1.3](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.2.png)
#### Step 2: Find the memory address of secretFunc() using GDB.
[[Ảnh 1.1.3](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.3.png)

The memory address of function secretFunc: 804846b => 0804846b => \x6b\x84\x04\x08.
#### Step3: Generate a buffer overflow with python scripting
[[Ảnh 1.1.4](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.4.png)
#### Result:
[[Ảnh 1.1.5](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.5.png)

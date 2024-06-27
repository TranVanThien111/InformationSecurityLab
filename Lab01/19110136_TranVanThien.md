# 19110136, Trần Văn Thiên
# Lab 01: Buffer Overflow
# Task 1: Stack smashing by memory overwritten
## 1.1. bof1.c 
[[Link ảnh code](http://https://vi.wikipedia.org/wiki/Markdown)
](https://github.com/TranVanThien111/InformationSecurityLab/blob/main/Lab01/Images/1.1.1.png)

### Idea:
#### We created a buffer with a capacity of 200 bytes as an array. We need to:
- Overflow the buffer with 200 + 8 bytes (including 4 junk bytes to overwrite the EBP register and 4 bytes of the memory address of the secretFunc function to overwrite the EIP register).
- Find the memory address of the secretFunc() function to overwrite the return address of the stack.
### Operation:
#### Step 1: Compile with GCC without stack protection and use some parameters to make the assembly code more readable.
Affected Version:
liblisp 4c65969405d38cabb47e7b86eb19232073cdaf7d

Vulnerability Description:
The vulnerability is a memory leak bug located at line 245 of the file /liblisp/src/io.c. This vulnerability could potentially be exploited maliciously to cause resource exhaustion and denial of service attacks.

liblisp download address:
https://github.com/howerj/liblisp.git

1.In the if statement at line 242 of the file io.c in /liblisp/src, dynamic memory space is allocated for the pointer variable i using calloc. When calloc is successful in allocating memory space for the pointer variable i at line 242, but fails to allocate memory space for i->p.str at line 244, the program will return at line 245 without releasing the memory area already allocated for the pointer variable i, leading to memory leakage, as shown in the figure below:

![image](https://github.com/LuMingYinDetect/liblisp_defects/blob/main/liblisp_1.png)

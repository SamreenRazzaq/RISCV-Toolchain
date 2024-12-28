# RISCV-Toolchain
### **C++ to RISC-V Assembly, Machine Code, and Hexadecimal Conversion**  

This project demonstrates a step-by-step process for converting C++ code into RISC-V assembly, machine code, and hexadecimal formats using the RISC-V toolchain. It serves as a practical guide to understanding the compilation and translation of high-level code into executable forms compatible with RISC-V processors.  

#### **Workflow Overview**  

1️⃣ **Convert C++ Code to RISC-V Assembly**  
- Write your C++ program (e.g., `factorial.cpp`).  
- Use the RISC-V cross-compiler to generate assembly instructions:  
  ```bash  
  riscv64-unknown-elf-g++ -S factorial.cpp -o factorial.s  
  ```  
  - Output: `factorial.s` (RISC-V assembly code).  

2️⃣ **Generate Machine Code from Assembly**  
- Assemble the RISC-V assembly file into machine code (object file):  
  ```bash  
  riscv64-unknown-elf-as -o factorial.o factorial.s  
  ```  
- Optional: Link the object file to create an executable:  
  ```bash  
  riscv64-unknown-elf-ld -o factorial factorial.o  
  ```  
  - Output: `factorial.o` (object file) or `factorial` (executable).  

3️⃣ **Convert Machine Code to Hexadecimal**  
- Disassemble the program to view machine code in hexadecimal format:  
  ```bash  
  riscv64-unknown-elf-objdump -d factorial > factorial_dump.txt  
  ```  
  - Output: `factorial_dump.txt` (disassembly with hexadecimal).  
- Alternatively, extract raw binary machine code:  
  ```bash  
  riscv64-unknown-elf-objcopy -O binary factorial factorial.bin  
  ```  
  - Output: `factorial.bin` (binary machine code).  

#### **Key Outputs**  
- **Assembly Code**: Human-readable RISC-V instructions (`factorial.s`).  
- **Machine Code**: Object file for execution (`factorial.o`).  
- **Hexadecimal Representation**: Memory-friendly machine code in hexadecimal (`factorial_dump.txt`).  

This project illustrates the complete journey from high-level C++ code to low-level RISC-V formats, bridging the gap between software development and processor architecture.  

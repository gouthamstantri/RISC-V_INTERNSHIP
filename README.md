# RISC-V Internship Project

## Overview

This repository contains the work completed during the RISC-V internship program. The primary focus is on developing and testing RISC-V-based applications and understanding the underlying architecture.

## Table of Contents

- [Project Structure](#project-structure)
- [Installation](#installation)
- [Task 1: Sum of Numbers and Optimization Comparison](#task-1-sum-of-numbers-and-optimization-comparison)
- [Usage](#usage)
- [Contributions](#contributions)
- [Acknowledgments](#acknowledgments)

## Project Structure


## Installation

To set up the project locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/gouthamstantri/RISC-V_Internship.git

   Task 1: Sum of Numbers and Optimization Comparison
Overview
This task involves creating a simple C program to calculate the sum of numbers up to n, compiling it with different optimization levels (O1 and Ofast) using the RISC-V toolchain, and analyzing the outputs.

Steps
Step 1: Write the Program
Open a terminal and create the file:
bash
Copy code
leafpad sum_numbers.c
Note: If leafpad is not installed, use:

bash
Copy code
sudo apt install leafpad
Add the following code to sum_numbers.c:
c
Copy code
#include <stdio.h>

int main() {
    int n, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        sum += i;
    }

    printf("Sum of numbers up to %d is: %d\n", n, sum);
    return 0;
}
Save and exit the editor.
Step 2: Compile and Run with Optimization Level O1
Compile the program with O1 optimization:
bash
Copy code
riscv64-unknown-elf-gcc -O1 -o sum_numbers_O1 sum_numbers.c
Run the program using a RISC-V simulator:
bash
Copy code
spike pk sum_numbers_O1
Enter a value for n and observe the output.
Step 3: Compile and Run with Optimization Level Ofast
Compile the program with Ofast optimization:
bash
Copy code
riscv64-unknown-elf-gcc -Ofast -o sum_numbers_Ofast sum_numbers.c
Run the program:
bash
Copy code
spike pk sum_numbers_Ofast
Enter a value for n and observe the output.
Step 4: Analyze and Compare
Use objdump to inspect assembly instructions:

bash
Copy code
riscv64-unknown-elf-objdump -d sum_numbers_O1 > O1_dump.txt
riscv64-unknown-elf-objdump -d sum_numbers_Ofast > Ofast_dump.txt
Open the dumps and count instructions:

Each instruction is 4 bytes.
Example: 44 bytes = 11 instructions.
Compare the instruction counts:

O1 optimization produces more instructions.
Ofast optimization uses aggressive optimizations, resulting in fewer instructions.
Acknowledgments
Special thanks to:

Kunal Ghosh and VSD (VLSI System Design) for providing guidance, resources, and support throughout the internship program.

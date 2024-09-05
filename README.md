# CompressedLUT
Lookup tables are widely used in hardware applications to store arrays of constant values. They can be directly used to evaluate nonlinear functions or used as a part of other approximate methods (e.g., piecewise linear approximation and bipartite tables) to compute such functions. CompressedLUT is a tool for lossless compression of lookup tables and generation of their hardware files in Verilog for RTL designs. 

CompressedLUT was origionally developed as a part of the following publication:
> Alireza Khataei and Kia Bazargan. 2024. CompressedLUT: An Open Source Tool for Lossless Compression of Lookup Tables for Function Evaluation and Beyond. In Proceedings of the 2024 ACM/SIGDA International Symposium on Field Programmable Gate Arrays (FPGA ’24), March 3–5, 2024, Monterey, CA, USA. ACM, New York, NY, USA, 10 pages. https://doi.org/10.1145/3626202.3637575

The original code can be found here: https://github.com/kiabuzz/CompressedLUT
## Authors
- Oliver Cassidy, Imperial College London, London, UK (modifications)
- Alireza Khataei, University of Minnesota, Minneapolis, MN, USA (original)
- Kia Bazargan (kia@umn.edu), University of Minnesota, Minneapolis, MN, USA (original)


## Installation
```bash
git clone https://github.com/ollycassidy13/CompressedLUT.git
cd CompressedLUT
make
```
    
## Getting Started
#### Lookup Table as a Text File
A text (.txt) file, containing the values of your lookup table, should be prepared. The file must contain a power of 2 lines, each of which is a single hexadecimal value. An example of such a text file can be found in example.txt. The following command generates hardware files corresponding to the lookup table described in that text file.

```bash
./compressedlut -table example.txt
```

See the help.txt file for command line arguments in more detail.

## Summary of Modifications
- Fixed output bitwidth calculated initially
- Unique sub-table and bias bitwidths calculated and then fixed before the assignment of values to either table
- Higher-bit cost calculation updated to use these fixed values
- RTL updated to build files losslessly using the fixed values where applicable

## Copyright & License Notice
It can be freely used for educational and research purposes by non-profit institutions and US government agencies only. Other organizations are allowed to use CompressedLUT only for evaluation purposes, and any further uses will require prior approval. The software may not be sold or redistributed without prior approval. One may make copies of the software for their use provided that the copies, are not sold or distributed, are used under the same terms and conditions.

As unestablished research software, this code is provided on an ``as is'' basis without warranty of any kind, either expressed or implied. The downloading, or executing any part of this software constitutes an implicit agreement to these terms. These terms and conditions are subject to change at any time without prior notice.

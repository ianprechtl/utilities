# utilities
Useful scripts for FPGA support

## fpga_elf_dma
Breaks down an .elf into .txt files containing section information and data. Used to DMA cross-compiled binaries to target FPGA. Writes two files: program_sections.txt (section header information) and program_compressed.txt (compressed binary data).

1. Compile to target
> toolchain-gcc -o program.elf
2. Copy to binary 
> toolchain-objcopy -O binary program.txt
3. Extract program information
> readelf program.elf -l > program_info.txt
4. Run script
> python fpga_elf_dma.py -i program


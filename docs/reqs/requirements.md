# Requirements Document for Single Port Synchronous RAM in HDL

## 1 - Introduction
This document outlines the requirements for a Single Port Synchronous Random Access Memory (RAM) to be designed using Hardware Description Language (HDL). The SPS RAM will provide synchronous read and write operations with a single data port.

## 2 - Requirements

| **#**     | **Requirement**                                      | **Description**                                                                                                                    |
|-----------|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **1**     | *Memory Inputs and Outputs*                          |                                                                                                                                     |
| **1.a**   | *Address Input (i_addr)*                             | The SPS RAM shall have a single address input port (`i_addr`). The width of this port shall be parametric based on the depth of the memory (`MEM_DEPTH`).                   |
| **1.b**   | *Write Data Input (i_wr_data)*                       | The SPS RAM shall have a single write data input port (`i_wr_data`). The width of this port shall be parametric (`DATA_WIDTH`).             |
| **1.c**   | *Read Data Output (o_rd_data)*                       | The SPS RAM shall have a single read data output port (`o_rd_data`). The width of this port shall be parametric (`DATA_WIDTH`).           |
| **2**     | *Memory Control Signals*                             |                                                                                                                                     |
|           | *Write Enable (i_we)*                                | The SPS RAM shall have a single write enable input signal (`i_we`). This signal shall be used to control the write operation.               |
| **3**     | *Memory Functionality*                               |                                                                                                                                     |
| **3.a**   | *Read Operation*                                     | During a read operation, the SPS RAM shall output the data stored at the memory location specified by the current address on the `i_addr` port. |
| **3.b**   | *Write Operation*                                    | During a write operation, the SPS RAM shall store the data present on the `i_wr_data` port at the memory location specified by the current address on the `i_addr` port. |
| **4**     | *Registering and Resetting*                          |                                                                                                                                     |
| **4.a**   | *Data Output Registration*                           | The data on the `o_rd_data` port shall be registered. This ensures that the output data remains stable during the next clock cycle.      |
| **4.b**   | *Non-Resettable Registers*                           | The registers used in the design shall not have a reset functionality. The data stored in the registers shall persist across clock cycles. |
| **5**     | *Memory Depth and Width*                             |                                                                                                                                     |
|           | *Parametric Depth and Width*                         | The depth of the memory (number of memory locations) (`MEM_DEPTH`) and the width of the data input and output ports (`DATA_WIDTH`) shall be user-accessible module parameters. |
| **6**     | *Clock Signal*                                       |                                                                                                                                     |
|           | *Clock (i_clk)*                                      | The SPS RAM shall have a single clock input signal (`i_clk`). This signal shall be used to synchronize the read and write operations.         |
| **7**     | *Design Language*                                    |                                                                                                                                     |
|           | *Hardware Description Language (HDL)*                | The SPS RAM shall be designed using a hardware description language suitable for digital circuit design. The specific language choice will be determined during the implementation phase. |


## 3 - Revision History
| **Version** | **Revision History** | **Author**   | **Description of Changes** |
|:-----------:|:--------------------:|:------------:|:--------------------------:|
| 0.0.1       | 09 May 2024          | Emre Kirkaya | Initial release            |
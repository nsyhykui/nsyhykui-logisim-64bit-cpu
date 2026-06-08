# 64 位 CPU（Logisim-evolution 实现）

从零开始在 Logisim-evolution 中设计的 64 位 CPU。

## 现状

- 64 位数据总线，64 位地址空间（实际使用 24 位）
- 32 条通用寄存器（R0-R31）
- 支持算术运算（ADD、SUB、AND、OR）
- 支持内存访问（LDA、STA）
- 支持条件跳转（JZ、JNZ、JC、JNC、JN、JP、JO、JNO）
- 支持比较指令（CMP）
- 支持无条件跳转（JMP）和输出（OUT）
- 程序和数据共用 RAM

## 指令集

| 类型 | 指令 | opcode | 功能 |
|------|------|--------|------|
| 运算 | ADD | 0x11 | rd = rs1 + rs2 |
| 运算 | SUB | 0x12 | rd = rs1 - rs2 |
| 运算 | AND | 0x13 | rd = rs1 & rs2 |
| 运算 | OR | 0x14 | rd = rs1 \| rs2 |
| 内存 | LDA | 0x01 | rd = mem[addr] |
| 内存 | STA | 0x03 | mem[addr] = rs |
| 输出 | OUT | 0x0e | 输出 rs 到 LED |
| 跳转 | JMP | 0x08 | PC = addr |
| 跳转 | JZ | 0x20 | if ZF==1: PC = addr |
| 跳转 | JNZ | 0x21 | if ZF==0: PC = addr |
| 跳转 | JC | 0x22 | if CF==1: PC = addr |
| 跳转 | JNC | 0x23 | if CF==0: PC = addr |
| 跳转 | JN | 0x24 | if SF==1: PC = addr |
| 跳转 | JP | 0x25 | if SF==0: PC = addr |
| 跳转 | JO | 0x26 | if OF==1: PC = addr |
| 跳转 | JNO | 0x27 | if OF==0: PC = addr |
| 比较 | CMP | 0x28 | 比较 rs1, rs2，设置标志位 |

## 已知问题

- 仿真较慢（行波进位加法器 + 64 位总线）
- 无流水线，单条 LDA/STA 需 2 周期
- 部分功能未充分测试

## 如何运行

1. 用 Logisim-evolution 4.1.0+ 打开 `sikir.circ`
2. 双击 RAM 元件，手动写入机器码
3. 按 `Ctrl+K` 运行仿真

## 文件说明

- `mycomputer_64.circ` - CPU 主电路
- `isa.md` - 指令集详细说明
- `README.md` - 本文件

## 许可证

Apache 2.0

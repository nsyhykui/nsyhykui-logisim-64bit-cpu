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

# 64 位 CPU（Logisim-evolution 实现）

没什么特别的原因，就是突然想搭一个 64 位的。然后就在 Logisim-evolution 里试了一下。

**不一定对，但能跑。**

## 现状
- 支持 LDA、ADD、OUT、JMP 四条指令
- 64 位数据总线，32 位指令
- 纯 RAM 架构，程序手动写入
- 能跑 5+3=8 循环

## 已知问题
- 仿真慢（行波进位加法器 + 64 位总线）
- 指令集简单
- 没做优化

## 怎么跑
1. Logisim-evolution 4.1.0+ 打开 `mycomputer_64.circ`
2. 双击 RAM，按示例程序写数据
3. `Ctrl+K` 运行，看 LED

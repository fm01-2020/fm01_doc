# FMSMD-2

胖蚊子步进电机驱动板 (4 路), 使用 HR8833MTE (TSSOP16 封装) 芯片.

HR8833MTE 主要性能:

+ 一个 HR8833 含有 2 个全桥电路, 可以驱动 1 只双极步进电机 (4 线), 或 2 只有刷电机.

+ 电压: 2.7 ~ 15V (步进电机) 或 10.8V (有刷电机).

+ 电流: 1.5A

+ 细分: 1, 2.


## PCB 设计参数

| 序号 | 项目 | 数值 |
| :--: | :-- | ---: |
| 1 | PCB 大小 | 20x50mm |
| 2 | 材质 | FR-4 厚度 1.6mm 铜箔厚度 1oz (35um) |
| 3 | 层数 | 2 (双面) |
| 4 | 最小线宽线距 | 0.16mm (6mil) |
| 5 | 最小过孔内径 | 0.3mm |
| 6 | 最小过孔外径 | 0.6mm |
| 7 | 最小字符高度 | 0.8mm |
| 8 | 最小过孔间距 | 0.4mm |
| 9 | 最小过孔与线间距 | 0.25mm |
| 10 | 最小非金属化槽宽度 | 0.8mm |

推荐加工厂: [嘉立创](https://www.jlc.com/)


## 元件清单

| 序号 | 引用 | 型号 | 封装 | 数量 | 价格 (CNY) |
| :--: | :-- | :--- | :--: | --: | ---------: |
| 1 | `U1`, `U2`, `U3`, `U4` | HR8833MTE | TSSOP16 | 4 | 1.2 x4 = 4.8 |
| 2 | `Q1`, `Q2`, `Q3`, `Q4` | AON6504 (NMOS 30V 85A 3.2mR) | DFN5x6 (6x5mm) | 4 (不上件, 可选) | 0.7 x0 = 0 |
| 3 | `Q11`, `Q12`, `Q21`, `Q22`, `Q31`, `Q32`, `Q41`, `Q42` | AO3422 (NMOS 55V 2.1A 200mR) | SOT23 | 8 (不上件, 可选) | 0.08 x0 = 0 |
| 4 | `R11`, `R12`, `R21`, `R22`, `R31`, `R32`, `R41`, `R42` | 电阻 (限流电阻) | 0603 (SMD) | 8 | 0.03 x8 = 0.24 |
| 5 | `R15`, `R16`, `R25`, `R26`, `R35`, `R36`, `R45`, `R46` | 电阻 0R | 0402 (SMD) | 8 (不上件, 可选) | 0 |
| 6 | `R18`, `R28`, `R38`, `R48` | 电阻 10k | 0402 (SMD) | 4 | 0.024 x4 = 0.10 |
| 7 | `C10`, `C20`, `C30`, `C40` | 电容 10uF 20V | 0805 (SMD) | 4 | 0.15 x4 = 0.6 |
| 8 | `C11`, `C21`, `C31`, `C41` | 电容 10nF 16V | 0402 (SMD) | 4 | 0.06 x4 = 0.24 |
| 9 | `C12`, `C22`, `C32`, `C42` | 电容 2.2uF 6.3V | 0402 (SMD) | 4 | 0.02 x4 = 0.08 |
| 总计 | 48 | 9 | 6 | 28 | 6.06 |

注: 价格仅供参考.


## 接口引脚说明

| 序号 | 引用 | 说明 |
| :--: | :-- | :--- |

TODO


## 限流电阻

HR8833 限流电阻的选择.

HR8833 的内置检测电压固定为 0.2V.
使用通过两个限流电阻的电流来限制两个全桥的电流.

| 序号 | 封装 | 阻值 (R) | 精度 | 电流 (A) | 推荐 (3x / 6*) | 价格 (CNY) |
| :--: | :--: | ------: | ---: | ------: | :-----------: | --------: |
| 1 | 0603 | 0.13 | 1% | 1.54 | | 0.03 |
| 2 | 0603 | 0.14 | 1% | 1.43 | * x | 0.025 |
| 3 | 0603 | 0.15 | 1% | 1.33 | | 0.03 |
| 4 | 0603 | 0.16 | 1% | 1.25 | | 0.08 |
| 5 | 0603 | 0.18 | 1% | 1.11 | | 0.03 |
| 6 | 0603 | 0.20 | 1% | 1.00 | * | 0.03 |
| 7 | 0603 | 0.25 | 1% | 0.80 | | 0.03 |
| 8 | 0603 | 0.3 | 1% | 0.67 | * | 0.03 |
| 9 | 0603 | 0.4 | 1% | 0.50 | | 0.03 |
| 10 | 0603 | 0.5 | 1% | 0.40 | * x | 0.03 |
| 11 | 0603 | 0.62 | 1% | 0.32 | | 0.03 |
| 12 | 0603 | 0.82 | 1% | 0.24 | | 0.03 |
| 13 | 0603 | 1.0 | 1% | 0.20 | * | 0.025 |
| 14 | 0603 | 1.1 | 1% | 0.18 | | 0.03 |
| 15 | 0603 | 1.2 | 1% | 0.17 | | 0.03 |
| 16 | 0603 | 1.3 | 1% | 0.15 | | 0.03 |
| 17 | 0603 | 1.4 | 1% | 0.14 | | 0.025 |
| 18 | 0603 | 1.5 | 1% | 0.13 | | 0.03 |
| 19 | 0603 | 1.8 | 1% | 0.11 | | 0.03 |
| 20 | 0603 | 2.0 | 1% | 0.10 | * x | 0.025 |
| 21 | 0603 | 2.4 | 1% | 0.08 | | 0.025 |
| 22 | 0603 | 2.8 | 1% | 0.07 | | 0.025 |
| 23 | 0603 | 3.3 | 1% | 0.06 | | 0.025 |
| 24 | 0603 | 5.1 | 1% | 0.04 | | 0.025 |

注: 价格仅供参考.

为降低限流电阻购买成本, 现给出推荐组合:

1. 推荐 * 组合: 0.1A, 0.2A, 0.4A, 0.67A, 1.0A, 1.43A (共 6 种).

   此组合限定为最多同时安装 2 个限流电阻.
   此组合可以实现的电流为:

   0.1A, 0.2A, 0.3A (0.2+0.1), 0.4A, 0.5A (0.4+0.1), 0.6A (0.4+0.2),
   0.67A, 0.8A (0.4+0.4), 0.87A (0.67+0.2), 1.0A, 1.1A (1.0+0.1), 1.2A (1.0+0.2), 1.43A.

   如果精确到 0.1A, 则此组合无法实现 1.3A.

2. 推荐 x 组合: 0.1A, 0.4A, 1.43A (共 3 种).

   此组合限定为最多同时安装 4 个限流电阻.
   此组合可以实现的电流为:

   0.1A, 0.2A (0.1x2), 0.3A (0.1x3), 0.4A, 0.5A (0.4+0.1), 0.6A (0.4+0.1x2), 0.7A (0.4+0.1x3),
   0.8A (0.4x2), 0.9A (0.4x2+0.1), 1.0A (0.4x2+0.1x2), 1.2A (0.4x3), 1.3A (0.4x3+0.1), 1.43A.

   如果精确到 0.1A, 则此组合无法实现 1.1A.


## 功能电路

TODO


## 保护电路

此电路板没有设置保护电路, 使用时请小心, 请正确接线, 并注意对应电压.


## 电路板制造历史

| 序号 | 版本号 | 材质 | 阻焊颜色 | 生产文件 | 工厂 | 数量 | 测试结果 | 备注 |
| :--: | :---- | :--- | :-----: | :-----: | :--: | --: | :------ | :--- |

TODO
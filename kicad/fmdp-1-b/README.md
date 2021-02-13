# FMDP-1-B

胖蚊子超声波驱动板.

FMDP-1 完整电路主要由以下部分构成:

1. **廉价 ATX 电源**

   将 220V 交流电转换为 12V 输出, 为作为整个系统的主电源, 功率约 200W, 成本约 CNY 10.

2. **可调升压电路**

   输出电压 12 ~ 48 V, 输出功率 50W (最大).

3. **压电陶瓷片驱动电路**

   采用半桥结构, 输出方波, 输出频率 1.6 ~ 2.0 MHz.

4. **压电陶瓷片前置 LC 低通滤波电路**

   将驱动方波转换为正弦波, 最终驱动压电陶瓷片.

5. **压电陶瓷片**

   1.7MHz 工作频率, 20mm 直径, 功率约 2W, 电压约 24V (估计), 成本约 CNY 1.7.

6. **控制及辅助电路**

   控制器 stm32f103c8t6 开发小板 (蓝色药丸, blue pill), 成本约 CNY 8.8.
   热敏电阻温度检测电路, LED 指示灯, 急停按钮, 等.

FMDP-1 完整电路分为 **板上电路** 和 **板外电路**, FMDP-1-B 只包括板上电路部分.


## PCB 设计参数

| 序号 | 项目 | 数值 |
| :--: | :-- | ---: |
| 1 | PCB 大小 | 17x50mm |
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

板上电路的器件:  (对应原理图 `FMDP-1-B.sch`)

| 序号 | 引用 | 型号 | 封装 | 数量 | 价格 (CNY) |
| :--: | :-- | :--- | :--: | --: | ---------: |
| 1 | `U1`, `U2` | UCC27211 半桥驱动芯片 (4A 120V 7.2ns) | SOIC-8 | 2 | 3 x2 = 6 |
| 2 | `Q1`, `Q2`, `Q3`, `Q4` | NMOS AOD482 (32A 100V 37mR 7ns) | TO-252 | 4 | 0.45 x4 = 1.8 |
| 3 | `C1`, `C3` | 电容 0.1uF 100V 陶瓷 | SMD 0805 | 2 | 0.09 x2 = 0.18 |
| 4 | `C2`, `C4` | 电容 10uF 25V 陶瓷 | SMD 0805 | 2 | 0.15 x2 = 0.3 |
| 5 | `D1`, `D2` | LED | SMD 0402 | 2 | 0.08 x2 = 0.16 |
| 6 | `R1`, `R2` | 电阻 LED 限流 | SMD 0402 | 2 | 0.04 x2 = 0.08 |
| 7 | `R11`, `R12`, `R13`, `R14`, `R15`, `R16`, `R17`, `R18`, `R21`, `R22`, `R23`, `R24`, `R25`, `R26`, `R27`, `R28` | 电阻 分压检测 (100k, 4.7k, 3.3k) | SMD 0402 | 16 | 0.04 x16 = 0.6 |
| 总计 | 30 | 9 | 4 | 30 | 9.2 |

板外电路的器件:  (对应原理图 `FMDP-1-full.sch`)

| 序号 | 引用 | 型号 | 封装 | 数量 | 价格 (CNY) |
| :--: | :-- | :--- | :--: | --: | ---------: |
| 1 | `L1` | 电感 240uH 25A 大功率 1.0mm 双线并绕 | 插件 | 1 | 6 |
| 2 | `C1` | 电容 1000uF 50V 铝电解 | 插件 | 1 | 0.6 |
| 3 | `C2` | 电容 470uF 100V 铝电解 | 插件 | 1 | 1.4 |
| 4 | `RI1`, `RI2` | 电流传感器 ACS758 (50A 量程) | 插件 | 2 | 5.8 x2 = 11.6 |
| 总计 | 5 | 4 | | 5 | 19.6 |

单个压电陶瓷单元的器件:  (对应原理图 `FMDP-1-full.sch`)

| 序号 | 引用 | 型号 | 封装 | 数量 | 价格 (CNY) |
| :--: | :-- | :--- | :--: | --: | ---------: |
| 1 | `Y1` | 压电陶瓷片 1.7MHz 直径 20mm 功率 2W | | 1 | 1.7 |
| 2 | `L2` | 电感 2.2uH | 插件 0410 色环电感 | 1 | 0.07 |
| 3 | `C3` | 电容 1000pF 250V 高压瓷片 | 插件 | 1 | 0.05 |
| 总计 | 3 | 3 | | 3 | 1.9 |

注: 价格仅供参考.

### FMDP-1 电路部分成本分析

| 序号 | 名称 | 说明 | 数量 | 价格 (CNY) |
| :--: | :-- | :--- | ---: | ---------: |
| 1 | `FMDP-1-B` | 压电陶瓷片驱动板 (板上电路) | 1 ~ 2 | 10 ~ 20 |
| 2 | FMDP-1 板外电路 | 板外电路的器件 | 1 ~ 2 | 19.6 ~ 39.2 |
| 3 | 压电陶瓷片单元 | 单个换能器及相关器件 | 1 ~ 48 | 1.9 ~ 91.2 |
| 4 | 控制器 | stm32f103c8t6 开发小板 | 1 | 8.8 |
| 5 | 电源 | 二手 ATX 电源 200W | 1 | 10 |
| 总计 | | | 5 ~ 54 | 51 ~ 170 |

注: 价格仅供参考.


## 接口引脚说明

| 序号 | 引用 | 说明 |
| :--: | :-- | :--- |

TODO


## 功能电路

TODO

### 可调升压电路

TODO

### 压电陶瓷片驱动方波电路

TODO

### 前置 LC 低通滤波电路

TODO

### LED 指示灯驱动电路

TODO

### 电阻分压电路

TODO

### 电压电流检测电路

TODO

### 急停按钮

TODO

### 热敏电阻温度检测电路

TODO

### 控制板信号连接

TODO


## 保护电路

此电路板没有设置保护电路, 使用时请小心, 请正确接线, 并注意对应电压.


## 电路板制造历史

| 序号 | 版本号 | 材质 | 阻焊颜色 | 生产文件 | 工厂 | 数量 | 测试结果 | 备注 |
| :--: | :---- | :--- | :-----: | :-----: | :--: | --: | :------ | :--- |
| 1 | `FMDP-1-B v0.1` 2020-12-30 | FR-4 厚度 1.6mm | 黄 | | [嘉立创](https://www.jlc.com/) | 5 | (测试中) | |

(2021-01-10)
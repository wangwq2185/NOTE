# 芯片的Corner
## 1 Corner定义
将工艺(Process)、电压(Voltage)、温度(Temperature)分级，指极端的工艺或者环境。
## 2 为什么需要Corner
芯片制造是一个物理过程，存在着工艺偏差（包括掺杂浓度、扩散深度、刻蚀程度等），导致不同批次之间，同一批次不同晶圆之间，同一晶圆不同芯片之间情况都是不相同的。在一片wafer上，不可能每点的载流子平均漂移速度都是一样的，随着电压、温度不同，它们的特性也会不同。在各种corner和极限温度条件下对电路进行仿真(在后仿的时候就要根据不同的Corner进行仿真)，使其在各种corner上都能正常工作，才能使最终生产出的芯片良率高(最终目的，提高良率)。
## 3 Corenr的分类
### 3.1 Process corener
由于全局工艺偏差对 CMOS 中 NMOS，PMOS 的影响有所不同，因此按照晶体管的速度，可以分为以下 5 种 process corner：
|Corner|NMOS|PMOS|
|-|-|-|
|TT|Typical|Typical|
|FF|Fast|Fast|
|SS|Slow|Slow|
|FS|Fast|Slow|
|SF|Slow|Fast|
                  
`Typical 是指晶体管驱动电流是一个平均值，Fast 是指驱动电流是其最大值，而 Slow 是指驱动电流是其最小值`                       
NMOS和PMOS在工艺上是独立做出来的，彼此之间不会影响，但是对于电路，NMOS和PMOS是同时工作的，会出现NMOS快的同时PMOS也快，或者慢，所以会出现FF、SS、FS、SF四种情况。通过Process注入的调整，模拟器件速度快慢，同时根据偏差大小设定不同等级的FF和SS。正常情况下大部分是TT，而以上5种corner在+/-3sigma可以覆盖约99.73%的范围，这种随机性的发生符合正态分布。
### 3.2 Voltage Corner
晶体管的速度随着电压的升高而提高。因此，时序签收时需要考虑极限电压的情况，以保证芯片在整个电压范围内能够正常工作。
### 3.3 Temperature Corner
温度会影响晶体管的速度。时序签收时，能够保证芯片在设计的整个温度范围内能够正常工作。由于结温与环境温度的差异，需要保留足够的设计余量。

### 3.4 PVT Corner
将Process Corener、Voltage Corener、Temperature Corener叠加形成PVT Corner(后仿的Corener常用PVT Corner)。常见用例：
|PVT Corner|Description|Process|Voltage|Temperature|
|-|-|-|-|-|
|wcl|worst case low temperature|SS|low|low|
|wc|worst case slow|SS|low|high|
|lt|low temperature|FF|high|low|
|ml|max leakage|FF|high|  high|
|tc|typical|TT|standard|standard|
`


# grbl-uno-4axes

这是一个专为**热线切割机**修改的 Grbl 版本，已移植到 Arduino UNO，支持四轴控制。
默认采用双平面配置：**XY / UZ**。

推荐配合 **FOAM WING STATION** 进行控制。

---

## 引脚映射 (Arduino UNO)

| 功能 | 引脚 | 说明 |
| :--- | :--- | :--- |
| **步进脉冲 (Step)** | | |
| X Axis | D2 | | 
| Y Axis | D3 | |
| Z Axis | D4 | |
| Q Axis | D12 | 第四轴 (默认 U) |
| **方向控制 (Dir)** | | |
| X Axis | D5 | |
| Y Axis | D6 | |
| Z Axis | D7 | |
| Q Axis | D13 | 第四轴 (默认 U) |

---

## 预设参数 (`defaults.h`)

```c
// 每毫米步数 (Steps per mm)
#define DEFAULT_X_STEPS_PER_MM (400)
#define DEFAULT_Y_STEPS_PER_MM (400)
#define DEFAULT_Z_STEPS_PER_MM (400)
#define DEFAULT_Q_STEPS_PER_MM (400)
```

**步数计算方法 (螺杆传动)：**
$$Steps\_per\_mm = \frac{电机每转步数 \times 驱动细分}{螺杆导程 (mm)}$$
*例如：NEMA 17 电机 (1.8°/200步) + 16细分 + 8mm导程螺杆*
$$\frac{200 \times 16}{8} = 400\ steps/mm$$

---

## 编译与上传

1. **准备环境**：下载并安装 [Arduino IDE](https://www.arduino.cc/en/software)
2. **导入库**：`项目` -> `包含库` -> `添加 .ZIP 库...`
3. **打开示例**：`文件` -> `示例` -> `grbl-uno-4axes` -> `grblUpload`
4. **配置开发板**：
   - 选择：`工具` -> `开发板` -> `Arduino Uno`
   - 选择对应的串口
5. **上传**

---

## 参考项目

- [Grbl Main Repository](https://github.com/grbl/grbl)
- [grblQ-Mega-4axes (LETARTARE)](https://github.com/LETARTARE/grblQ-Mega-4axes)



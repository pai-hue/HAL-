
---

## STM32CubeMX 新建工程完整步骤

### 1. 新建工程

- 打开 STM32CubeMX，点击 **File → New Project**
- 在搜索框输入芯片型号（如 `STM32F103C8T6`），双击选中
  ![alt text](image.png)

---

### 2. 配置时钟源（RCC）

- 左侧 **Pinout & Configuration → System Core → RCC**
- `High Speed Clock (HSE)` 选 **Crystal/Ceramic Resonator**（使用外部晶振）
  ![alt text](image-2.png)

---

### 3. 配置调试接口（SYS）

- **System Core → SYS**
- `Debug` 选 **Serial Wire**（SWD 调试）
  ![alt text](image-1.png)

---

### 4. 配置时钟树（Clock Configuration）

- 点击顶部 **Clock Configuration** 标签
- 设置 HCLK 频率（如 F103 最高 72MHz）
- 点击 **Resolve Clock Issues** 或手动配置 PLL
  ![alt text](image-3.png)

---

### 5. 配置外设（按需）

- 在 **Pinout & Configuration** 中启用需要的外设（GPIO、UART、SPI、I2C 等）
- 配置对应参数（波特率、模式等）

---

### 6. 配置工程设置

- 点击顶部 **Project Manager** 标签
- **Project Name**：填写工程名
- **Project Location**：选择保存路径（路径不要有中文）
- **Toolchain/IDE**：选 **MDK-ARM**
- **Min Version**：选对应的 Keil 版本（如 V5）
![alt text](image-4.png)
---

### 7. 配置代码生成选项

- 切换到 **Code Generator** 子标签
- 勾选 **Copy only the necessary library files**（只复制用到的库，减小体积）
- 勾选 **Generate peripheral initialization as a pair of '.c/.h' files**（外设分文件生成，结构更清晰）
  ![alt text](image-5.png)

---

### 8. 生成代码

- 点击右上角 **GENERATE CODE**
- 弹窗提示后点击 **Open Project**，自动在 Keil 中打开工程
![alt text](image-6.png)
---

### 9. Keil 中编译验证

- 点击编译按钮（F7），确认 **0 Error, 0 Warning**
- 工程结构中用户代码写在 `/* USER CODE BEGIN */` 和 `/* USER CODE END */` 之间，重新生成代码时不会被覆盖
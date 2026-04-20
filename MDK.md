## MDK核心知识点

### 1. **MDK基本概念**

- MDK（Microcontroller Development Kit）（微控制器开发工具）是ARM公司的Keil开发的嵌入式开发工具
- 专门用于ARM Cortex-M系列微控制器开发
- 集成了编译器、调试器、项目管理等功能

### 2. **主要组件**

- **μVision IDE**：集成开发环境，提供代码编辑、项目管理界面
- **ARM编译器**：支持ARMCC（v5）和ARM Compiler 6（基于LLVM）
- **CMSIS**：Cortex微控制器软件接口标准
- **RTX RTOS**：实时操作系统
- **Pack Installer**：软件包管理器，用于安装芯片支持包

### 3. **工程管理**

- **Project结构**：Target（目标）→ Group（组）→ File（文件）
- **Target配置**：可配置多个编译目标（Debug/Release）
- **文件分组**：按功能模块组织源文件
- **依赖管理**：自动处理头文件依赖关系

### 4. **编译配置**

- **C/C++选项**：
    
    - Optimization（优化级别：-O0/-O1/-O2/-O3）
    - Define（宏定义）
    - Include Paths（头文件路径）
    - Language/Code Generation（语言标准、代码生成选项）
- **Linker选项**：
    
    - Scatter File（分散加载文件）
    - Memory Layout（内存布局配置）
    - 库文件链接
- **Output选项**：
    
    - HEX/BIN文件生成
    - Browse Information（浏览信息）
    - Debug Information（调试信息）

### 5. **调试功能**

- **仿真调试**：
    
    - Software Simulator（软件仿真器）
    - 无需硬件即可调试
- **硬件调试**：
    
    - ULINK调试器支持
    - J-Link/ST-Link等第三方调试器
    - SWD/JTAG接口配置
- **调试工具**：
    
    - Breakpoints（断点：硬件/软件断点）
    - Watch Window（监视窗口）
    - Memory Window（内存查看）
    - Peripheral View（外设寄存器查看）
    - Logic Analyzer（逻辑分析仪）
    - Call Stack（调用栈）
    - Disassembly（反汇编窗口）

### 6. **CMSIS支持**

- **CMSIS-Core**：核心外设访问层
- **CMSIS-Driver**：外设驱动接口
- **CMSIS-DSP**：数字信号处理库
- **CMSIS-RTOS**：实时操作系统API

### 7. **启动文件与系统配置**

- **startup_xxx.s**：汇编启动文件
    
    - 堆栈配置
    - 中断向量表
    - SystemInit调用
- **system_xxx.c**：系统初始化文件
    
    - 时钟配置
    - SystemCoreClock变量

### 8. **Pack包管理**

- 通过Pack Installer安装芯片支持包
- 包含：
    - Device支持文件
    - CMSIS库
    - 示例工程
    - 芯片手册链接

### 9. **代码优化技巧**

- 编译优化级别选择
- Inline函数使用
- 循环展开
- 代码大小vs速度权衡
- 使用`__attribute__`关键字

### 10. **常用快捷键**

- **F7**：编译（Build）
- **F8**：下载程序
- **F5**：开始调试
- **F10**：单步跳过（Step Over）
- **F11**：单步进入（Step Into）
- **Ctrl+F10**：运行到光标处

### 11. **分散加载文件（Scatter File）**

- 定义代码和数据在内存中的分布
- 配置ROM/RAM区域
- 支持多区域加载

### 12. **实用功能**

- **Code Template**：代码模板
- **User Code Template**：用户自定义模板
- **Version Control**：版本控制集成
- **External Tools**：外部工具集成
- **Batch Build**：批量编译

### 13. **性能分析**

- **Execution Profiler**：执行性能分析
- **Code Coverage**：代码覆盖率分析
- **Event Recorder**：事件记录器

### 14. **常见问题处理**

- Stack Overflow（栈溢出）
- Heap不足
- Hard Fault调试
- 编译错误/警告处理
- 下载失败排查
# 第八届中国集成电路创新大赛 —— 图像处理加速系统

## 项目简介
本仓库收录了我们团队在第八届中国集成电路创新大赛专题赛中的完整设计与源码。项目基于 Xilinx Vivado 2018.3，利用 FPGA 实现对图像数据的高速读取、处理和显示，具备可复现与二次开发的特性。

## 目录结构
```text
.
├── Vivado_prj/             # FPGA 工程
│   ├── Picture_Data/       # 原始图片数据（*.coe / *.bin）
│   └── TOP/
│       ├── SRC/            # RTL 源码（single_ROM2.v 等）
│       └── ...             # Vivado 生成文件
├── Robei_prj/              # Robei 建模工程，Top.v 为顶层
└── readme.md               # 项目说明文档
```

## 快速开始

1. 克隆仓库  
   ```bash
   git clone <repo-url>
   ```

2. 修改图片路径  
   `single_ROM2.v` 默认使用绝对路径读取 `Picture_Data` 中的 `.coe` 文件。  
   请将下列语句中的路径替换为本地路径：  

   ```verilog
   // Vivado_prj/TOP/SRC/single_ROM2.v
   // ...
   localparam ROM_FILE = "D:/your/path/to/Picture_Data/img.coe";
   ```

3. 打开 Vivado 2018.3 并生成位流  
   双击文件 `Vivado_prj/TOP/TOP.xpr` 打开工程，然后点击 `Generate Bitstream` 生成位流并烧录到开发板。

## 环境要求
- Vivado 2018.3
- 推荐硬件：Xilinx Artix-7 FPGA 系列开发板
- 仓库已在 Windows 10 & Ubuntu 22.04 环境验证

## 相关资料
- `Robei_prj` 目录包含基于 Robei 的系统建模文件，可用于快速原型设计。
- `Vivado_prj/Picture_Data` 提供测试图片数据，也可替换为自定义图片。

## 致谢
- 第八届中国集成电路创新大赛官方组委会  
- 指导老师与团队成员

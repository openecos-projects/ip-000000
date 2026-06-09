# ip-000000

中文说明 | [English](#english)

## 基本信息

- 名称：SYS_UART
- UID：ip-000000
- IP 家族：uart
- 分类：peripheral
- 上游来源：OpenCores UART 16550 compatible project
- 当前基线：2025-06-27 流片工程代码，本地 RTL 镜像，上游 commit 未知
- 许可证：LGPL-2.1-or-later
- 状态：candidate

本仓库是 `ip-catalog` 的单 IP 子仓库，包含一个 Verilog 编写的
UART 16550 兼容控制器，并带有一个本地 APB 风格封装。

## 仓库内容

- `rtl/uart_apb.v`：APB 风格顶层封装。
- `rtl/uart16550/`：来自 OpenCores 项目族的 UART 16550 兼容 RTL 文件。
- `ip.yaml`：与 `ip-catalog` 对齐的本地元数据。
- `upstream.lock`：上游来源与镜像策略记录。
- `docs/reviews/ip-000000.md`：当前评审记录。
- `reports/filelist.f`：供 Verilog 工具使用的 RTL 文件列表。

## 顶层模块

集成顶层模块为 `uart_apb`。

关键端口：

- `clk`、`resetn`：APB 时钟和低有效复位。
- `in_psel`、`in_penable`、`in_paddr`、`in_pwrite`、`in_pwdata`、`in_prdata`、`in_pready`、`in_pslverr`：APB 风格寄存器访问接口。
- `uart_rx`、`uart_tx`：串口接收和发送引脚。

## 收录状态说明

OpenCores 来源的 UART RTL 文件头部带有 LGPL-2.1-or-later 许可证声明。
仓库顶层已补充 `LICENSE` 文件，用于 catalog 许可证评审。

当前代码来源于 2025-06-27 流片工程代码，并已完成流片验证。当前源码包未记录
镜像 RTL 对应的精确上游 commit，因此仍需在后续评审中补充工程版本、流片项目
记录或等价来源凭证。

## English

[Back to Chinese](#ip-000000)

## Basic Information

- Display name: SYS_UART
- UID: ip-000000
- Family: uart
- Category: peripheral
- Upstream: OpenCores UART 16550 compatible project
- Current baseline: 2025-06-27 tapeout project code, local RTL mirror, upstream commit unknown
- License: LGPL-2.1-or-later
- Status: candidate

This repository is a single-IP child repository for `ip-catalog`. It contains
a Verilog UART 16550-compatible controller with a local APB-style wrapper.

## Contents

- `rtl/uart_apb.v`: APB-style top-level wrapper.
- `rtl/uart16550/`: UART 16550-compatible RTL files from the OpenCores project family.
- `ip.yaml`: local metadata aligned with `ip-catalog`.
- `upstream.lock`: upstream source and mirror policy record.
- `docs/reviews/ip-000000.md`: current review notes.
- `reports/filelist.f`: RTL file list for Verilog tools.

## Top Level

The integration top module is `uart_apb`.

Key ports:

- `clk`, `resetn`: APB clock and active-low reset.
- `in_psel`, `in_penable`, `in_paddr`, `in_pwrite`, `in_pwdata`, `in_prdata`, `in_pready`, `in_pslverr`: APB-style register interface.
- `uart_rx`, `uart_tx`: serial receive and transmit pins.

## Catalog Status

The bundled OpenCores-origin UART RTL files carry LGPL-2.1-or-later license
headers. A repository-level `LICENSE` file is included for catalog review.

The current code comes from the 2025-06-27 tapeout project code and has been
silicon validated. The exact upstream commit for the mirrored RTL is not
recorded in the current source drop, so future review should still attach the
project version, tapeout record, or an equivalent provenance reference.

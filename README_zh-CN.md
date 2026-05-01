# ThoughtTrace Pro 🧠⌨️

[![Version](https://img.shields.io/badge/version-2.8.0-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()

> *Read this in [English](README.md) | [繁體中文](README_zh-TW.md)*

**ThoughtTrace Pro** 是一个基于浏览器的写作行为取证框架，专为区分“人类原创认知”与“AI 辅助搬运”而设计。

与传统基于 NLP 的 AI 检测工具（仅关注最终文本）不同，ThoughtTrace 专注于分析写作过程中的**行为生物特征（Behavioral Biometrics）**。

# 解决痛点
现有的 AI 检测工具在面对“人肉抄写 AI”或“深度洗稿”时往往失效，且容易产生伪阳性（False Positives），误杀原创作者。

#  核心技术：行为取证
ThoughtTrace 通过监控击键动力学（Keystroke Dynamics）、上下文切换和输入熵，生成完整的**会话审计轨迹（Audit Trail）**。我们不审查文字内容，我们审查文字是“如何”被产生的。

＃ 核心算法
*   **专属基准线校准 (Baseline Calibration)：** 在写作开始前建立个人的击键指纹（CV值），消除不同硬件设备带来的误差。
*   **同步覆盖率 (Sync Coverage)：** 动态比对 DOM 文本长度与实际有效按键数，精准拦截外部剪贴板注入（大段粘贴）。
*   **认知熵分析 (Cognitive Entropy)：** 分析按键延迟的变异系数 (CV)。真实的人类思考会产生非线性的节奏抖动；而看着 AI 抄写则会呈现机械化、匀速的输入特征。
*   **焦点流失追踪 (Focus Loss Tracking)：** 监控窗口切换与失焦事件，有效防范对着外部 AI 画面进行“洗稿”的行为。

#  快速开始
本项目为零依赖的 Local-first 原型（Vanilla JS）。
1. Clone 本项目。
2. 在任何现代浏览器中直接打开 `index.html`。
3. 完成初始校准（Calibration）即可解锁安全编辑器。

#隐私与安全
**100% 本地端运算。** ThoughtTrace Pro 仅依赖浏览器的 `localStorage` 进行状态管理。用户的击键特征与文本内容**绝对不会**被传送至云端服务器。

# 审计报告
系统可一键导出 **PDF 行为审计报告**。报告内含行为转向时间轴（例如先出现 `[大规模粘贴]`，随后出现 `[人类原创修复]`），为教育工作者提供完整的行为上下文，而非单一死板的评分。

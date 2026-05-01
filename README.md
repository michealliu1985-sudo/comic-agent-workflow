🎬 Comic Agent Workflow


<p align="center">
<img src="https://img.shields.io/badge/Version-1.0.0-blue.svg" alt="Version">
<img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
<img src="https://img.shields.io/badge/Python-3.13+-orange.svg" alt="Python">
<img src="https://img.shields.io/badge/OpenClaw-2026.3.20-red.svg" alt="OpenClaw">
</p>


🤖 基于 OpenClaw 的智能漫剧创作工作流 —— 用多Agent协作自动生成漫画剧集
✨ 特性


多Agent协作: 剧本、角色、分镜、审核四大智能体无缝协作
自动化工作流: 一键生成完整漫画内容，从剧本到分镜
质量把控: 内置审核Agent确保内容合规性
易于扩展: 模块化设计，支持自定义Agent
跨平台: 支持本地部署和云端API调用
🏗️ 技术架构


plaintext
┌─────────────────────────────────────────────────────────────────┐
│                      Comic Agent Workflow                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   ┌──────────────┐    ┌──────────────┐    ┌──────────────┐      │
│   │   📝 输入     │───▶│ ScriptWriter │───▶│   剧本结构    │      │
│   │   原始故事    │    │   Agent      │    │   分析结果    │      │
│   └──────────────┘    └──────────────┘    └──────┬───────┘      │
│                                                   │              │
│                                                   ▼              │
│   ┌──────────────┐    ┌──────────────┐    ┌──────────────┐      │
│   │   剧本结构    │───▶│CharacterDes- │───▶│   角色设定    │      │
│   │   分析结果    │    │  igner Agent │    │   文档       │      │
│   └──────────────┘    └──────────────┘    └──────┬───────┘      │
│                                                   │              │
│                                                   ▼              │
│   ┌──────────────┐    ┌──────────────┐    ┌──────────────┐      │
│   │   角色设定    │───▶│ Storyboard  │───▶│   分镜脚本    │      │
│   │   文档       │    │  Gen Agent   │    │   输出       │      │
│   └──────────────┘    └──────────────┘    └──────┬───────┘      │
│                                                   │              │
│                                                   ▼              │
│                                            ┌──────────────┐      │
│                                            │QualityReview │      │
│                                            │    Agent     │      │
│                                            └──────┬───────┘      │
│                                                   │              │
│                                                   ▼              │
│                                            ┌──────────────┐      │
│                                            │   📤 最终     │      │
│                                            │   输出文件    │      │
│                                            └──────────────┘      │
└─────────────────────────────────────────────────────────────────┘

📁 目录结构


plaintext
comic-agent-workflow/
├── README.md                 # 项目说明文档
├── openclaw_demo.py          # 演示脚本
├── requirements.txt          # Python依赖
├── workflow/
│   ├── __init__.py
│   ├── script_writer.py       # 剧本Agent
│   ├── character_designer.py  # 角色设定Agent
│   ├── storyboard_gen.py      # 分镜生成Agent
│   └── quality_review.py      # 质量审核Agent
├── examples/
│   └── demo.py                # 演示脚本
├── tests/
│   └── test_workflow.py       # 单元测试
└── docs/
    └── architecture.md        # 架构文档

🚀 快速开始
环境要求


Python 3.13+
OpenClaw SDK 2026.3.20+
CMDOP API Key
安装


bash
# 克隆项目
git clone https://github.com/michealliu1985-sudo/comic-agent-workflow.git
cd comic-agent-workflow

# 安装依赖
pip install -r requirements.txt

# 配置环境变量
export CMDOP_API_KEY="cmdop_your_api_key_here"

使用示例


python
from workflow import ComicWorkflow

# 初始化工作流
workflow = ComicWorkflow(api_key="cmdop_your_api_key")

# 执行漫剧创作
result = workflow.run(
    story="在一个遥远的星系，少年星河偶然发现了",
    genre="科幻冒险",
    episode_count=24
)

print(result)

命令行使用


bash
python -m workflow.cli --story "你的故事" --genre "科幻" --episodes 24

🔧 Agent 详解


Agent	功能	输入	输出
ScriptWriter	剧本创作	原始故事	结构化剧本
CharacterDesigner	角色设定	剧本	角色描述
StoryboardGen	分镜生成	角色+剧本	分镜脚本
QualityReview	质量审核	分镜脚本	审核报告
🤝 贡献指南


欢迎提交 Issue 和 Pull Request！


Fork 本仓库
创建特性分支 (git checkout -b feature/amazing)
提交更改 (git commit -m 'Add amazing feature')
推送到分支 (git push origin feature/amazing)
创建 Pull Request
📝 更新日志
v1.0.0 (2026-04)


✨ 初始版本发布
🤖 支持4种核心Agent
📦 支持本地和云端部署
📄 License


本项目采用 MIT License - 详见 LICENSE 文件


<p align="center">
<sub>Built with ❤️ by Comic Agent Team | Powered by <a href="https://cmdop.com">CMDOP</a></sub>
</p>

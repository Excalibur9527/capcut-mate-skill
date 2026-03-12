# CapCut Mate 自动化技能

这是一个为 OpenClaw 开发的剪映（CapCut）自动化剪辑技能，通过调用 CapCut Mate API，实现视频草稿的自动化创建、素材导入及云端渲染。

## 🚀 项目概述
CapCut Mate 是一个完全开源、免费的剪映草稿自动化助手，支持本地部署，让大型语言模型具备基础视频编辑能力。

## 🛠️ 安装与部署说明

### 1. 服务端部署（CapCut Mate Server）

#### 方式一：Python 原生部署（推荐）
需确保已安装 `Python 3.11+` 和 `uv` 包管理器。
```bash
# 克隆仓库
git clone https://github.com/Hommy-master/capcut-mate.git
cd capcut-mate

# 安装依赖
uv sync
# (Windows 系统需额外执行: uv pip install -e .[windows])

# 启动服务
uv run main.py
```
*服务启动后，默认端口为 `30000`。*

#### 方式二：Docker 快速部署
```bash
docker-compose pull && docker-compose up -d
```

---

## ⚙️ OpenClaw 技能配置
在你的 OpenClaw 环境 `TOOLS.md` 中添加 API 地址：
```markdown
### CapCut Mate 配置
- CAPCUT_MATE_URL: http://localhost:30000/openapi/capcut-mate/v1
```

---

## 📚 核心 API 接口概览

| 模块 | 核心接口 | 功能描述 |
| :--- | :--- | :--- |
| **草稿管理** | `create_draft` | 创建新草稿项目，设置画布尺寸 |
| **视频处理** | `add_videos` | 批量添加视频，支持裁剪、缩放 |
| **音频处理** | `add_audios` | 批量添加音频，支持音量调节与淡入淡出 |
| **字幕处理** | `add_captions` | 批量添加字幕，支持样式设置 |
| **特效动画** | `add_effects`, `add_keyframes` | 添加视觉特效、关键帧动画控制 |
| **视频生成** | `gen_video` | 提交云渲染任务（异步处理） |

*(更多辅助接口请访问 http://localhost:30000/docs 查看完整交互文档)*

## 🛠️ 高级用法：桌面端客户端
如果你需要桌面图形界面，可在项目目录下执行：
```bash
# 安装依赖
npm install --verbose
# 启动 Web 开发版
npm run web:dev
# 启动客户端
npm start
```
*注意：macOS 环境下需在系统设置中给予应用相应的文件夹访问权限。*

## 💡 开发支持
- **Coze 插件**: 本项目支持一键导入 Coze 平台作为插件使用。
- **更多文档**: 请参阅项目根目录下的 `docs/` 文件夹获取 macOS 沙盒权限配置及其他技术细节。
- **开源社区**: 如有疑问，可搜索项目文档中的微信群二维码进群交流。

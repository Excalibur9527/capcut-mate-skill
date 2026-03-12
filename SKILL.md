# CapCut Mate 自动化技能

这是一个用于 OpenClaw 的剪映（CapCut）自动化剪辑技能，通过调用 CapCut Mate API 实现视频草稿的自动化创建、素材导入及渲染。

## 🚀 功能特点
- 自动化创建剪映草稿
- 批量导入视频、音频、图片素材
- 支持关键帧动画、字幕添加与特效设置
- 自动化提交云渲染任务

## 🛠️ 环境依赖
1. **CapCut Mate 服务**: 确保你的 CapCut Mate 服务已在本地（或 Docker）启动。
2. **Node.js 环境**: Skill 运行时需要 Node 环境。

## ⚙️ 配置说明
在 OpenClaw 的 `TOOLS.md` 中配置 API 地址：
```markdown
### CapCut Mate 配置
- CAPCUT_MATE_URL: http://localhost:30000/openapi/capcut-mate/v1
```

## 📚 使用示例
```javascript
const capcut = require('capcut-mate');

// 创建草稿
const draft = await capcut.createDraft(1080, 1920);

// 添加视频
await capcut.addVideos(draft.url, [{ url: '...', start: 0, end: 5000 }]);

// 渲染视频
await capcut.genVideo(draft.url);
```

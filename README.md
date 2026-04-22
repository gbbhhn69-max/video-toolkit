# 视频快剪工具 · VideoKit

纯前端视频工具：截取片段 + 缩小分辨率，支持批量处理，输出为 WebM 视频文件（单个）或 ZIP 压缩包（批量）。

## 自己用（零配置）

双击 `index.html` 用浏览器打开即可。推荐 Chrome / Edge。

## 上线给别人用

最简单的两种方式：

### 方式 1：GitHub Pages

1. 在 GitHub 新建仓库，把 `index.html` 上传到仓库根目录
2. 仓库 → Settings → Pages → Source 选 `Deploy from a branch`，分支选 `main`，保存
3. 等 1-2 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`

### 方式 2：Cloudflare Pages（国内访问更稳定）

1. 注册 https://dash.cloudflare.com
2. Workers & Pages → Create → Pages → Upload assets
3. 拖拽 `index.html` 进去 → Deploy

## 功能

| 功能 | 说明 |
|------|------|
| 截取片段 | 时间轴拖动 / 输入 HH:MM:SS，批量时所有视频应用相同范围 |
| 缩小尺寸 | 8 种预设（1080p / 720p / 540p / 360p / 25% / 50% / 75% / 自定义），批量一键 |
| 同时处理 | 先截取再缩小，一次搞定 |
| 换视频 | 工作区顶部"🔄 换视频"按钮，无需刷新页面即可重新选文件 |
| 批量处理 | 多选视频 → 一键处理 → 下载 **单个 ZIP 压缩包** |
| 本地处理 | 视频不上传服务器，浏览器内完成 |
| 输出格式 | **WebM**（Chrome / Edge / Safari 17+ / 微信原生支持） |

## 推荐浏览器

- **Chrome / Edge（任意现代版本）** → 最稳定
- Safari 17+ → 可用
- Firefox → 可用

## Windows 用户怎么播 WebM

- 直接在 **Chrome** 或 **Edge** 里拖进去播
- 或者装 [VLC](https://www.videolan.org/vlc/)（30 秒免费安装，什么格式都能播）
- 新版 Windows 11 自带的 Movies & TV 也能播

## 已知限制

- **源视频编码**：HEVC/H.265、部分 MOV、MKV 浏览器无法解码。上传失败请先用剪映/格式工厂转成标准 **MP4（H.264）** 再上传
- **时长**：建议 ≤ 5 分钟。处理时间约等于视频时长（Canvas 实时录制原理）
- **不支持 MP4 输出**：Chrome 的 MP4 MediaRecorder 目前不稳定，会产出 0 秒的空文件，所以先统一用 WebM 保证可用
- **图片/截图**：工具只接视频文件，拖截图会提示"不支持这个文件类型"

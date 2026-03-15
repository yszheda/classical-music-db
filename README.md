# 古典音乐专辑 Booklet 收藏库

> **⚠️ 重要声明**  
> 本收藏库中的专辑内页（Booklet）文字内容系通过 **AI 大语言模型** 对原版扫描文档进行 OCR 识别和翻译生成，**仅供学习与研究参考**。

## 📋 AI 生成内容声明

### 内容来源

本库包含：

1. **原版扫描**：唱片内页（Booklet）的高清扫描图片
2. **AI 生成文字**：
   - 原文识别：使用 AI 模型对扫描图片进行 OCR 文字识别
   - 中文翻译：使用 AI 模型将外文（英/法/德/意等）翻译为中文

### 可能的误差

由于 AI 模型的局限性，以下内容**可能存在误差**：

| 类型 | 说明 |
|---|---|
| **OCR 识别错误** | 专有名词、人名、地名、作品编号可能识别有误 |
| **翻译误差** | 音乐术语、历史背景、文化典故可能翻译不准确 |
| **事实性错误** | 日期、地点、演奏者信息等可能与原版有出入 |
| **格式问题** | 段落划分、标点符号可能与原文不一致 |

### 使用建议

- ✅ **参考学习**：可作为欣赏音乐、了解作品的辅助资料
- ✅ **对比校勘**：建议对照原版扫描图片核对重要信息
- ❌ **学术引用**：不建议直接用于学术研究或正式出版
- ❌ **商业使用**：禁止用于任何商业用途

### 纠错反馈

如果您发现任何事实性错误或翻译问题，**欢迎指正**！

---

## 📀 收藏概览

本库收录古典音乐专辑 **30+ 张**，涵盖：

### 作曲家

- **巴赫**：平均律钢琴曲集、英国组曲、法国组曲、赋格的艺术
- **德彪西**：钢琴独奏作品、钢琴二重奏早期作品
- **莫扎特**：钢琴协奏曲、歌剧咏叹调
- **巴托克**：钢琴作品、管弦乐作品
- **李斯特**：匈牙利狂想曲、钢琴改编曲
- **浪漫派**：肖邦、舒曼、勃拉姆斯等

### 演奏家

- **钢琴家**：Andrei Vieru、Andrew Rangell、Zoltán Kocsis、Alexis Weissenberg、Alfred Brendel 等
- **指挥家**：Ivan Fischer、Ferenc Fricsay、Sir Charles Mackerras 等
- **歌唱家**：Birgit Nilsson、Maria Callas、Renata Tebaldi、Giuseppe di Stefano 等
- **室内乐**：Alfred Cortot、Tibor Varga 等

### 唱片厂牌

- ECM、Philips、Erato、Naxos、Bridge、Steinway & Sons、Harmonia Mundi、Alpha 等

---

## 📁 专辑结构

每个专辑文件夹包含：

```
专辑名称 (厂牌)/
├── 1. 专辑基本信息.md      # 演奏者、曲目、录音时间、厂牌编号等
├── 2. Booklet 原文.md       # AI 识别的原版内页文字（外文）
├── 3. Booklet 中文翻译.md   # AI 翻译的内页文字（中文）
├── cover.jpg               # 专辑封面
├── back.jpg                # 专辑封底
└── scans/                  # 内页完整扫描图片
    ├── HIPPO_xxxxxx_0001.jpg
    ├── HIPPO_xxxxxx_0002.jpg
    └── ...
```

---

## 🛠️ Git 管理工具

本库使用 Git 进行版本控制，**仅追踪 Markdown 文档**，图片文件保留在本地但不纳入版本控制。

### 快速命令

```bash
# 添加所有 Markdown 文件
git add-md

# 查看 Markdown 状态
git status-md

# 快速提交
git cm "提交信息"

# 查看 Markdown 差异
git diff-md

# 查看 Markdown 历史
git log-md
```

### 脚本工具

| 脚本 | 说明 |
|---|---|
| `./scripts/add-md.sh` | 添加所有 Markdown 文件 |
| `./scripts/commit-md.sh "消息"` | 添加并提交 |
| `./scripts/md-status.sh` | 查看 Markdown 状态 |

详细文档见 `scripts/README.md`。

---

## 📄 许可证与版权

- **扫描图片**：版权归原作者唱片公司所有，仅供个人学习研究
- **AI 生成文字**：基于原版 Booklet 生成，版权归原版权方所有
- **本库结构**：自由使用，欢迎分享

---

## 📬 联系方式

如有任何问题、建议或纠错，欢迎联系。

---

*最后更新：2026 年 3 月 15 日*

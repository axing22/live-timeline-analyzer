# 📊 直播公屏时间轴分析系统

> 专业的直播数据可视化分析工具，让数据洞察触手可及

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-GitHub_Pages-blue?style=for-the-badge)](https://axing22.github.io/live-timeline-analyzer/live_timeline_analyzer_v2.html)
[![GitHub](https://img.shields.io/github/license/axing22/live-timeline-analyzer?style=for-the-badge)](https://github.com/axing22/live-timeline-analyzer/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/axing22/live-timeline-analyzer?style=for-the-badge)](https://github.com/axing22/live-timeline-analyzer/stargazers)

## ✨ 功能特色

### 📈 数据分析核心功能
- **智能CSV解析** - 自动识别数据格式，支持多种编码
- **三层时间轴** - 普通用户、助教互动、分享消息分层展示
- **实时筛选** - 关键词搜索、机器人过滤、消息分类
- **多维统计** - 活跃用户、互动频次、高峰时段全面分析

### 📊 可视化图表
- **📈 互动趋势图** - 时间序列柱状图，支持多时间粒度
- **☁️ 词云分析** - 高频词汇可视化，N-Gram智能分词
- **🏆 用户排行榜** - TOP活跃用户统计与排名
- **😊 情感分析** - 积极/中性/消极情感分布饼图

### 🎨 用户体验
- **响应式设计** - 完美适配桌面端和移动端
- **拖拽上传** - 支持文件拖放和点击上传
- **实时交互** - 悬停提示、缩放控制、时间轴导航
- **一键导出** - 高清PNG图片导出，支持1920×1080分辨率

## 🚀 快速开始

### 在线体验
点击上方Live Demo按钮即可在线使用，无需安装任何软件。

### 本地运行
```bash
# 克隆仓库
git clone https://github.com/axing22/live-timeline-analyzer.git

# 进入目录
cd live-timeline-analyzer

# 在浏览器中打开
open live_timeline_analyzer_v2.html
```

### 数据格式
CSV文件需包含以下字段：
```csv
时间,用户ID,用户昵称,平台,发言内容,是否机器人
2025-01-20 19:00:01,u001,张三,抖音,老师好,0
```

## 📊 数据统计

系统提供6项核心统计指标：

| 指标 | 说明 | 计算方式 |
|------|------|----------|
| **有效消息** | 过滤机器人后的真实用户消息数 | 总消息数 - 机器人消息数 |
| **活跃用户** | 参与互动的独立用户数量 | 去重用户ID统计 |
| **助教互动** | 助教/老师的回复消息数 | 昵称包含"助教"/"老师"的消息 |
| **分享次数** | 用户分享直播间的次数 | 包含"刚刚分享了直播间"的消息 |
| **高峰时段** | 消息量最高的时间段 | 按小时聚合的最大值 |
| **平均/分钟** | 每分钟平均消息数 | 总消息数 ÷ 时间跨度(分钟) |

## 📚 使用指南

### 1️⃣ 数据导入
1. 点击上传区域或拖拽CSV文件
2. 系统自动解析并验证数据格式
3. 显示解析结果和基础统计信息

### 2️⃣ 时间轴分析
- **缩放控制**：50%-300%缩放比例
- **时间粒度**：30秒/1分钟/2分钟/5分钟
- **消息筛选**：实时关键词搜索
- **类型分离**：普通/助教/分享消息分层

### 3️⃣ 图表切换
- **互动趋势**：时间段消息分布分析
- **词云分析**：高频词汇可视化展示
- **用户排行**：活跃度TOP10用户
- **情感分析**：消息情感倾向统计

### 4️⃣ 数据导出
点击"导出为高清图片"按钮，生成包含完整分析结果的PNG报告。

## 🛠️ 技术架构

### 前端技术栈
- **HTML5** - 语义化标签与现代Web标准
- **CSS3** - Tailwind CSS响应式设计
- **JavaScript ES6+** - 模块化架构与异步处理
- **Canvas API** - 高性能图表绘制

### 核心模块
```javascript
📦 架构设计
├── 📊 DataProcessor      # 数据处理引擎
├── 🕒 TimelineRenderer   # 时间轴渲染器  
├── 📈 ChartRenderer      # 图表绘制引擎
├── 📤 ExportManager      # 导出管理器
└── 🎮 App               # 主应用控制器
```

### 性能特性
- ⚡ **高性能处理** - 支持10000+条数据实时分析
- 🔄 **增量渲染** - 智能更新机制，流畅交互体验
- 💾 **内存优化** - 数据分层缓存，减少内存占用
- 📱 **移动优化** - 触摸手势支持，移动端友好

## 🤝 贡献指南

欢迎提交Issue和Pull Request！

### 开发环境
1. Fork本仓库
2. 创建功能分支 `git checkout -b feature/AmazingFeature`
3. 提交更改 `git commit -m 'Add some AmazingFeature'`
4. 推送分支 `git push origin feature/AmazingFeature`
5. 创建Pull Request

## 📄 许可证

本项目采用 MIT 许可证

## 👨‍💻 作者

**xiaowenjie** - [@axing22](https://github.com/axing22)

---

⭐ 如果这个项目对你有帮助，请给它一个Star！

## 🔗 相关链接

- [在线演示](https://axing22.github.io/live-timeline-analyzer/live_timeline_analyzer_v2.html)
- [GitHub仓库](https://github.com/axing22/live-timeline-analyzer)
- [问题反馈](https://github.com/axing22/live-timeline-analyzer/issues)
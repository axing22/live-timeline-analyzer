# 直播公屏时间轴分析系统 - 自动开发任务

## 🎯 开发目标
请创建一个完整的单页面Web应用（index.html），用于分析直播公屏CSV数据。

## ⚡ 重要说明
1. **单文件要求**：所有代码必须写在 index.html 中
2. **纯前端实现**：不需要任何后端服务
3. **部署目标**：GitHub Pages
4. **测试数据**：请使用 test_data.csv 进行测试

## 📋 必须实现的核心功能

### 1. CSV数据导入
```javascript
// CSV格式示例
时间,用户ID,用户昵称,平台,发言内容,是否机器人
2025-01-20 19:00:01,u001,张三,抖音,老师好,0
2025-01-20 19:00:05,u002,李四,抖音,刚刚分享了直播间,0
2025-01-20 19:00:10,bot001,助教小美,抖音,欢迎大家,1
```
- 支持拖拽上传和点击上传
- 自动识别数据起始行
- 文件大小限制2MB
- 支持10000条数据

### 2. 数据筛选（必须实现）
- [ ] 过滤机器人消息（是否机器人=1）
- [ ] 分离助教/老师消息到独立时间轴
- [ ] 分离"刚刚分享了直播间"到独立时间轴
- [ ] 搜索框实时筛选
- [ ] 自定义关键词高亮

### 3. 三层时间轴展示
```
主时间轴（紫色）：普通用户消息
助教时间轴（橙色）：助教/老师消息
分享时间轴（绿色）：分享消息
```
- 横向展示，支持4小时
- 缩放50%-300%
- 拖拽移动
- 时间粒度：30秒/1分钟/2分钟/5分钟
- 高峰标记（>5条消息显示红色脉冲）

### 4. 数据分析图表（使用Canvas）
1. **互动趋势图**：柱状图，渐变色 #667eea → #764ba2
2. **词云图**：N-Gram分词，5级字体
3. **用户排行榜**：Top 10活跃用户
4. **情感分析**：积极/中性/消极饼图

### 5. 统计卡片
显示：有效消息数、活跃用户数、助教互动次数、分享次数、高峰时段、平均每分钟消息数

### 6. 导出功能
- 导出为PNG高清图片
- 使用纯Canvas实现（无需外部API）
- 分辨率：1920×1080或更高

## 🎨 UI设计要求

### 配色方案
- 主色：#667eea → #764ba2（紫色渐变）
- 助教：#f97316（橙色）
- 分享：#10b981（绿色）
- 高峰：#ef4444（红色）
- 背景：#f8f9fa

### 布局结构
```html
<body>
  <!-- 顶部：标题和统计卡片 -->
  <header>
    <h1>直播公屏时间轴分析系统</h1>
    <div class="stats-cards">...</div>
  </header>
  
  <!-- 控制区：上传和筛选 -->
  <section class="controls">
    <div class="upload-area">...</div>
    <div class="filters">...</div>
  </section>
  
  <!-- 时间轴区域 -->
  <section class="timelines">
    <div class="main-timeline">...</div>
    <div class="teacher-timeline">...</div>
    <div class="share-timeline">...</div>
  </section>
  
  <!-- 分析图表 -->
  <section class="charts">
    <div class="tabs">...</div>
    <canvas id="chart-canvas">...</canvas>
  </section>
  
  <!-- 导出按钮 -->
  <button class="export-btn">导出为图片</button>
</body>
```

## 💻 技术实现要求

### 必须使用的技术
1. **样式**：Tailwind CSS (CDN)
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```

2. **Canvas绘图**：原生Canvas API
3. **DOM操作**：原生JavaScript
4. **ES6+语法**：使用现代JavaScript特性

### 代码组织结构
```javascript
// 1. 数据处理模块
class DataProcessor {
  parseCSV(text) {}
  filterData(data, filters) {}
  aggregateByTime(data, granularity) {}
}

// 2. 时间轴渲染模块
class TimelineRenderer {
  render(data, container) {}
  handleZoom(scale) {}
  handleDrag(offset) {}
}

// 3. 图表绘制模块
class ChartRenderer {
  drawBarChart(canvas, data) {}
  drawWordCloud(canvas, words) {}
  drawPieChart(canvas, data) {}
}

// 4. 导出模块
class ExportManager {
  exportToPNG() {}
}

// 5. 主应用控制器
class App {
  init() {}
  handleFileUpload(file) {}
  updateView() {}
}
```

## 🐛 错误处理
1. CSV格式错误：友好提示缺少的列
2. 文件过大：提示文件大小限制
3. 空数据：显示"暂无数据"提示
4. 编码问题：提醒使用UTF-8

## ✅ 完成标准
1. 可以正确解析test_data.csv
2. 三层时间轴正常显示
3. 筛选功能全部可用
4. 四种图表都能切换显示
5. 导出功能生成高清PNG
6. 响应速度快（10000条数据3秒内处理完）

## 🚀 自动化测试建议
完成后请自动执行以下测试：
1. 上传test_data.csv查看是否正常解析
2. 测试所有筛选条件
3. 切换所有图表类型
4. 测试导出功能
5. 检查移动端显示

## 📝 附加说明
- 请添加适当的注释
- 使用语义化的变量名
- 处理边界情况
- 优化性能（使用requestAnimationFrame等）
- 添加加载动画和过渡效果

---

**开始开发吧！请创建一个完整的 index.html 文件，包含所有功能。**
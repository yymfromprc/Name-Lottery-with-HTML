# 🎰 Name Lottery - 华丽赌场风格姓名抽签系统

一个精美的HTML5单文件姓名抽签应用，采用豪华赌场老虎机风格设计，支持CSV文件导入和无重复抽签功能。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=flat&logo=javascript&logoColor=%23F7DF1E)

## ✨ 特性

- 🎨 **华丽视觉效果**：黄铜金色主题，深红天鹅绒背景，Marquee闪烁灯泡
- 🎯 **智能抽签**：自动防止重复抽取，支持无重复模式
- 📁 **灵活数据导入**：支持CSV文件上传，可自定义姓名所在列数
- 📊 **历史记录**：实时记录所有抽取历史，支持一键清除
- 🎭 **精美动画**：老虎机转轮动画，2秒渐进式停止效果
- 💎 **透明水晶球拉杆**：高度还原真实赌场老虎机体验
- 📦 **单文件应用**：无需安装，双击即用，易于分享
- 🌐 **离线运行**：无外部依赖，完全本地运行

## 🚀 快速开始

### 安装

无需安装！直接下载 `name_lottery.html` 文件即可使用。

```bash
# 克隆仓库
git clone https://github.com/yourusername/name-lottery.git

# 进入目录
cd name-lottery

# 在浏览器中打开
open name_lottery.html  # macOS
start name_lottery.html # Windows
xdg-open name_lottery.html # Linux
```

### 使用方法

1. **准备CSV文件**

   创建一个CSV文件，姓名可以在任意列：
   ```csv
   张三,班级A,18
   李四,班级B,19
   王五,班级C,20
   ```

   或者：
   ```csv
   001,张三,班级A
   002,李四,班级B
   003,王五,班级C
   ```

2. **上传CSV文件**
   - 在浏览器中打开 `name_lottery.html`
   - 如果姓名不在第一列，调整"姓名所在列数"输入框（从1开始）
   - 点击或拖拽上传CSV文件
   - 确认显示"✅ 已加载 X 个姓名"

3. **开始抽签**
   - 点击"开始抽签"按钮进入抽签页面
   - 点击透明水晶球拉杆开始抽签
   - 观看华丽的老虎机动画（2秒）
   - 查看左侧历史记录看板

4. **管理历史**
   - 已抽中的姓名会显示在左侧看板
   - 点击"清除记录"可重新开始
   - 点击右上角"返回"按钮返回上传页面（保留CSV数据）

## 🎬 界面预览

### 主要功能

- **上传页面**：简洁的CSV文件上传界面，支持拖拽和列数自定义
- **抽签页面**：6个金色转轮，透明水晶球拉杆，圆形Marquee灯泡
- **历史记录**：实时显示所有抽取记录，带序号和滚动条
- **动画效果**：星光背景、灯泡闪烁、转轮旋转、停止闪光

### 视觉特点

- 🎨 黄铜金色主色调 (#daa520, #b8860b)
- 🎪 深红褐色天鹅绒背景
- 💡 闪烁的圆形Marquee灯泡
- 💎 透明水晶球头拉杆（带蓝色光晕）
- ✨ 红宝石装饰点缀
- 🌟 暖色调星光粒子效果

## 🔧 技术栈

- **HTML5**：语义化结构
- **CSS3**：渐变、阴影、动画、3D变换
- **Vanilla JavaScript**：无框架依赖，纯原生JS

## 📋 核心功能详解

### 无重复抽签

系统自动跟踪已抽取的姓名，确保每个人只被抽中一次：

```javascript
// 核心算法
const availableNames = nameList.filter(name => !selectedHistory.includes(name));

// 特性：
// - 只从未抽中的姓名中选择
// - 已抽中的姓名自动排除
// - 全部抽完后提示用户清除记录
```

### 灵活的CSV列选择

支持从CSV的任意列提取姓名：

```javascript
const columnNumber = parseInt(columnInput.value) || 1;
const columnIndex = columnNumber - 1; // 转换为0-based索引
```

### 动画系统

精心设计的多层动画效果：

```css
/* 转轮旋转 */
animation: spin 0.1s linear infinite;

/* 灯泡闪烁 */
animation: bulb-glow 1.5s infinite;

/* 星光闪烁 */
animation: twinkle 3s infinite;
```

## 📊 项目结构

```
name-lottery/
├── name_lottery.html      # 主应用文件（包含HTML+CSS+JS）
├── DEVELOPMENT_LOG.md     # 详细开发日志
└── README.md              # 项目说明（本文件）
```

## 🎯 使用场景

- 📚 课堂随机提问抽签
- 🎉 活动幸运观众抽取
- 🏆 抽奖活动名单选择
- 👥 团队任务随机分配
- 🎲 游戏玩家随机选择
- 🎪 年会抽奖活动

## 💡 设计理念

### 视觉设计
- **豪华赌场风格**：营造高端、奢华的抽签氛围
- **黄铜金色主调**：传达尊贵、正式的感觉
- **动态光效**：增强视觉冲击力和仪式感
- **3D质感**：提升真实感和沉浸感

### 交互设计
- **直观操作**：拖拽上传、点击拉杆
- **即时反馈**：实时显示状态和结果
- **防误操作**：禁用重复点击、全部抽完提示
- **流畅动画**：2秒抽签动画营造期待感

### 用户体验
- **零门槛**：双击即用，无需安装配置
- **易分享**：单文件传输方便
- **容错性**：支持多种CSV格式
- **灵活性**：可自定义列数

## 📝 已知限制

1. **CSV格式**：仅支持标准逗号分隔格式
2. **姓名长度**：最多支持6个字符（6个转轮）
3. **文件大小**：建议CSV文件小于1MB
4. **浏览器兼容**：需要支持ES6+的现代浏览器

## 🚧 未来改进方向

### 功能增强
- [ ] 支持批量抽取（一次抽多个）
- [ ] 添加导出历史记录功能
- [ ] 支持自定义抽签音效
- [ ] 添加主题切换（多种风格）
- [ ] 支持Excel文件导入

### 技术优化
- [ ] 添加PWA支持（离线缓存）
- [ ] 优化移动端适配
- [ ] 添加打印友好样式
- [ ] 支持更多CSV格式（TSV、SSV等）

### 视觉增强
- [ ] 添加更多特效选项
- [ ] 可自定义配色方案
- [ ] 添加全屏模式
- [ ] 支持背景图片/视频

## 🤝 贡献

欢迎提交Issue和Pull Request！

1. Fork本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启Pull Request

## 📄 许可证

本项目采用MIT许可证 - 详见 [LICENSE](LICENSE) 文件

## 🙏 致谢

- 感谢所有使用和反馈的用户
- 设计灵感来源于经典赌场老虎机
- 开发工具：Claude Code + Claude Sonnet 4.5

## 📞 联系方式

如有问题或建议，欢迎通过以下方式联系：

- 提交Issue：[GitHub Issues](https://github.com/yourusername/name-lottery/issues)
- 邮箱：your.email@example.com

---

**开发完成日期**：2026年1月27日
**版本**：v2.0.0
**代码行数**：约1000行（HTML+CSS+JS合计）

⭐ 如果这个项目对你有帮助，请给个Star支持一下！

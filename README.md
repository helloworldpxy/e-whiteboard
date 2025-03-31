# e-whiteboard

基于HTML5 Canvas实现的电子白板应用，支持多种绘图工具和多画布管理。

## 功能特性

### 绘图工具
- ✎ 普通笔（支持自定义颜色和粗细）
- 🖍️ 荧光笔（半透明效果）
- 🧹 橡皮擦（带实时尺寸预览）
- 🎚️ 笔画粗细调节（1-50px）
- 🎨 颜色选择器

### 画布管理
- ➕ 创建新画布
- 🔄 切换不同画布
- ❌ 删除当前画布
- 🔍 支持Ctrl+滚轮缩放画布
- 🖱️ 画布拖拽查看（待实现）

### 其他功能
- 🚀 带使用说明的启动页面
- 📱 自适应窗口尺寸
- ⚡ 实时绘制预览
- 💾 绘图数据内存存储

## 使用说明

### 快速开始
1. 直接双击打开`index.html`
2. 点击"开始使用"关闭启动页
3. 选择工具开始绘制

### 快捷键
| 操作              | 快捷键            |
|-------------------|-------------------|
| 放大/缩小         | Ctrl + 鼠标滚轮   |
| 切换工具          | 点击工具栏按钮    |
| 新建画布          | 点击"新建画布"    |
| 删除当前画布      | 点击"删除画布"    |

## 技术实现

### 核心技术
- HTML5 Canvas
- CSS3 弹性布局
- Vanilla JavaScript

### 关键特性
1. **绘图系统**：
   - 基于路径记录的绘制方式
   - 使用`globalCompositeOperation`实现橡皮擦
   - 实时绘制与数据持久化分离

2. **状态管理**：
   ```javascript
   class CanvasState {
       constructor() {
           this.id = Date.now();
           this.data = [];  // 存储绘图操作
           this.zoom = 1;    // 当前缩放级别
           this.offsetX = 0; // 画布偏移量X
           this.offsetY = 0; // 画布偏移量Y
       }
   }
   ```

## 安装与运行

### 环境要求
- 现代浏览器（Chrome 80+/Firefox 75+/Edge 80+）
- 不需要服务器环境

### 使用方式
1. 直接运行：
```bash
git clone https://github.com/helloworldpxy/e-whiteboard.git
cd e-whiteboard && open e-whiteboard.html
```
2. 服务器运行：
```bash
python3 -m http.server 8000
# 访问 http://localhost:8000
```

## 许可证
本项目采用 MIT协议 开源
完整协议内容请查看项目根目录下的 LICENSE 文件。

## 注意事项
1. 当前版本数据存储在内存中，刷新页面会丢失数据
2. 建议在最新版本浏览器下使用
3. 橡皮擦实际作用范围为圆形区域

欢迎提交 Issue 或 PR 参与贡献！

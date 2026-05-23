# Fall Cake

> 下落蛋糕粒子效果库 - 创建优雅的漂浮粒子动画

## 特性

- 导入HTML页面即用
- 流畅的 CSS 动画
- 内置多种参数可供自定义
- 零依赖（纯 JavaScript）

## 安装

### 方式一：CDN 引入（推荐）

```html
<script src="https://unpkg.com/fall-cake/dist/fall-cake.min.js"></script>
```

或使用 jsDelivr:

```html
<script src="https://cdn.jsdelivr.net/npm/fall-cake/dist/fall-cake.min.js"></script>
```

### 方式二：npm 安装

```bash
npm install fall-cake
```

```javascript
const FallCake = require('fall-cake');
```

## 快速开始

### 基础用法

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Birthday Page</title>
    <style>
        body {
            margin: 0;
            background: #050510;
            min-height: 100vh;
        }
    </style>
</head>
<body>
    <!-- 页面内容 -->
    <h1>Happy Birthday!</h1>
    
    <!-- 引入 Fall Cake -->
    <script src="https://unpkg.com/fall-cake/dist/fall-cake.min.js"></script>
    
    <script>
        // 创建漂浮粒子效果
        const fallCake = new FallCake(document.body);
    </script>
</body>
</html>
```

## 配置选项

| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `particleCount` | number | `18` | 初始粒子数量 |
| `particleInterval` | number | `850` | 粒子生成间隔（毫秒） |
| `particleLifespan` | number | `22000` | 粒子存活时间（毫秒） |

## 示例

### 基础示例

```javascript
const fallCake = new FallCake(document.body);
```

### 自定义配置

```javascript
const fallCake = new FallCake(document.body, {
    particleCount: 30,        // 更多粒子
    particleInterval: 500,    // 更快的生成速度
    particleLifespan: 30000   // 更长的存活时间
});
```

### 页面加载时启动

```javascript
window.addEventListener('load', () => {
    const fallCake = new FallCake(document.body);
});
```

## 方法

### `stop()`

停止生成新的粒子。

```javascript
const fallCake = new FallCake(document.body);

// 5秒后停止生成粒子
setTimeout(() => {
    fallCake.stop();
}, 5000);
```

### `restart()`

重新开始生成粒子。

```javascript
const fallCake = new FallCake(document.body);
fallCake.stop();
fallCake.restart();
```

### `destroy()`

销毁实例，完全移除粒子层。

```javascript
const fallCake = new FallCake(document.body);
// 页面切换时销毁
fallCake.destroy();
```

## 效果说明

粒子会：
1. 从屏幕顶部以随机位置生成
2. 缓慢下落同时旋转
3. 带有随机大小（24px - 114px）
4. 带有随机透明度（0.08 - 0.26）
5. 持续循环生成

## 开发

```bash
# 克隆仓库
git clone https://github.com/VignaChu/fall-cake.git
cd fall-cake

# 安装依赖
npm install

# 查看示例
npm run demo
```

## 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

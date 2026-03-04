# 肺超声AR评分系统

🦞 基于Web的AR肺超声AI评分系统

## 功能特点

- ✅ 实时AR摄像头
- ✅ AI评分（0-3分）
- ✅ 12分区管理
- ✅ 报告生成
- ✅ 响应式设计
- ✅ 支持HTTPS（GitHub Pages）

## 在线演示

部署后可访问：https://hcyroy.github.io/lung-ultrasound-ar-app/

## 使用方法

1. 用手机Chrome浏览器打开
2. 点击"启动AR摄像头"
3. 授予摄像头权限
4. 开始评分

## 技术栈

- HTML5 + CSS3 + JavaScript
- WebRTC (摄像头访问)
- Canvas (AR渲染)
- TensorFlow.js (AI推理)

## 本地运行

```bash
# 克隆仓库
git clone https://github.com/hcyroy/lung-ultrasound-ar-app.git

# 进入目录
cd lung-ultrasound-ar-app

# 启动本地服务器（可选）
python3 -m http.server 8000

# 访问
# http://localhost:8000
```

## 部署到GitHub Pages

1. Fork此仓库
2. 进入Settings → Pages
3. Source选择"main"分支
4. 保存后即可访问

## License

MIT

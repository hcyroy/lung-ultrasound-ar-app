# 肺超声AI评分系统

> **高原肺前瞻项目 - AI辅助肺超声评分解决方案**

## 🦞 系统简介

基于 TensorFlow ResNet50 的肺超声实时AI评分系统，支持12分区评分和完整报告生成。

## 📦 版本说明

### 1. 模拟版本（离线可用）
- **文件**: `index.html`
- **特点**: 纯前端，无需服务器
- **适用**: 演示、测试、离线使用
- **限制**: 使用模拟评分，非真实AI

### 2. 真实AI版本（推荐）⭐
- **文件**: `index-real-ai.html`
- **特点**: 真实AI分析，ResNet50模型
- **适用**: 实际临床应用
- **要求**: 需要后端API服务

## 🚀 快速开始

### 方式1: GitHub Pages（模拟版）
直接访问：[https://hcyroy.github.io/lung-ultrasound-ar-app/](https://hcyroy.github.io/lung-ultrasound-ar-app/)

### 方式2: 真实AI版（需API服务）

#### 步骤1: 启动API服务
```bash
# 在服务器上
cd lung-ultrasound-ai
python3 api_server.py
```

#### 步骤2: 访问前端
```
http://服务器IP:8080/index-real-ai.html
```

## 🏗️ 系统架构

```
┌──────────────────┐         ┌──────────────────┐
│   前端网页        │  HTTP   │   Flask API      │
│ (index-real-ai)  │◄───────►│ (api_server.py)  │
│                  │         │                  │
│  浏览器摄像头    │         │  TensorFlow      │
│  图像采集        │         │  ResNet50        │
└──────────────────┘         └──────────────────┘
```

## 📊 功能特性

| 功能 | 模拟版 | 真实AI版 |
|------|-------|----------|
| 实时摄像头 | ✅ | ✅ |
| AI评分 | 🟡 模拟 | ✅ 真实 |
| 12分区评分 | ✅ | ✅ |
| 报告生成 | ✅ | ✅ |
| 离线使用 | ✅ | ❌ |
| 准确性 | 低 | 高 |

## 🎯 使用流程

1. **打开网页** → 等待API连接
2. **点击"开始"** → 启动摄像头
3. **对准图像** → 点击"评分"
4. **查看结果** → AI返回评分和置信度
5. **切换分区** → 完成12个分区
6. **生成报告** → 查看完整评分报告

## 📡 API接口

### 健康检查
```
GET /api/health
```

### 单张预测
```
POST /api/predict
{
  "image": "base64编码的图像",
  "zone": "RUL-PS"
}
```

## 🔧 技术栈

- **前端**: HTML5, CSS3, JavaScript
- **后端**: Python, Flask
- **AI框架**: TensorFlow 2.x
- **模型**: ResNet50V2 (ImageNet预训练)

## 📂 项目结构

```
lung-ultrasound-ar-app/
├── index.html              # 模拟版前端
├── index-real-ai.html      # 真实AI版前端
├── README.md               # 本文件
└── .git/

lung-ultrasound-ai/         # 后端API（需单独部署）
├── api_server.py           # Flask API服务
├── src/
│   └── model.py            # AI模型代码
└── requirements.txt        # Python依赖
```

## 🌐 部署说明

### GitHub Pages（前端）
1. 推送代码到 GitHub
2. 启用 GitHub Pages
3. 访问 `https://用户名.github.io/仓库名/`

### API服务（后端）
```bash
# 安装依赖
pip install tensorflow flask flask-cors numpy opencv-python

# 启动服务
python3 api_server.py

# 后台运行
nohup python3 api_server.py > /tmp/api.log 2>&1 &
```

## ⚠️ 注意事项

1. **首次运行**: 模型会自动下载 ResNet50 权重（91MB）
2. **摄像头权限**: 需要浏览器授权
3. **HTTPS**: 生产环境建议使用 HTTPS
4. **性能**: CPU 可用，GPU 更快

## 📊 评分标准

| 分数 | 含义 | 描述 |
|------|------|------|
| 0 | 正常 | A线，肺滑动 |
| 1 | 轻度 | 离散B线（≥3条） |
| 2 | 中度 | 融合B线 |
| 3 | 重度 | 实变 |

**总分**: 0-36分
- 0-5: 正常或轻微
- 6-12: 轻度
- 13-20: 中度
- 21-36: 重度

## 🔄 更新日志

### v2.0 (2026-03-05)
- ✅ 添加真实AI版本
- ✅ ResNet50V2 模型支持
- ✅ Flask API 后端
- ✅ 完善报告功能

### v1.0 (2026-03-04)
- ✅ 初始版本
- ✅ 模拟评分功能
- ✅ 12分区支持

## 📞 技术支持

- **GitHub**: [hcyroy/lung-ultrasound-ar-app](https://github.com/hcyroy/lung-ultrasound-ar-app)
- **文档**: 查看 `docs/` 目录
- **问题反馈**: GitHub Issues

## 📜 许可证

MIT License

---

**高原肺前瞻研究项目组**
**2026年3月**

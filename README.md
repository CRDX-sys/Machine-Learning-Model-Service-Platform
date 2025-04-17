# ML Model Serving Platform

[![Python](https://img.shields.io/badge/Python-3.9+-blue)]()
[![FastAPI](https://img.shields.io/badge/FastAPI-0.85+-green)]()
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)]()

机器学习模型服务化平台，支持：
- 多模型并行服务
- 自动版本控制
- 性能监控
- A/B测试

## 核心功能

✨ 模型热加载  
✨ 自动扩缩容  
✨ 请求批处理  
✨ 模型性能分析  
✨ 灰度发布  

## 安装

### 使用Docker

```bash
docker-compose up --build
```

### 本地开发

1. 创建虚拟环境
```bash
python -m venv venv
source venv/bin/activate
```

2. 安装依赖
```bash
pip install -r requirements.txt
```

3. 启动服务
```bash
uvicorn app.main:app --reload
```

## API文档

访问 `http://localhost:8000/docs` 查看交互式API文档

## 模型部署示例

```python
from app.models.model_manager import ModelManager

manager = ModelManager()
manager.load_model(
    model_name="sentiment-analysis",
    version="1.0",
    path="models/sentiment/v1"
)
```

## 监控指标

平台暴露Prometheus指标端点：
```
GET /metrics
```

## 贡献

请阅读[贡献指南](CONTRIBUTING.md)后提交PR

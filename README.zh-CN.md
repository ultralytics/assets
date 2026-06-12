<a href="https://www.ultralytics.com/"><img src="https://raw.githubusercontent.com/ultralytics/assets/main/logo/Ultralytics_Logotype_Original.svg" width="320" alt="Ultralytics 标志"></a>

# Ultralytics Assets

[English](README.md) | [简体中文](README.zh-CN.md)

本仓库存放 Ultralytics 在文档、应用、示例、发布和模型下载中共用的资源文件。它为 Ultralytics YOLO 生态提供稳定文件，覆盖[目标检测](https://docs.ultralytics.com/tasks/detect)、[实例分割](https://docs.ultralytics.com/tasks/segment)、[图像分类](https://docs.ultralytics.com/tasks/classify)、[姿态估计](https://docs.ultralytics.com/tasks/pose)和[目标跟踪](https://docs.ultralytics.com/modes/track)等任务。

[![Ultralytics Actions](https://github.com/ultralytics/assets/actions/workflows/format.yml/badge.svg)](https://github.com/ultralytics/assets/actions/workflows/format.yml)
[![Ultralytics Discord](https://img.shields.io/discord/1089800235347353640?logo=discord&logoColor=white&label=Discord&color=blue)](https://discord.com/invite/ultralytics)
[![Ultralytics Forums](https://img.shields.io/discourse/users?server=https%3A%2F%2Fcommunity.ultralytics.com&logo=discourse&label=Forums&color=blue)](https://community.ultralytics.com/)
[![Ultralytics Reddit](https://img.shields.io/reddit/subreddit-subscribers/ultralytics?style=flat&logo=reddit&logoColor=white&label=Reddit&color=blue)](https://reddit.com/r/ultralytics)

## 包含内容

- **视觉资源**：标志、网站图标、社交图标、Open Graph 图片、截图、图表和横幅。
- **模型资源**：当本地不存在所需模型时，Ultralytics 工具会自动下载的预训练模型文件。
- **数据集资源**：Ultralytics 文档和教程引用的数据集发布文件和示例。

## 使用资源

在文档、Notebook、网站或示例中引用资源时，建议使用 raw GitHub URL：

```text
https://raw.githubusercontent.com/ultralytics/assets/main/path/to/asset.ext
```

例如，上方使用的 Ultralytics 标志位于：

```text
https://raw.githubusercontent.com/ultralytics/assets/main/logo/Ultralytics_Logotype_Original.svg
```

## 使用预训练模型

当本地找不到请求的模型时，Ultralytics YOLO 库会自动从本仓库下载支持的预训练模型。

```python
from ultralytics import YOLO

model = YOLO("yolo26n.pt")
results = model("path/to/image.jpg")
```

可在 [Ultralytics 模型文档](https://docs.ultralytics.com/models)中查看可用模型系列、任务和导出选项。

## 数据集

数据集文件通过仓库 Releases 发布，并在 [Ultralytics 数据集文档](https://docs.ultralytics.com/datasets)中引用。在项目中使用数据集前，请先查看对应的 README、许可证和使用说明。

## 仓库结构

- `app/`：应用商店徽章、截图和引导页视觉资源。
- `blog/`、`og/` 和 `partners/`：博客、Open Graph 和合作伙伴媒体资源。
- `docs/`：文档图片、图表、截图、音频和媒体。
- `im/`：推理和文档示例使用的示例图片。
- `logo/`：Ultralytics 标志、字标和网站图标资源。
- `mkdocs/`：Ultralytics 文档构建使用的资源。
- `social/`：Ultralytics 各仓库使用的社交媒体图标。
- `yolo/`、`yolov3/`、`yolov5/` 和 `yolov8/`：YOLO 系列横幅、图表和示例资源。

## 贡献

欢迎提交能提升资源质量、准确性、组织方式或文档说明的贡献。打开 Pull Request 前，请先阅读[贡献指南](https://docs.ultralytics.com/help/contributing)。如需提供产品反馈，请使用 [Ultralytics 调查问卷](https://www.ultralytics.com/survey?utm_source=github&utm_medium=social&utm_campaign=Survey)。

[![Ultralytics 开源贡献者](https://raw.githubusercontent.com/ultralytics/assets/main/im/image-contributors.png)](https://github.com/ultralytics/ultralytics/graphs/contributors)

## 许可证

Ultralytics 提供两种许可方式：

- **AGPL-3.0 许可证**：经 [OSI 批准](https://opensource.org/license/agpl-3.0)的开源许可证，适用于开放协作和知识共享。详情请参阅 [LICENSE](LICENSE) 文件。
- **企业许可证**：商业许可证，允许在商业产品中集成 Ultralytics 软件和 AI 模型，而无需遵循 AGPL-3.0 的开源要求。详情请联系 [Ultralytics Licensing](https://www.ultralytics.com/license)。

## 联系方式

如需报告 bug、提交功能请求或贡献内容，请使用 [GitHub Issues](https://github.com/ultralytics/assets/issues)。如需提问或参与讨论，请加入 Ultralytics [Discord](https://discord.com/invite/ultralytics) 社区。

<br>
<div align="center">
  <a href="https://github.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-github.png" width="3%" alt="Ultralytics GitHub"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.linkedin.com/company/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-linkedin.png" width="3%" alt="Ultralytics LinkedIn"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://twitter.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-twitter.png" width="3%" alt="Ultralytics Twitter"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.youtube.com/ultralytics?sub_confirmation=1"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-youtube.png" width="3%" alt="Ultralytics YouTube"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.tiktok.com/@ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-tiktok.png" width="3%" alt="Ultralytics TikTok"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://ultralytics.com/bilibili"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-bilibili.png" width="3%" alt="Ultralytics BiliBili"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://discord.com/invite/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-discord.png" width="3%" alt="Ultralytics Discord"></a>
</div>

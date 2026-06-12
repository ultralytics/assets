<a href="https://www.ultralytics.com/"><img src="https://raw.githubusercontent.com/ultralytics/assets/main/logo/Ultralytics_Logotype_Original.svg" width="320" alt="Ultralytics logo"></a>

# Ultralytics Assets

[English](README.md) | [简体中文](README.zh-CN.md)

This repository stores shared Ultralytics assets used across documentation, applications, examples, releases, and model downloads. It provides stable files for the Ultralytics YOLO ecosystem, including [object detection](https://docs.ultralytics.com/tasks/detect), [instance segmentation](https://docs.ultralytics.com/tasks/segment), [classification](https://docs.ultralytics.com/tasks/classify), [pose estimation](https://docs.ultralytics.com/tasks/pose), and [tracking](https://docs.ultralytics.com/modes/track).

[![Ultralytics Actions](https://github.com/ultralytics/assets/actions/workflows/format.yml/badge.svg)](https://github.com/ultralytics/assets/actions/workflows/format.yml)
[![Ultralytics Discord](https://img.shields.io/discord/1089800235347353640?logo=discord&logoColor=white&label=Discord&color=blue)](https://discord.com/invite/ultralytics)
[![Ultralytics Forums](https://img.shields.io/discourse/users?server=https%3A%2F%2Fcommunity.ultralytics.com&logo=discourse&label=Forums&color=blue)](https://community.ultralytics.com/)
[![Ultralytics Reddit](https://img.shields.io/reddit/subreddit-subscribers/ultralytics?style=flat&logo=reddit&logoColor=white&label=Reddit&color=blue)](https://reddit.com/r/ultralytics)

## What Is Included

- **Visual assets**: logos, favicons, social icons, Open Graph images, screenshots, diagrams, and banners.
- **Model assets**: pretrained model files downloaded automatically by Ultralytics tools when they are not already available locally.
- **Dataset assets**: dataset release artifacts and examples referenced by Ultralytics documentation and tutorials.

## Using Assets

Use raw GitHub URLs when referencing assets from documentation, notebooks, websites, or examples:

```text
https://raw.githubusercontent.com/ultralytics/assets/main/path/to/asset.ext
```

For example, the Ultralytics logo above is available at:

```text
https://raw.githubusercontent.com/ultralytics/assets/main/logo/Ultralytics_Logotype_Original.svg
```

## Using Pretrained Models

Ultralytics YOLO libraries download supported pretrained models from this repository automatically when the requested model is not found locally.

```python
from ultralytics import YOLO

model = YOLO("yolo26n.pt")
results = model("path/to/image.jpg")
```

See the [Ultralytics model documentation](https://docs.ultralytics.com/models) for available model families, tasks, and export options.

## Datasets

Dataset artifacts are published through repository releases and referenced from the [Ultralytics datasets documentation](https://docs.ultralytics.com/datasets). Review the README, license, and usage notes for each dataset before using it in a project.

## Repository Layout

- `app/`: App store badges, screenshots, and onboarding visuals.
- `blog/`, `og/`, and `partners/`: Blog, Open Graph, and partner media.
- `docs/`: Documentation images, diagrams, screenshots, audio, and media.
- `im/`: Sample images used in inference and documentation examples.
- `logo/`: Ultralytics logos, logotypes, and favicon assets.
- `mkdocs/`: Assets used by Ultralytics documentation builds.
- `social/`: Social media icons used across Ultralytics repositories.
- `yolo/`, `yolov3/`, `yolov5/`, and `yolov8/`: YOLO-family banners, diagrams, and example assets.

## Contributing

Contributions are welcome when they improve asset quality, accuracy, organization, or documentation. Please read the [Contributing Guide](https://docs.ultralytics.com/help/contributing) before opening a pull request. For product feedback, use the [Ultralytics Survey](https://www.ultralytics.com/survey?utm_source=github&utm_medium=social&utm_campaign=Survey).

[![Ultralytics open-source contributors](https://raw.githubusercontent.com/ultralytics/assets/main/im/image-contributors.png)](https://github.com/ultralytics/ultralytics/graphs/contributors)

## License

Ultralytics offers two licensing options:

- **AGPL-3.0 License**: An [OSI-approved](https://opensource.org/license/agpl-3.0) open-source license for open collaboration and knowledge sharing. See the [LICENSE](LICENSE) file for details.
- **Enterprise License**: A commercial license for integrating Ultralytics software and AI models into commercial products without AGPL-3.0 requirements. Contact [Ultralytics Licensing](https://www.ultralytics.com/license) for details.

## Contact

For bug reports, feature requests, and contributions, use [GitHub Issues](https://github.com/ultralytics/assets/issues). For questions and discussions, join the Ultralytics community on [Discord](https://discord.com/invite/ultralytics).

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

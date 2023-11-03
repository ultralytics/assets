<div align="center">
  <p>
    <a href="https://ultralytics.com/" target="_blank">
      <img width="100%" src="https://raw.githubusercontent.com/ultralytics/assets/main/im/banner-yolo-vision-2023.png"></a>
  </p>
<br>

<div align="center">
  <a href="https://github.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-github.png" width="3%" alt="Ultralytics GitHub"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://www.linkedin.com/company/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-linkedin.png" width="3%" alt="Ultralytics LinkedIn"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://twitter.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-twitter.png" width="3%" alt="Ultralytics Twitter"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://youtube.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-youtube.png" width="3%" alt="Ultralytics YouTube"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://www.tiktok.com/@ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-tiktok.png" width="3%" alt="Ultralytics TikTok"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://www.instagram.com/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-instagram.png" width="3%" alt="Ultralytics Instagram"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="2%">
  <a href="https://ultralytics.com/discord"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-discord.png" width="3%" alt="Ultralytics Discord"></a>
</div>
</div>

# 🌟 Ultralytics Assets Repository

## 📋 Overview

Welcome to the [Ultralytics](https://ultralytics.com) Assets repository! This repository serves as a storage for visual assets like banners, logos, and more importantly, pre-trained models and datasets. These assets are designed to work seamlessly with [Ultralytics YOLO](https://github.com/ultralytics/ultralytics) implementations, aiding in [object detection](https://docs.ultralytics.com/tasks/detect/), [instance segmentation](https://docs.ultralytics.com/tasks/segment/), [image classification](https://docs.ultralytics.com/tasks/classify/), [pose estimation](https://docs.ultralytics.com/tasks/pose/), and multi-object [tracking](https://docs.ultralytics.com/modes/track/).

## 🛠 Features

1. **🖼 Visual Assets**: Banners and logos to use in your projects or for showcasing your use of Ultralytics resources.
2. **🤖 Models**: Pre-trained models that are ready for download and immediate use. These models are optimized for various computer vision tasks.
3. **📦 Datasets**: Collections of annotated data that can be used for training or validating models.

## 💡 Usage

### 📥 Autodownload of Pretrained Models

When using Ultralytics YOLO APIs, if a pre-trained model is not found locally, it will be automatically downloaded from this repository.

Here's a simple example using Python:

```python
from ultralytics import YOLO

# Load a pretrained YOLOv8n model
model = YOLO('yolov8n.pt')

# Define path to the image file
source = 'path/to/image.jpg'

# Run inference on the source
results = model(source)  # Returns a list of Results objects
```

### 🌐 Accessing Visual Assets

The visual assets can be downloaded directly from the main branch of this repository. They are free for use in your own projects or documentation.

### 📚 Accessing Datasets

Datasets can be downloaded from the repository releases. Please refer to the individual dataset READMEs for usage instructions and licenses.

## 🤝 Contributing

If you'd like to contribute models, datasets, or visual assets to this repository, please submit a pull request or open an issue to discuss the contribution.

## 🆘 Support

For any questions, feature requests, or debugging queries, feel free to reach out to the Ultralytics support team or raise an issue on GitHub.

## 📝 License

This repository and its assets are covered under the GNU Affero General Public License v3.0 (AGPL-3.0). Please refer to the [LICENSE](./LICENSE) file for more details.

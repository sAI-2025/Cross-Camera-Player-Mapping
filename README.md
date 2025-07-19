
# 🎥 Cross-Camera Player Mapping

_*Efficient player matching across multiple camera feeds using deep learning and visual similarity modeling.*_

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10-blue?logo=python" />
  <img src="https://img.shields.io/badge/YOLO-Detection-orange?logo=opencv" />
  <img src="https://img.shields.io/badge/Siamese%20Network-PyTorch-9cf?logo=pytorch" />
  <img src="https://img.shields.io/badge/Similarity-Cosine%20Score-green?logo=scikitlearn" />
  <img src="https://img.shields.io/badge/License-MIT-green?logo=opensourceinitiative" />
  <img src="https://img.shields.io/badge/Status-Prototype-lightgrey?logo=github" />
</p>

---

## Problem Statement

Current player tracking systems using multiple cameras face challenges:

* **Inconsistent Player Identification**: Different camera angles lead to inconsistent player recognition.
* **Manual Intervention**: Cross-camera player matching often requires human effort.
* **Lack of Real-time Processing**: Automatic and accurate player matching is difficult in real-time applications.

---

## Our Solution

This project addresses the challenge of **cross-camera player mapping** using a **pretrained Siamese Network**. It enables:

* **Automatic Player Matching**: Identifies and matches players across multiple camera feeds.
* **Real-Time Processing**: Efficiently processes video frames for live applications.
* **High Accuracy**: Achieves high similarity scores in matching players based on appearance.

---

## How It Works: Step-by-Step

### 1. Video Input – Start with Multiple Camera Feeds

You provide two video inputs: one from a **broadcast camera** and the other from a **tacticam**. Both videos contain player interactions in the same game or event.

### 2. Player Detection – Detect Players Using YOLO

YOLO (You Only Look Once) is used to detect players within the video frames. The bounding boxes are extracted for each detected player in both camera feeds.

### 3. Feature Extraction – Extract Visual Features with Siamese Network

Each detected player is cropped out and passed to a **pretrained Siamese Network** for feature extraction. The network generates embeddings that represent the player’s appearance.

### 4. Player Matching – Compare Embeddings with Cosine Similarity

The embeddings of players from both cameras are compared using **cosine similarity**. A higher similarity score means the players are likely the same person, despite coming from different camera angles.

### 5. Optimal Matching – Use Hungarian Algorithm for Mapping

The Hungarian algorithm is applied to find the optimal matching of players between the two video feeds based on the similarity scores.

### 6. Output – Display Matched Players

The result is a list of player pairs indicating which players in the **broadcast video** correspond to players in the **tacticam video**.

---

## Project Structure

```bash
Cross-Camera-Player-Mapping/
|   code/
|   ├── titled.ipynb             # Jupyter notebook with implementation
|   ├── requirements.txt         # Python dependencies
└── README.md                 
```

---

## Quick Start Guide

### Prerequisites

Before you run the project, ensure you have the following installed:

```bash
# Required Software
- Python 3.10 or higher
- Git
- CUDA (optional, for GPU acceleration)
```

### Installation

Follow the steps below to set up the project:

```bash
# Clone the repository
git clone https://github.com/sAI-2025/Cross-Camera-Player-Mapping.git
cd Cross-Camera-Player-Mapping

# Install dependencies
pip install -r requirements.txt
```

---

## Key Technologies

| **Component**         | **Technology**            | **Purpose**                                   |
| --------------------- | ------------------------- | --------------------------------------------- |
| **Object Detection**  | YOLO (You Only Look Once) | Detecting players in video frames             |
| **Deep Learning**     | PyTorch (Siamese Network) | Feature extraction and similarity computation |
| **Optimization**      | Hungarian Algorithm       | Optimal player matching between frames        |
| **Similarity Metric** | Cosine Similarity         | Comparing player embeddings                   |

---

## Key Features

* **🔍 Real-Time Object Detection**: Uses YOLO for fast and efficient player detection.
* **🧠 Siamese Network**: Pretrained model to extract and compare player features.
* **⚡ Fast Processing**: Efficient player matching even in real-time scenarios.
* **📊 Performance Metrics**: High accuracy and minimal latency for player mapping.

---

## Testing the System

### Run the Jupyter Notebook

1. **Open Jupyter Notebook**:

   ```bash
   jupyter notebook titled.ipynb
   ```

2. **Execute all cells** to:

   * Load and process video data
   * Perform player detection and feature extraction
   * Run the player matching algorithm

### Sample Test: Player Matching

```python
# Initialize video inputs
video_broadcast = cv2.VideoCapture('broadcast_video.mp4')
video_tacticam = cv2.VideoCapture('tacticam_video.mp4')

# Initialize YOLO Model
yolo_model = YOLOModel()

# Initialize Siamese Network
siamese_model = SiameseNetwork()

# Run player matching function
match_players(video_broadcast, video_tacticam)
```

---

## Configuration

### Environment Variables

```bash
# Required
CUDA_VISIBLE_DEVICES=0  # Optional: GPU configuration

# Optional
VIDEO_BROADCAST_PATH=path/to/broadcast_video.mp4
VIDEO_TACTICAM_PATH=path/to/tacticam_video.mp4
```

---

## Contributing

We welcome contributions from the community! To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to your branch: `git push origin feature/new-feature`
5. Open a Pull Request

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Support & Contact

For further questions or support:
* **GitHub Issues**: [Report bugs or request features](https://github.com/sAI-2025/Cross-Camera-Player-Mapping/issues)
* **GitHub**: [sAI-2025](https://github.com/sAI-2025)
* **LinkedIn**: [linkedin/sai-krishna-chowdary-chundru](https://linkedin.com/in/sai-krishna-chowdary-chundru)
* Medium: [@sai2025](https://medium.com/@sai2025)

---

### Author: Sai Krishna Chowdary Chundru

**GitHub**: [git@sAI](https://github.com/sAI-2025)
* **Email**: \[cchsaikrishnachowdary@gmail.com]
**LinkedIn**: [sai-krishna-chowdary-chundru](https://linkedin.com/in/sai-krishna-chowdary-chundru)
**Medium**: [medium@sai](https://medium.com/@sai2025)

---

# Object Detection

## Overview

This project implements **real-time object detection** using a pre-trained **MobileNet SSD** model deployed via OpenCV's DNN module. It captures live video from a webcam, runs inference on each frame, and draws labeled bounding boxes around detected objects — all in a lightweight, dependency-minimal Python environment.

The solution is ideal for demonstrating on-device object detection without the overhead of a GPU or deep learning framework, leveraging the efficiency of MobileNet SSD optimized for embedded and real-time applications.

## Key Features

- 🎥 **Real-time webcam detection** — processes live video feed frame by frame
- 🔍 **20-class object recognition** — detects people, animals, vehicles, household items, and more
- 📦 **Pre-trained Caffe model** — no training required; plug-and-play inference
- 🎨 **Color-coded bounding boxes** — each class is assigned a unique random color for easy visualization
- ⚡ **Lightweight pipeline** — runs on CPU using OpenCV's optimized DNN backend
- 🛑 **Configurable confidence threshold** — filters out low-confidence detections

## Tech Stack

| Category    | Technology                        |
|-------------|-----------------------------------|
| Language    | Python 3.11                       |
| Framework   | OpenCV DNN                        |
| Libraries   | OpenCV (`cv2`), NumPy             |
| Model       | MobileNet SSD (Caffe)             |
| Interface   | Jupyter Notebook                  |
| Platform    | macOS / Linux / Windows           |

## Installation

### Prerequisites

- Python 3.8 or higher
- pip

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/vanix056/Object-Detection.git
cd Object-Detection

# 2. Install dependencies
pip install opencv-python numpy jupyter

# 3. Verify model files are present
ls models/
# Expected: MobileNetSSD_deploy.caffemodel  MobileNetSSD_deploy.prototxt.txt
```

## Usage

Launch the Jupyter Notebook and run the detection cell:

```bash
jupyter notebook main.ipynb
```

Then execute the first cell. A window titled **"Detected Objects"** will open showing the live webcam feed with bounding boxes and class labels.

- **Press `q`** to exit the detection loop and release the camera.

### Configuration

You can adjust the following variables at the top of the notebook cell:

| Variable         | Default | Description                                       |
|------------------|---------|---------------------------------------------------|
| `min_confidence` | `0.2`   | Minimum detection confidence (0.0 – 1.0)         |
| `prototxt_path`  | `models/MobileNetSSD_deploy.prototxt.txt` | Path to model architecture |
| `model_path`     | `models/MobileNetSSD_deploy.caffemodel`   | Path to pre-trained weights |

## Project Structure

```
Object-Detection/
├── models/
│   ├── MobileNetSSD_deploy.caffemodel       # Pre-trained MobileNet SSD weights
│   └── MobileNetSSD_deploy.prototxt.txt     # Model architecture definition
├── main.ipynb                               # Main detection notebook
├── image1.jpeg                              # Sample test image
├── image2.jpeg                              # Sample test image
├── image3.avif                              # Sample test image
├── image4.jpeg                              # Sample test image
└── README.md
```

## Model Architecture

| Property         | Detail                          |
|------------------|---------------------------------|
| Architecture     | MobileNet SSD (Single Shot Detector) |
| Framework        | Caffe                           |
| Input Size       | 300 × 300 pixels                |
| Preprocessing    | Mean subtraction (127.5), scale factor 0.007843 |
| Output           | Bounding box coordinates + class probabilities |

MobileNet SSD combines the MobileNet feature extractor with the SSD detection head, enabling fast single-pass object detection suitable for real-time applications on standard hardware.

## Dataset

The model is pre-trained on the **PASCAL VOC** dataset and detects the following 20 object classes:

`aeroplane` · `bicycle` · `bird` · `keyboard` · `bottle` · `bus` · `headphones` · `cat` · `chair` · `cow` · `diningtable` · `dog` · `horse` · `motorbike` · `person` · `sheep` · `bag` · `train` · `tv/laptop/mobile`

No additional dataset download is required for inference.

## Results

The model runs at interactive frame rates on CPU. Each detected object is annotated with:
- A color-coded bounding rectangle
- A label in the format `class_name: confidence%`

Sample input images are provided in the repository root (`image1.jpeg` – `image4.jpeg`).

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

Please ensure your code follows existing conventions and includes relevant comments.

## License

This project is licensed under the [MIT License](LICENSE).

## Author

**vanix056**  
GitHub: [@vanix056](https://github.com/vanix056)

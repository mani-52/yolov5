# Helmet and License Plate Detection using YOLOv5 🚧📸

This project implements a real-time object detection system to identify **helmets** and **license plates** using the YOLOv5 deep learning model. It is optimized for workplace safety monitoring and traffic surveillance, with live CCTV/RTSP feed compatibility.

## 🔧 Features

- Detects:
  - Helmets 🪖
  - License Plates 🚘
- Real-time video stream processing
- Trained on a custom dataset
- YOLOv5 lightweight model (Nano/Medium)
- TensorFlow-based UI (optional)
- RTSP integration for CCTV monitoring

---

## 🗂️ Project Structure
HelmetPlateDetection/
├── yolov5/ # YOLOv5 source code
├── datasets/
│ └── helmet_plate/
│ ├── images/ # Training and validation images
│ ├── labels/ # Corresponding YOLO format labels
│ └── data.yaml # Dataset configuration file
├── runs/ # Training results and saved models
├── detect.py # Script for inference
├── train.py # Training script
└── README.md # This file

---

## 🚀 Setup Instructions


```bash
### 1. Clone the Repo
git clone https://github.com/mani-52/yolov5.git
cd yolov5

### 2. Create a Virtual Environment
python -m venv .venv
.\.venv\Scripts\activate

### 3. Install Requirements
pip install -r requirements.txt

📊 Training the Model
Train with Custom Dataset
bash
Copy
Edit
python train.py --img 640 --batch 16 --epochs 100 --data ../datasets/helmet_plate/data.yaml \
--weights yolov5m.pt --name helmet_plate_model_optimized --cache --workers 2

Training Output
After training, results (metrics, weights) will be saved to:

bash
Copy
Edit
runs/train/helmet_plate_model_optimized/

🔎 Inference
To detect objects on an image or video:

bash
Copy
Edit
python detect.py --weights runs/train/helmet_plate_model_optimized/weights/best.pt \
--img 640 --conf 0.25 --source path/to/your/image_or_video.mp4

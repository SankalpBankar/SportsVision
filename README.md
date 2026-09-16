<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=header&text=SportsVision&fontSize=60&fontAlignY=35" />

<div align="center">

# 🏟️ SportsVision

### Human Action Recognition in Sports Videos using Hybrid Deep Learning

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=34D399&center=true&width=650&lines=Human+Action+Recognition;YOLOv8+Athlete+Detection;ResNet-50+Feature+Extraction;Bi-LSTM+Temporal+Modeling;Self-Attention+Classification)](https://git.io/typing-svg)

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-111F68?style=for-the-badge&logo=yolo&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)

*An AI-powered sports video analysis system that recognizes human actions using a hybrid deep learning pipeline.*

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" />

## 🎯 About

**SportsVision** is a Human Action Recognition system designed to identify sports-related actions from video clips.

The system combines **YOLOv8, ResNet-50, Bi-LSTM, and Self-Attention** to detect athletes, extract spatial features, understand temporal movement patterns, and classify the final action.

Unlike traditional image classification approaches, SportsVision considers the **sequence of frames in a video**, allowing the model to learn how an action develops over time.

---

## ✨ Features

### 🧠 Hybrid Deep Learning Pipeline

- 🎯 **YOLOv8 Athlete Detection** — Detects the person/athlete in each video frame.
- 🖼️ **ResNet-50 Feature Extraction** — Extracts 2048-dimensional spatial features.
- 🔄 **Bi-LSTM Temporal Modeling** — Learns movement patterns across video frames.
- 👁️ **Self-Attention** — Focuses on important temporal information.
- 🏆 **11-Class Classification** — Predicts the sports action being performed.
- 📊 **Confidence Score** — Displays the model's prediction confidence.

### 💻 Full-Stack Application

- ⚡ FastAPI backend for model inference.
- ⚛️ Next.js frontend for video upload and visualization.
- 🎥 Video preview before analysis.
- 📱 Responsive and modern UI.
- 🔌 REST API for video prediction.

---

## 🔄 How It Works

The complete SportsVision pipeline follows these steps:

1. 🎥 **Upload Video** — The user uploads a sports video through the web interface.
2. 🎞️ **Frame Sampling** — The video is converted into a fixed sequence of **32 frames**.
3. 🎯 **Athlete Detection** — YOLOv8 detects the athlete/person in each frame.
4. 🧠 **Spatial Feature Extraction** — ResNet-50 extracts **2048-dimensional visual features**.
5. 🔄 **Temporal Modeling** — Bi-LSTM learns movement patterns across the 32 frames.
6. 👁️ **Self-Attention** — Important temporal features receive greater focus.
7. 🏆 **Classification** — The classifier predicts one of the 11 action classes.
8. 📊 **Result** — The frontend displays the predicted action and confidence score.

### Architecture

```text
                    Input Sports Video
                           │
                           ▼
                  ┌─────────────────┐
                  │  Frame Sampling │
                  │    32 Frames    │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │     YOLOv8      │
                  │ Athlete         │
                  │ Detection       │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │    ResNet-50    │
                  │ 2048-D Spatial  │
                  │    Features     │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │     Bi-LSTM     │
                  │    Temporal     │
                  │    Modeling     │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ Self-Attention  │
                  │ Important       │
                  │ Features        │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   Classifier    │
                  └────────┬────────┘
                           │
                           ▼
                  🏆 Predicted Action
```

---

## 🏆 Supported Actions

SportsVision is trained using the **UCF11 Human Action Recognition Dataset**.

The dataset contains 11 action categories:

| # | Action |
|---:|---|
| 1 | 🏀 Basketball |
| 2 | 🚴 Biking |
| 3 | 🤿 Diving |
| 4 | ⛳ Golf Swing |
| 5 | 🐎 Horse Riding |
| 6 | ⚽ Soccer Juggling |
| 7 | 🎠 Swing |
| 8 | 🎾 Tennis Swing |
| 9 | 🤸 Trampoline Jumping |
| 10 | 🏐 Volleyball Spiking |
| 11 | 🚶 Walking |

---

## 📊 Dataset

SportsVision uses the **UCF11 YouTube Action Dataset**.

The dataset is divided into training, validation, and testing subsets.

| Dataset | Samples |
|---|---:|
| Training | 1119 |
| Validation | 240 |
| Testing | 240 |
| **Total** | **1599** |

The dataset itself is **not included in the GitHub repository** because of its size.

---

## 📈 Model Performance

Current evaluation on the held-out UCF11 test set:

| Metric | Score |
|---|---:|
| **Test Accuracy** | **83.33%** |
| **Macro F1-Score** | **0.8267** |
| **Weighted F1-Score** | **0.8337** |

### Per-Class Accuracy

| Action | Accuracy |
|---|---:|
| Basketball | 80.95% |
| Biking | 90.48% |
| Diving | 56.52% |
| Golf Swing | 90.91% |
| Horse Riding | 80.00% |
| Soccer Juggling | 87.50% |
| Swing | 90.00% |
| Tennis Swing | 96.00% |
| Trampoline Jumping | 94.44% |
| Volleyball Spiking | 83.33% |
| Walking | 66.67% |

> Performance may vary when the model is retrained with different configurations or random seeds.

---

## ⚙️ Technical Details

### 🎞️ Video Processing

Each input video is sampled into a fixed-length sequence of:

```text
32 Frames
```

This provides a consistent temporal input for the deep learning model.

### 🖼️ Spatial Features

ResNet-50 generates:

```text
2048 Features / Frame
```

Therefore, every video is represented as:

```text
[32, 2048]
```

### 🔄 Temporal Model

The temporal network consists of:

```text
Bi-LSTM
   │
   ▼
Multi-Head Self-Attention
   │
   ▼
Temporal Pooling
   │
   ▼
Fully Connected Classifier
```

The Bi-LSTM uses a hidden size of **256**, while the attention mechanism uses **8 attention heads**.

---

## 🛠️ Built With

| Technology | Role |
|---|---|
| Python | Machine Learning and backend development |
| PyTorch | Deep learning framework |
| YOLOv8 | Athlete detection |
| ResNet-50 | Spatial feature extraction |
| Bi-LSTM | Temporal sequence modeling |
| Self-Attention | Temporal feature refinement |
| OpenCV | Video processing |
| FastAPI | REST API and inference server |
| Next.js | Frontend application |
| React | UI development |
| Scikit-learn | Dataset splitting and evaluation |

---

## 📁 Project Structure

```text
SportsVision/
│
├── backend/
│   │
│   ├── inference/
│   │   └── predict.py
│   │
│   ├── models/
│   │   ├── yolov8_detector.py
│   │   └── resnet_features.py
│   │
│   ├── training/
│   │   ├── dataset.py
│   │   ├── extract_features.py
│   │   ├── model.py
│   │   ├── split_dataset.py
│   │   └── train.py
│   │
│   ├── utils/
│   │   └── video_processing.py
│   │
│   └── main.py
│
├── dataset/
│   ├── UCF11/
│   ├── features/
│   ├── models/
│   └── splits.pt
│
├── frontend/
│   │
│   ├── public/
│   │
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── lib/
│   │   └── utils/
│   │
│   ├── package.json
│   └── next.config.mjs
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## ⚡ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/SankalpBankar/SportsVision.git
cd SportsVision
```

---

### 2. Backend Setup

Create a Python virtual environment:

```bash
cd backend
python -m venv venv
```

Activate the environment on Git Bash:

```bash
source venv/Scripts/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

### 3. Start the Backend

From the **project root**:

```bash
cd ..
python -m uvicorn backend.main:app --reload
```

Backend:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

### 4. Frontend Setup

Open a new terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:3000
```

---

## 🔗 Environment Variables

Create the following file:

```text
frontend/.env.local
```

Add:

```env
NEXT_PUBLIC_API_URL=http://127.0.0.1:8000
```

The frontend uses this URL to communicate with the FastAPI backend.

---

## 🎬 Using the Application

1. Start the FastAPI backend.
2. Start the Next.js frontend.
3. Open `http://localhost:3000`.
4. Upload a sports video.
5. Click **Analyze**.
6. Wait for the video to be processed.
7. View the predicted action and confidence score.

### Supported Video Formats

```text
.mp4
.avi
.mov
.mkv
.mpg
```

---

## 🧪 Training the Model

### Dataset Splitting

From the project root:

```bash
python -m backend.training.split_dataset
```

The dataset is divided into:

```text
Training   → 70%
Validation → 15%
Testing    → 15%
```

### Feature Extraction

```bash
python -m backend.training.extract_features
```

Extracted features are stored in:

```text
dataset/features/
```

Each video produces a feature tensor of:

```text
[32, 2048]
```

### Model Training

```bash
python -m backend.training.train
```

Trained models are stored under:

```text
dataset/models/
```

> The UCF11 dataset, extracted features, and trained model files are not included in the repository because of their large size.

---

## 🔧 Troubleshooting

### `ModuleNotFoundError: No module named 'training'`

Run the training modules from the **project root**:

```bash
python -m backend.training.train
```

Instead of:

```bash
python training/train.py
```

---

### `ModuleNotFoundError: No module named 'backend'`

Make sure the terminal is inside:

```text
D:/SportsVision
```

Then run:

```bash
python -m uvicorn backend.main:app --reload
```

---

### `ModuleNotFoundError: No module named 'torch'`

Activate the virtual environment:

```bash
source backend/venv/Scripts/activate
```

Then install the dependencies:

```bash
pip install -r backend/requirements.txt
```

---

### Frontend Cannot Connect to Backend

Check whether the backend is running:

```text
http://127.0.0.1:8000/health
```

Expected response:

```json
{
  "status": "healthy",
  "models_loaded": true
}
```

Also verify:

```env
NEXT_PUBLIC_API_URL=http://127.0.0.1:8000
```

---

### Unsupported Video Format

Make sure the uploaded file uses one of the supported formats:

```text
MP4
AVI
MOV
MKV
MPG
```

---

## ⚠️ Limitations

- The model is trained on the UCF11 dataset.
- Real-world videos may contain different camera angles, backgrounds, lighting conditions, and video characteristics.
- CPU inference can be slower than GPU inference.
- Prediction confidence should not be interpreted as overall model accuracy.
- The complete UCF11 dataset is too large to store directly in the GitHub repository.
- Performance can vary depending on the input video and training configuration.

---

## 🔮 Future Improvements

- 🎥 Real-time webcam action recognition
- 🏟️ Support for additional sports and action datasets
- 🎯 Improved athlete tracking
- ⚡ GPU-accelerated inference
- 📊 Detailed action analytics
- 📈 Improved performance on real-world videos
- ☁️ Cloud deployment
- 📱 Improved responsive interface

---

## 🤓 Did You Know?

- 🧠 Each video is converted into a **32 × 2048** feature representation before temporal modeling.
- 🎯 YOLOv8 helps the system focus on the athlete instead of the entire background.
- 🔄 Bi-LSTM processes temporal information in both forward and backward directions.
- 👁️ Self-Attention helps the model focus on important moments within the video.
- 🏆 SportsVision recognizes **11 different actions** from the UCF11 dataset.

---

## 👨‍💻 Author

<div align="center">

### Sankalp Bankar

**B.Tech — Computer Science & Engineering**  
**Ramdeobaba University, Nagpur**

⭐ If you found this project interesting, consider giving it a star!

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer" />

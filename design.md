# Sign2Notes AI – Design Document

---

## 1. System Overview

### 1.1 Purpose
This document defines the system architecture, module design, data flow, and deployment strategy of Sign2Notes AI.

### 1.2 Objectives
- Convert sign gestures into structured academic notes  
- Support multi-input processing  
- Maintain low latency  
- Ensure privacy-first architecture  
- Enable scalable deployment  

---

## 2. High-Level Architecture

Input Layer  
↓  
Frame Processing Layer  
↓  
Pose Detection Layer  
↓  
Sign Recognition Layer  
↓  
Context Understanding Layer  
↓  
AI Note Generation Layer  
↓  
Output Layer  

---

## 3. Module Design

### 3.1 Input Layer
Handles:
- Live webcam  
- Uploaded videos  
- Video links  

Responsibilities:
- Input validation  
- FPS control  
- Buffer management  

---

### 3.2 Frame Processing Layer
Technology: **OpenCV**

Responsibilities:
- Extract frames  
- Normalize resolution  
- Preprocess for pose detection  

---

### 3.3 Pose Detection Layer
Technology: **MediaPipe**

Responsibilities:
- Detect hand and body landmarks  
- Convert frames to numerical keypoints  
- Ensure no raw video storage  

Output:
- Keypoint coordinates  
- Confidence scores  

---

### 3.4 Sign Recognition Layer
Technology: **PyTorch / HMM**

Responsibilities:
- Process temporal keypoint sequences  
- Classify sign gestures  
- Output sign label + confidence  

Design:
- Sliding window sequence modeling  
- Confidence threshold filtering  

---

### 3.5 Context Understanding Layer
Responsibilities:
- Maintain sign buffer  
- Merge related signs  
- Improve semantic accuracy  

Example:
`Tomorrow + Assignment`  
→ **Assignment due tomorrow**

---

### 3.6 AI Note Generation Layer
Technology: **LLaMA2 / Transformer Model**

Responsibilities:
- Generate structured academic notes  
- Format readable bullet points  
- Support short answers and summaries  

---

### 3.7 Output Layer
Responsibilities:
- Display structured notes  
- Show detection confidence  
- Maintain sign history  

UI Design Goals:
- Clean layout  
- Minimal distraction  
- Real-time updates  

---

## 4. Data Flow

1. User provides input  
2. Frames extracted  
3. Keypoints detected  
4. Sign classification applied  
5. Context buffer merges sequences  
6. AI generates structured notes  
7. Output displayed  

---

## 5. Deployment Strategy

### 5.1 Local Deployment
- Models run locally  
- Privacy-preserving  
- Suitable for classrooms and exams  

### 5.2 Cloud Deployment (Optional)
- Frontend hosted online  
- API-based inference  
- Scalable for institutions  

---

## 6. Design Principles
- Privacy First  
- Modular Architecture  
- Low Latency  
- Scalable Vocabulary  
- Education-Focused Output  

---

## 7. Future Design Enhancements
- Full ISL dataset integration  
- Mobile app architecture  
- LMS integration  
- Edge optimization using ONNX  
- Real-time exam support mode  

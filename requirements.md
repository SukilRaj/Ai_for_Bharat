# Sign2Notes AI – Requirements Document

---

## 1. Project Overview

### 1.1 Project Name
**Sign2Notes AI – Sign-to-Structured Learning Assistant**

### 1.2 Problem Statement
Hearing-impaired students face difficulty capturing real-time classroom information due to the lack of affordable AI systems that convert sign communication into structured academic notes. This leads to missed instructions, incomplete understanding, and dependency on manual note-taking or interpreters.

### 1.3 Solution Overview
Sign2Notes AI is a multi-input AI system that converts educational sign gestures into structured notes and answers using computer vision and NLP models.

The system supports:
- Live webcam input  
- Uploaded video files  
- Video links  

It detects signs, understands context, and generates structured academic output in real time.

---

## 2. Target Users

### 2.1 Primary Users
- Hearing-impaired students  
- Sign-language users in classrooms  
- Special education learners  

### 2.2 Secondary Users
- Teachers in inclusive classrooms  
- Educational institutions  
- Online learning platforms  

### 2.3 User Characteristics
- Depend on visual communication  
- Require real-time understanding support  
- Need structured academic content  
- Prefer simple interfaces  

---

## 3. Functional Requirements

### 3.1 Multi-Input System
- FR-1.1: Accept live webcam input  
- FR-1.2: Accept uploaded video files  
- FR-1.3: Accept video links  
- FR-1.4: Support real-time lecture and exam input  
- FR-1.5: Allow replay and reprocessing  

### 3.2 Frame Processing
- FR-2.1: Extract frames from video streams  
- FR-2.2: Optimize frame rate for real-time inference  
- FR-2.3: Preprocess frames for pose detection  

### 3.3 Pose Keypoint Detection
- FR-3.1: Detect hand and body keypoints using MediaPipe  
- FR-3.2: Convert frames into structured keypoint data  
- FR-3.3: Avoid storing raw video for privacy  

### 3.4 Sign Recognition
- FR-4.1: Recognize predefined educational signs  
- FR-4.2: Use temporal modeling for sequence recognition  
- FR-4.3: Provide confidence scores  
- FR-4.4: Maintain sliding context window  

### 3.5 Context Understanding
- FR-5.1: Combine sequential signs into meaningful context  
- FR-5.2: Reduce false predictions using buffer logic  

Example:  
`Tomorrow + Exam + Chapter 5`  
→ **Exam scheduled tomorrow on Chapter 5**

### 3.6 AI Note Generation
- FR-6.1: Generate structured lecture notes  
- FR-6.2: Generate short answers  
- FR-6.3: Format output for readability  

### 3.7 Output System
- FR-7.1: Display structured notes in real time  
- FR-7.2: Show confidence indicators  
- FR-7.3: Maintain detection history  

---

## 4. Non-Functional Requirements

### 4.1 Performance
- Real-time processing with minimal latency  
- Output generation within 2–3 seconds  
- Optimized for standard laptops  

### 4.2 Usability
- Simple and distraction-free UI  
- Clear structured note display  
- Visual feedback during processing  

### 4.3 Accessibility
- Designed for hearing-impaired users  
- High-contrast interface  
- Minimal text-heavy navigation  

### 4.4 Reliability
- Target ≥ 85% recognition accuracy  
- Stable performance during long sessions  
- Graceful handling of interruptions  

### 4.5 Security & Privacy
- No permanent storage of raw video  
- Process only numerical keypoint data  
- No external sharing of user data  

---

## 5. Data Requirements

### 5.1 Sign Dataset
- Educational sign vocabulary  
- Temporal sequences  
- Annotated training samples  

### 5.2 Keypoint Data
- Hand landmarks  
- Body pose coordinates  

### 5.3 Note Templates
- Academic sentence structures  
- Subject-specific templates  

---

## 6. Constraints & Assumptions

### Constraints
- Limited vocabulary in initial version  
- Requires visible hand gestures  
- Depends on camera quality  

### Assumptions
- Users perform standardized signs  
- Webcam access is available  
- Lighting conditions are sufficient  

---

## 7. Success Criteria
- ≥ 85% sign recognition accuracy  
- Positive accessibility feedback  
- Successful classroom demo deployment  

---

## 8. Future Enhancements
- Full Indian Sign Language support  
- Multi-language note generation  
- LMS integration  
- Mobile application version  
- Offline optimization  

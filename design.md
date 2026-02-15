Sign2Notes AI – Design Document
1. System Overview
1.1 Purpose

This document describes the technical architecture, module design, data flow, and deployment strategy of Sign2Notes AI — a multi-input sign-to-structured-learning assistant designed for educational accessibility.

1.2 System Objectives

Convert educational sign gestures into structured notes.

Support real-time and recorded input modes.

Ensure privacy by processing keypoint data instead of storing raw video.

Provide scalable and modular AI architecture.

Maintain low latency for classroom usage.

2. High-Level Architecture
2.1 System Flow
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

3. Architecture Components
3.1 Input Layer

Responsibilities:

Accept live webcam input.

Accept uploaded video files.

Accept video links (URL).

Manage real-time exam or lecture input.

Design Considerations:

Input validation

FPS control

Buffer management

Low-latency streaming

3.2 Frame Processing Layer

Responsibilities:

Extract frames from video streams.

Normalize frame size and resolution.

Preprocess frames for pose detection.

Tech Used:

OpenCV

Design Goals:

Efficient frame extraction

Maintain consistent frame rate

Minimize preprocessing delay

3.3 Pose Detection Layer

Responsibilities:

Detect hand and body landmarks.

Convert image frames into structured keypoint coordinates.

Remove dependency on raw image storage.

Tech Used:

MediaPipe

Data Output:

2D/3D keypoint coordinates

Confidence score per landmark

Privacy Design:

Only numerical keypoint data is processed.

No raw video storage.

3.4 Sign Recognition Layer

Responsibilities:

Process temporal keypoint sequences.

Classify sign gestures.

Output predicted label and confidence score.

Tech Used:

PyTorch

Hidden Markov Model (HMM) (optional for sequence modeling)

Model Design:

Sliding window temporal modeling

Sequence-based classification

Confidence threshold filtering

Performance Goal:

≥85% recognition accuracy

3.5 Context Understanding Layer

Responsibilities:

Maintain recent sign buffer.

Merge sequential signs for semantic meaning.

Reduce false positives using contextual inference.

Example:
“Tomorrow” + “Assignment”
→ “Assignment due tomorrow”

Design Strategy:

Sliding context window

Rule-based merging (initial version)

Expandable to LLM-based contextual reasoning

3.6 AI Note Generation Layer

Responsibilities:

Convert recognized signs into structured academic notes.

Generate:

Lecture notes

Short answers

Exam-related responses

Tech Used:

LLaMA2 / Transformer-based LLM

Output Format:

Bullet-point notes

Structured academic sentences

Confidence indicators

Design Goal:

Maintain clarity and readability

Avoid hallucination through controlled prompts

3.7 Output Layer

Responsibilities:

Display structured notes.

Show sign detection history.

Display confidence score.

Allow note export (future enhancement).

UI Design Goals:

Minimal and distraction-free interface.

Clear separation between live feed and notes.

Real-time update display.

4. Data Flow Design
4.1 Data Pipeline

User provides input (webcam/video/link)

Frames extracted

Keypoints detected

Temporal sign recognition applied

Context buffer merges sequences

AI generates structured notes

Notes displayed to user

4.2 Data Types
Layer	Data Type
Input	Video frames
Pose Detection	Keypoint coordinates
Recognition	Sign label + confidence
Context Layer	Buffered sign sequence
AI Layer	Structured text
Output	Formatted notes
5. Deployment Architecture
5.1 Local Deployment (Primary Mode)

All models run locally.

Ensures privacy.

Suitable for classrooms and exams.

No continuous internet dependency.

5.2 Cloud Deployment (Optional)

Frontend hosted on cloud.

Model served via API.

Scalable for institutions.

Enables centralized updates.

6. Design Principles

Privacy First

Modular Architecture

Low Latency

Scalable Vocabulary

Education-Focused Output

Multi-Input Support

7. Scalability Strategy

Expand vocabulary gradually.

Add subject-specific sign sets.

Integrate with LMS platforms.

Support multi-language output.

Optimize models using ONNX for edge deployment.

8. Error Handling Strategy

Confidence threshold filtering.

Fallback message if recognition fails.

Allow reprocessing of input.

Graceful handling of camera interruptions.

9. Future Design Enhancements

Full Indian Sign Language dataset integration.

Mobile application architecture.

Real-time exam monitoring support.

Offline LLM optimization.

Adaptive learning personalization.

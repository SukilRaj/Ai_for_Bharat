Sign2Notes AI – Requirements Document
1. Project Overview
1.1 Project Name

Sign2Notes AI – Sign-to-Structured Learning Assistant

1.2 Problem Statement

Hearing-impaired students and sign-language users face challenges in educational environments due to:

Difficulty capturing real-time classroom information

Lack of affordable sign language interpreters

Missing important instructions during lectures and exams

Limited tools that convert sign communication into structured learning content

Dependence on manual note-taking leading to incomplete understanding

These challenges reduce learning efficiency and accessibility in both physical and online classrooms.

1.3 Solution Overview

Sign2Notes AI is an AI-powered system that converts educational sign gestures into structured notes and answers using computer vision and natural language processing.

The system supports multiple input modes including live webcam input, uploaded videos, and video links. It detects sign gestures, understands context through temporal modeling, and generates structured academic outputs such as notes, answers, and summaries in real time.

2. Target Users
2.1 Primary Users

Hearing-impaired students

Sign-language users in educational institutions

Students attending online or hybrid classes

Special education learners

2.2 Secondary Users

Teachers handling inclusive classrooms

Educational institutions

Online learning platforms

Examination environments supporting accessibility

2.3 User Characteristics

Depend on visual communication

Require real-time understanding support

May not be able to follow spoken lectures

Need structured academic content instead of raw text output

Prefer simple and distraction-free interfaces

3. Functional Requirements
3.1 Multi-Input System

FR-1.1: System shall accept live webcam input for real-time sign detection
FR-1.2: System shall accept uploaded video files for offline processing
FR-1.3: System shall accept video links for sign analysis
FR-1.4: System shall support real-time input during lectures and exams
FR-1.5: System shall allow replay and reprocessing of input

3.2 Frame Processing

FR-2.1: System shall extract frames from video input streams
FR-2.2: System shall optimize frame rate for real-time processing
FR-2.3: System shall preprocess frames for pose detection
FR-2.4: System shall handle varying lighting and camera angles

3.3 Pose Keypoint Detection

FR-3.1: System shall detect hand and body keypoints using MediaPipe
FR-3.2: System shall convert video frames into numerical keypoint data
FR-3.3: System shall avoid storing raw video data for privacy
FR-3.4: System shall handle partial occlusion of gestures

3.4 Sign Recognition

FR-4.1: System shall recognize predefined educational signs
FR-4.2: System shall use temporal models for sequence recognition
FR-4.3: System shall generate confidence scores for predictions
FR-4.4: System shall maintain sliding window context for accuracy
FR-4.5: System shall support expandable sign vocabulary

3.5 Context Understanding

FR-5.1: System shall combine sequential signs into meaningful context
FR-5.2: System shall reduce incorrect predictions using context buffering
FR-5.3: System shall interpret sign sequences for academic meaning

Example:
“Tomorrow” + “Exam” + “Chapter 5”
→ “Exam scheduled tomorrow on Chapter 5”

3.6 AI Note and Answer Generation

FR-6.1: System shall generate structured notes from detected signs
FR-6.2: System shall generate short answers for question-based input
FR-6.3: System shall format output for academic readability
FR-6.4: System shall support lecture summaries

3.7 Output System

FR-7.1: System shall display structured notes in real time
FR-7.2: System shall display confidence indicators
FR-7.3: System shall maintain sign detection history
FR-7.4: System shall allow copying or exporting notes

4. Non-Functional Requirements
4.1 Performance

NFR-1.1: Real-time sign recognition shall operate with minimal latency
NFR-1.2: Output generation shall complete within 2–3 seconds
NFR-1.3: System shall run on standard laptops without GPU dependency
NFR-1.4: Model inference shall be optimized for real-time usage

4.2 Usability

NFR-2.1: Interface shall be simple and distraction-free
NFR-2.2: Notes shall be clearly structured and readable
NFR-2.3: Primary functions shall be accessible within 2–3 actions
NFR-2.4: Visual feedback shall be provided during processing

4.3 Accessibility

NFR-3.1: System shall support hearing-impaired users
NFR-3.2: Interface shall be visually clear and high contrast
NFR-3.3: System shall minimize text-heavy interactions

4.4 Reliability

NFR-4.1: System shall maintain stable performance during long sessions
NFR-4.2: Recognition accuracy target shall be minimum 85%
NFR-4.3: System shall gracefully handle input interruptions

4.5 Security & Privacy

NFR-5.1: Raw video data shall not be permanently stored
NFR-5.2: Only keypoint data shall be processed
NFR-5.3: User data shall not be shared externally
NFR-5.4: System shall follow privacy-first design principles

4.6 Compatibility

NFR-6.1: System shall work on Windows, Linux, and macOS
NFR-6.2: System shall support standard webcams
NFR-6.3: Web-based version shall support modern browsers

5. Data Requirements
5.1 Sign Dataset

Educational sign vocabulary

Temporal sign sequences

Gesture variations

Training annotations

5.2 Keypoint Data

Hand landmarks

Body pose coordinates

Temporal sequence data

5.3 Note Templates

Academic sentence structures

Subject-based templates

Question-answer formats

6. Integration Requirements
6.1 External Services

INT-1.1: MediaPipe for pose detection
INT-1.2: PyTorch for model inference
INT-1.3: LLM integration for note generation

6.2 APIs

INT-2.1: Sign recognition inference API
INT-2.2: Note generation API
INT-2.3: Video processing API

7. Constraints & Assumptions
7.1 Constraints

Limited vocabulary in initial version

Requires visible hand gestures

Performance depends on camera quality

Initial focus on educational use cases

7.2 Assumptions

Users perform standardized educational signs

Webcam access is available

Lighting conditions are reasonable

Educational vocabulary can be expanded over time

8. Success Criteria
8.1 Adoption

Usage in classroom demos or pilot institutions

Positive feedback from hearing-impaired users

8.2 Accuracy Metrics

85%+ sign recognition accuracy

90%+ correctness in note generation

8.3 User Satisfaction

Improved lecture understanding

Reduced dependency on manual note-taking

Positive accessibility feedback

9. Future Enhancements

Full Indian Sign Language support

Multi-language note generation

LMS integration

Mobile application support

Offline inference optimization

Real-time exam assistance mode

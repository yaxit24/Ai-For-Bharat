# Cognilock AI – Requirements Document

## 1. Project Overview

Cognilock AI is an AI-powered cognitive engagement system designed to convert passive screen time into adaptive micro-learning sessions. Parents upload educational material, and the system generates AI-driven questions that interrupt passive digital usage to reinforce learning.

---

## 2. Problem Statement

Children aged 3–12 engage in high levels of passive screen consumption (videos, games, social media). This leads to:
- Reduced attention span
- Weak retention of academic concepts
- Lack of personalized reinforcement
- No active cognitive stimulation during screen time

Existing solutions only block or limit usage, but do not improve learning engagement.

---

## 3. Objectives

- Convert passive screen time into active micro-learning.
- Generate adaptive questions from uploaded material.
- Personalize difficulty using AI.
- Provide parents with cognitive performance insights.
- Reduce excessive passive consumption.

---

## 4. Stakeholders

- Parents / Guardians
- Children (Ages 3–12)
- System Administrator (future scope)

---

## 5. Functional Requirements

### 5.1 Parent Module

- FR-P1: Parent can register and log in.
- FR-P2: Parent can add child profile (Name, Age, Grade).
- FR-P3: Parent can upload educational material (PDF, Text).
- FR-P4: Parent can set interruption frequency (e.g., every 10 minutes).
- FR-P5: Parent can view child performance dashboard.
- FR-P6: Parent can download performance report (PDF).

---

### 5.2 Child Module

- FR-C1: Child profile loads personalized UI.
- FR-C2: Overlay question appears during screen usage.
- FR-C3: Child must answer to continue usage.
- FR-C4: System provides instant feedback.
- FR-C5: Reward points are assigned for correct answers.

---

### 5.3 AI Engine

- FR-A1: Extract key concepts from uploaded content.
- FR-A2: Generate multiple types of questions (MCQ, Fill-in-the-blank).
- FR-A3: Adjust question difficulty dynamically.
- FR-A4: Track accuracy, response time, and concept mastery.
- FR-A5: Identify weak topics based on performance trends.

---

### 5.4 Analytics

- FR-AN1: Show concept mastery percentage.
- FR-AN2: Show screen usage vs learning engagement graph.
- FR-AN3: Show weekly cognitive report.
- FR-AN4: Predict retention trends (basic ML model).

---

## 6. Non-Functional Requirements

- NFR-1: System should respond within 2 seconds.
- NFR-2: AI question generation latency < 5 seconds.
- NFR-3: Data encryption for uploaded content.
- NFR-4: Scalable cloud architecture.
- NFR-5: Must work on Android devices (MVP).

---

## 7. Assumptions

- Parents provide relevant educational material.
- Children use Android devices.
- Overlay permissions are granted.

---

## 8. Constraints

- Must use synthetic or publicly available datasets.
- AI model must clearly state limitations.
- Limited budget (hackathon-level deployment).

---

## 9. Future Enhancements

- Emotion detection using camera (with consent).
- Gamified leaderboard.
- Multi-child dashboard.
- School integration module.

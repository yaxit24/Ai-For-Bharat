# Cognilock AI – System Design Document

---

## 1. High-Level Architecture

Architecture Type: Client-Server + AI Processing Layer

Mobile App (Android)
        ↓
Backend API Server
        ↓
AI Processing Layer
        ↓
Database (User + Performance Data)

---

## 2. System Components

### 2.1 Mobile Application (Frontend)

Technology:
- React Native / Flutter

Modules:
- Parent Dashboard
- Child Profile Interface
- Overlay Question Component
- Reward UI
- Analytics Screen

---

### 2.2 Backend Server

Technology:
- Node.js (Express) OR FastAPI
- Firebase Authentication
- REST API architecture

Responsibilities:
- Handle authentication
- Manage child profiles
- Store performance data
- Manage uploaded files
- Trigger AI question generation

---

### 2.3 AI Processing Layer

Technology:
- LLM API (OpenAI / Llama-based model)
- NLP pipeline

Subcomponents:
- PDF Parser
- Concept Extractor
- Question Generator
- Difficulty Adjustment Model
- Performance Analyzer

Flow:
1. Parse document
2. Extract key concepts
3. Generate categorized question bank
4. Store in DB
5. Adapt dynamically during usage

---

## 3. Database Design

### Tables

Users
- user_id
- email
- password_hash
- role

Children
- child_id
- user_id
- name
- age
- grade

Materials
- material_id
- child_id
- file_path
- upload_date

Questions
- question_id
- concept
- difficulty_level
- child_id

Performance
- performance_id
- child_id
- question_id
- response
- correctness
- response_time

---

## 4. Data Flow

Parent Uploads File
        ↓
Backend Stores File
        ↓
AI Parses + Generates Questions
        ↓
Question Bank Stored
        ↓
Child Screen Usage Detected
        ↓
Overlay Trigger
        ↓
Performance Logged
        ↓
Analytics Updated

---

## 5. Adaptive Difficulty Logic

If:
- Accuracy > 80% → Increase difficulty
- Accuracy 50–80% → Maintain level
- Accuracy < 50% → Reduce difficulty

Also consider:
- Response time
- Repeated errors on same concept

---

## 6. Overlay System Design

Android System-Level Overlay:
- Requires Accessibility Permission
- Runs background service
- Monitors active app usage
- Triggers pop-up question card

UI Components:
- Question Text
- Options (Buttons)
- Timer
- Reward Indicator

---

## 7. Security Considerations

- Encrypted file storage
- Secure API communication (HTTPS)
- Role-based access control
- Minimal child data collection
- AI limitation disclaimer

---

## 8. Scalability Plan

- Cloud-based backend (AWS / GCP)
- Microservice-ready AI module
- CDN for file storage
- Caching for frequently accessed questions

---

## 9. Deployment Plan

Phase 1: MVP
- Android only
- Basic AI question generation
- Simple analytics

Phase 2:
- Improved personalization model
- Advanced cognitive scoring
- Multi-device sync

---

## 10. Risks & Mitigation

Risk: AI generates incorrect questions  
Mitigation: Parent preview approval option

Risk: Overlay permission denied  
Mitigation: Standalone learning mode fallback

Risk: High AI cost  
Mitigation: Pre-generate question bank per upload

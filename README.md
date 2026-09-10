# 🚗 Adaptive Path Planning & Collision Avoidance for Autonomous Vehicles on Unstructured Indian Roads

## 🇮🇳 Smart India Hackathon 2026 — HackHive

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://jade-malabi-18e28d.netlify.app)

---
[![ppt](./SIH2026_HackHive_Presentation%20%281%29.pptx)
## 📌 Project Information

| Field | Details |
|---|---|
| **SIH Problem Statement ID** | SIH26037 |
| **Problem Statement** | Adaptive Path Planning and Collision Avoidance for Autonomous Vehicles on Unstructured Indian Roads |
| **Theme** | Smart Vehicles |
| **Category** | Software |
| **Team ID** | TEAM-142 |
| **Team Name** | HackHive |

---

## 🌐 Live Demo

### 🚀 [Launch Autonomous Vehicle Simulator](https://jade-malabi-18e28d.netlify.app)

Our web-based autonomous vehicle simulator demonstrates adaptive path planning and collision avoidance in complex Indian road environments.

**Deployment:** Netlify

**Live URL:**  
https://jade-malabi-18e28d.netlify.app

---

## 📖 About the Project

Autonomous vehicles are generally developed for structured road environments with clearly defined lanes, traffic signals and predictable traffic behavior.

Indian roads can be significantly more challenging because they may contain mixed traffic and unpredictable road-user behavior.

Our project focuses on developing an autonomous vehicle system capable of handling:

- 🚗 Cars
- 🛺 Auto-rickshaws
- 🏍️ Two-wheelers
- 🚶 Pedestrians
- 🛒 Pushcarts
- 🐄 Animals
- 🚧 Unstructured roads
- 🛣️ Missing or unclear lane markings
- 🔀 Unpredictable merging
- 🚦 Unsignalised intersections
- 👥 Crowded market areas

The proposed system follows a continuous:

**Perceive → Predict → Plan → Decide → Actuate → Replan**

architecture.

---

# 🎯 Objectives

- Detect different road users and obstacles.
- Fuse information from camera, LiDAR and radar.
- Predict the movement of surrounding road users.
- Generate safe and collision-free paths.
- Continuously monitor the environment.
- Detect newly appearing obstacles.
- Dynamically replan the vehicle's path.
- Handle roads without reliable lane markings.
- Handle mixed Indian traffic conditions.
- Evaluate the system using representative Indian road scenarios.

---

# 🧠 System Architecture

```text
                    ┌─────────────────────┐
                    │    ROAD ENVIRONMENT │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │       SENSING       │
                    │ Camera / LiDAR /    │
                    │ Radar               │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │   SENSOR FUSION     │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │     PERCEPTION      │
                    │  Object Detection   │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │     PREDICTION      │
                    │ Motion Forecasting  │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │       PLANNER       │
                    │ Safe Path Generation│
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │      DECISION       │
                    │  Stateflow Logic    │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │       CONTROL       │
                    │   Vehicle Dynamics  │
                    └──────────┬──────────┘
                               ↓
                         COLLISION CHECK
                               ↓
                       ┌───────┴───────┐
                       │               │
                     SAFE            RISK
                       │               │
                       ↓               ↓
                   CONTINUE          REPLAN
                                       │
                                       ↓
                                NEW SAFE PATH
                                       │
                                       └──────→ LOOP
[📥 Download Project Presentation](./SIH2026_HackHive_Presentation%20%281%29.pptx)

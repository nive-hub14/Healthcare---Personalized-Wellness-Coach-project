# Healthcare---Personalized-Wellness-Coach-project

🧑‍⚕️ Personalized AI Wellness Coach

A mobile-first AI Wellness Coach designed for Indian users, combining Generative AI + Wearable Data + On-device ML to deliver personalized health and fitness recommendations.

The system tracks activity, sleep, and nutrition, and provides culturally relevant diet plans, exercise routines, mental health support, and real-time form correction.

🚀 Features

Personalized Recommendations

1. Diet plans based on Indian Food Composition Tables (IFCT)

2. Region-specific vegetarian & non-vegetarian recipes

3. Personalized workout routines & meditation guides

Fitness & Exercise

1. Real-time pose estimation using TensorFlow Lite (MoveNet)

2. On-device form correction (<200ms) for yoga & gym workouts

3. AI-generated workout videos & corrective feedback

Sleep & Activity Tracking

1. Integration with Fitbit & Apple Watch

2. Heart rate, step count, and sleep quality analysis

3. Data-driven insights on lifestyle improvement

Mental Health & Motivation

1. Daily guided meditation & relaxation routines

2. Motivational messages and positive reinforcement using GenAI

3. Stress monitoring and mood tracking

Voice & Multilingual Support

1. Voice commands in Hindi & English

2. Motivational audio playback in native languages

Community & Social Features

1. Healthy competition via leaderboards

2. Community groups for motivation & support

Privacy & Security

1. All camera processing (pose estimation) runs on-device

2. No raw video uploads — only anonymized features stored

3. User data encrypted in MongoDB

4. Consent-driven cloud AI usage
   


🛠️ Tech Stack

Frontend (Mobile App): React Native

On-Device ML: TensorFlow Lite (MoveNet + custom form classifier)

Backend: Node.js + Express

Database: MongoDB

GenAI: OpenAI GPT-4 / Google Gemini (recommendations, content)

Wearables Integration: Fitbit SDK, Apple HealthKit

Languages: Hindi + English (STT/TTS with Common Voice + IndicVoices-R)



📊 Datasets Used

Exercise & Pose: Yoga for All, MM-Fit (Zenodo)

Nutrition: Indian Food Composition Tables (IFCT 2017), Indian Recipes Dataset

Sleep & Activity: Wearables datasets (Galaxy Active2, MMASH)

Voice: AI4Bharat IndicVoices-R, Mozilla Common Voice (Hindi)

Motivation: HappyDB (positive reinforcement dataset)



⚙️ System Architecture

[Mobile App] <---> [Backend API + MongoDB] <---> [GenAI Engine]
   |                       |
[TensorFlow Lite]   [Wearable Sync APIs]
   |                       |
[Pose Estimation]   [Fitbit / Apple Watch]


Camera frames → TFLite (MoveNet) → Pose Keypoints → Form Classifier → Feedback (<200ms)

User profile + wearable data → MongoDB → GPT-4/Gemini → Personalized insights



📂 Project Structure

Healthcare---Personalized-Wellness-Coach-project/
├── mobile/             # React Native mobile app
├── backend/            # Node.js + Express backend
├── ml/                 # Model training scripts & TFLite converters
│   ├── pose/           # Pose extraction + preprocessing
│   ├── form_classifier # Form correction classifier
│   └── nutrition/      # IFCT + recipe mapping
├── data/               # Public datasets (linked or preprocessed)
└── README.md           # Project documentation



▶️ Getting Started

1. Clone the repo

git clone https://github.com/nive-hub14/Healthcare---Personalized-Wellness-Coach-project.git
cd Healthcare---Personalized-Wellness-Coach-project


2. Setup backend

cd backend
npm install
npm start


3. Setup mobile app

cd mobile
npm install
npx react-native run-android


4. Train ML models
Use Google Colab or local machine:

cd ml/form_classifier
python train.py

The trained .tflite models go into mobile/android/app/src/main/assets/.


📌 Future Scope

Personalized video generation for workouts

Federated learning for continuous improvement without centralizing data

Expanding multilingual support to regional Indian languages

Integration with mental health professionals for guided therapy


🔒 Data Privacy

✅ Camera data processed locally only

✅ Wearable data encrypted at rest and in transit

✅ User can export/delete data anytime

✅ No third-party data sharing

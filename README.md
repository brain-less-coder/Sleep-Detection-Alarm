# 😴 Sleep Alarm Detector

A real-time sleep detection system using **OpenCV** and **MediaPipe** that monitors eye movement through your webcam.  
If your eyes remain closed for too long, the system triggers an alarm and displays visual warnings to help prevent drowsiness during studying, working, or driving.

---

## ✨ Features

- Real-time face and eye tracking
- Eye Aspect Ratio (EAR) based sleep detection
- Alarm sound on prolonged eye closure
- Live face bounding box and status overlay
- Lightweight and fast
- Adjustable sensitivity settings

---

## 🛠️ Tech Stack

- Python
- OpenCV
- MediaPipe
- NumPy
- Pygame

---

## 📦 Requirements

- Python 3.8+
- Webcam

Install dependencies:

```bash
pip install mediapipe==0.10.14 opencv-python numpy pygame
```

---

## ⚙️ Setup

1. Clone or download this repository.

2. Add your alarm sound file (`.mp3` or `.wav`) to the project folder.

3. Update the alarm file path in `sleep_alarm.py`:

```python
ALARM_SOUND_FILE = r"your_alarm.mp3"
```

4. (Optional) Adjust detection settings:

| Variable | Default | Description |
|---|---|---|
| `EAR_THRESHOLD` | `0.22` | Lower value = less sensitive |
| `EYE_CLOSED_SECONDS` | `2.5` | Time before alarm triggers |

---

## ▶️ Run the Project

```bash
python sleep_alarm.py
```

Press **Q** to quit the application.

---

## 🧠 How It Works

The system uses **MediaPipe Face Mesh** to detect facial landmarks in real time.

- The Eye Aspect Ratio (EAR) is calculated for both eyes.
- If the EAR drops below a threshold, the eyes are considered closed.
- If the eyes remain closed for more than the configured duration, the alarm is triggered.

---

## 📊 Detection States

| Status | Indicator |
|---|---|
| 👁️ Awake | Green face box |
| 😴 Eyes Closing | Progress timer |
| 🚨 Sleeping Detected | Red warning overlay + alarm |

---

## 🛠️ Troubleshooting

| Problem | Fix |
|---|---|
| Camera not opening | Change `cv2.VideoCapture(1)` to `cv2.VideoCapture(0)` |
| Alarm not playing | Check `ALARM_SOUND_FILE` path |
| Too many false alarms | Increase `EAR_THRESHOLD` |
| Alarm triggers too quickly | Increase `EYE_CLOSED_SECONDS` |

---

## 📁 Project Structure

```bash
Sleep-Detect-Alarm/
│
├── sleep_alarm.py
├── requirements.txt
├── README.md
├── dragon-studio-censor-beep-3-372460.mp3
└── .gitignore
```

---

🏭 Steel Mill Cobble Detection System
https://img.shields.io/badge/Python-3.9%252B-blue
https://img.shields.io/badge/PyTorch-2.0%252B-red
https://img.shields.io/badge/ROS2-Humble-blue
https://img.shields.io/badge/YOLOv8-Object%2520Detection-brightgreen
https://img.shields.io/badge/Award-Innovation%2520Award%2520%25E2%2580%2594%2520ArcelorMittal%2520Europe%25202025-gold

Real‑time cobble detection using only existing security cameras and CPU‑only hardware – delivering a 0.5s alert to protect workers and support ArcelorMittal's zero‑fatality goal.

🎥 Demo Video: Watch the system in action

🔥 The Challenge
A cobble in a steel mill is a sudden, dangerous event where hot metal escapes from the production line, posing a severe safety risk to field workers who may be nearby. Traditional monitoring relies on manual observation, which is:

Reactive – by the time a human spots the cobble, it's often too late.

High‑risk – workers must be physically close to the process.

Inconsistent – dependent on operator vigilance and line‑of‑sight.

The company's zero‑fatality safety goal demanded a faster, automated solution that could work with existing infrastructure – without adding expensive new sensors or GPUs.

🎯 My Contribution
I led this project end‑to‑end, collaborating closely with the Head of Technical Service and automation engineers (PLC specialists) to align the AI pipeline with factory constraints and existing control systems.

Key responsibilities & decisions:
Designed the hybrid CV + DL pipeline that runs reliably on CPU‑only industrial computers.

Chose ROS2 as the architectural backbone, enabling modular, multi‑threaded processing across 5 cameras.

Implemented and tuned YOLOv8 for production line detection, HSV + KNN background subtractor for anomaly spotting, and a ResNet classifier to filter false alarms.

Owned the full development cycle – from requirement gathering to on‑site deployment.

Delivered a 0.5‑second alert latency, balancing speed and accuracy under strict hardware limits.

📌 Though I wasn't leading a formal team, I coordinated with domain experts (automaticians, safety officers) to ensure the system integrated seamlessly into the plant's operations.

🛠️ Tech Stack
Layer	Technologies
Languages	Python
Deep Learning	PyTorch, YOLOv8 (line detection), ResNet (false alarm filtering)
Classical CV	OpenCV – HSV filtering, KNN background subtractor
Orchestration	ROS2 (multi‑threaded, topic‑based distributed pipeline)
Deployment	CPU‑only industrial computers, 5× security cameras (standard RTSP feeds)
🧠 How It Works – Pipeline Overview
Camera Ingestion – 5 standard security cameras stream RTSP video into ROS2 nodes.

Production Line Detection – YOLOv8 identifies the rolling mill area of interest.

Anomaly Detection – HSV filtering + KNN background subtractor highlights any unexpected movement/objects in the line.

False Alarm Filtering – A ResNet classifier distinguishes real cobbles from benign anomalies (e.g., steam, lighting changes, scale drops).

Alert Trigger – If a real cobble is confirmed, an instant alert is sent to the control room and field workers (audible/visual).

The entire pipeline runs in parallel on CPU only, thanks to ROS2's multi‑threaded architecture – each camera stream processed independently on its own thread, achieving 10 fps per stream with sub‑second latency.

📊 Key Results
Metric	Performance
Cameras	5 (standard security cameras, no hardware upgrades)
Frame rate	10 fps per camera
End‑to‑end alert latency	0.5 seconds
Hardware	CPU‑only (industrial computer, no GPU)
Detection approach	YOLOv8 + HSV/KNN + ResNet (hybrid pipeline)
Safety impact	Supports ArcelorMittal's zero‑fatality goal
Recognition	🏆 Innovation Award – ArcelorMittal Europe 2025
💡 The 0.5‑second reaction time gives workers crucial extra moments to evacuate or take cover, directly reducing injury risk.

🚀 What I Learned
CPU‑only deep learning is hard – but possible. Optimizing YOLOv8 + ResNet for real‑time inference on a CPU required careful model pruning, thread management, and frame‑skipping strategies.

ROS2 is a game‑changer for industrial vision. Its multi‑threaded, topic‑based architecture made distributing the 5‑camera pipeline surprisingly straightforward – and highly maintainable.

Domain collaboration is everything. Working with PLC experts and safety officers taught me to translate AI metrics (F1‑score, latency) into operational decisions (alert thresholds, fail‑safe behaviors).

Simple wins. The hybrid approach (classical CV for anomaly + DL for classification) was more robust and interpretable than a pure end‑to‑end deep learning model – and ran much faster on limited hardware.

📸 Gallery
Screenshot / Diagram	Description
🎥 Demo Video	Live demonstration of the system detecting a cobble and triggering an alert.
🖼️ (Coming soon)	Architecture diagram showing ROS2 node layout and camera processing threads.
🖼️ (Coming soon)	Example frames: normal operation → anomaly detection → cobble alert.
📄 License & Status
Project status: ✅ Deployed in production (ArcelorMittal plant).

Award: Innovation Award – ArcelorMittal Europe 2025.

Contact: ismael.hauss@gmail.com – I'm happy to discuss the technical details or collaboration opportunities.

Built to protect people, not just processes.


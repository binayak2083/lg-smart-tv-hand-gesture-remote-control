
📺 LG Air Gesture Remote

Control your LG Smart TV using hand gestures and facial actions (mouth open) — directly from your browser.

This project combines MediaPipe (gesture detection) with a Node.js bridge server to send commands to your LG TV using its IP address.

🧠 System Architecture
Camera (Browser - index.html)
        ↓
Gesture + Face Detection (MediaPipe)
        ↓
Node.js Bridge (bridge.js)
        ↓
LG Smart TV (via IP - WebOS API)
✨ Features
🖐️ Finger gesture control (1, 2, 3 fingers, fist, palm)
😮 Mouth-open detection → OK command
🌐 Browser-based UI (no app install needed)
⚡ Node.js backend using lgtv2
📡 Connect via TV IP address
🏠 Works on same Wi-Fi network
🎮 Manual remote buttons included
🔄 Auto reconnect + repair pairing
✋ Gesture Controls
Gesture	Action
👉 1 finger (hold)	Direction (Up/Down/Left/Right)
✌️ 2 fingers	Volume Up
🤟 3 fingers	Volume Down
✊ Fist	OK / Select
✋ Open palm	Back
😮 Mouth open	OK / Select
🌐 Important Network Setup

👉 You must:

Enter your LG TV IP address
Ensure your device (laptop/mobile/PC) and TV are connected to the same Wi-Fi/internet network

⚠️ Otherwise, the connection will NOT work.

🔌 Requirements
LG Smart TV (WebOS)
Laptop / PC / Mobile with camera
Node.js installed
Modern browser (Chrome recommended)
Same Wi-Fi network
🚀 Installation
git clone https://github.com/your-username/lg-tv-gesture-remote.git
cd lg-tv-gesture-remote
npm install
▶️ Run Project
node bridge.js

Open in browser:

http://localhost:3001
📱 How to Use
Start the server
Open browser → http://localhost:3001
Click Start Camera
Enter your TV IP address
Click Connect
Accept pairing request on TV
Use gestures to control
⚙️ Backend (bridge.js)
Connects via:
ws://<TV-IP>:3000
wss://<TV-IP>:3001
Handles:
Pairing & key storage
Command execution (ssap:// APIs)
Pointer socket for navigation
Auto reconnect
API Endpoints
Connect
POST /connect
{ "ip": "192.168.x.x" }
Repair (re-pair TV)
POST /repair
{ "ip": "192.168.x.x" }
Send Command
POST /cmd
{ "cmd": "VOL_UP" }
🎮 Supported Commands
VOL_UP, VOL_DOWN, MUTE
UP, DOWN, LEFT, RIGHT
OK, BACK, HOME
INPUT, POWER
🧪 Frontend (index.html)
Uses:
MediaPipe Hands
MediaPipe Face Mesh
Detects:
Finger positions
Gesture holding time
Mouth open ratio
Sends commands via REST API to backend
⚠️ Notes
First connection requires TV pairing confirmation
Good lighting improves gesture accuracy
Camera permission is required
Works best in Chrome
🧪 Troubleshooting

TV not connecting

Check IP address
Ensure same network
Try "Re-pair TV"

Gestures not detected

Improve lighting
Keep hand clearly visible
Avoid fast movement

Camera not working

Use http://localhost:3001 (not file://)
📌 Future Improvements
📱 Mobile UI optimization
🎯 Custom gesture mapping
🎤 Voice + gesture combo
🧠 AI gesture training
📜 License

MIT License

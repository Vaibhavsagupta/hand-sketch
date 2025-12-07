# hand-sketch
✋ Hand Gesture Whiteboard

A computer-vision–powered virtual whiteboard that lets you draw in the air using only your hand gestures.
The project uses MediaPipe, OpenCV, and custom logic to detect hand landmarks, finger positions, and interactive UI buttons (colors, pen sizes, erase, clear, board toggle).

📑 Table of Contents

Features

How It Works

Project Structure

Installation

How to Run

Usage (Hand Gestures)

Controls & UI Buttons

Dependencies

Troubleshooting

🚀 Features

Real-time hand tracking using MediaPipe

Draw on a virtual whiteboard by lifting only your index finger

Color palette toggle

Pen size selection

Eraser tool

Clear entire canvas

Toggle whiteboard visibility

Smooth line drawing and finger-following cursor

Fully gesture-controlled (no mouse/keyboard needed)

🧠 How It Works

The app uses a custom class HandTracker (in handTracker.py) to:

Detect hands using MediaPipe Hands

Extract landmark positions

Determine which fingers are raised

Use the index fingertip as the drawing pointer

The main app (main.py) uses these finger states to toggle UI menus and draw on a transparent canvas layered over the camera feed.

📁 Project Structure
project/
│── main.py               # Main application (whiteboard, UI, drawing logic)
│── handTracker.py        # Hand detection & finger tracking using MediaPipe

🛠 Installation
1. Clone the project (optional)
git clone https://github.com/your-repo/hand-gesture-whiteboard.git
cd hand-gesture-whiteboard

2. Create a virtual environment (recommended)
python3 -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows

3. Install required packages
pip install opencv-python mediapipe numpy

▶️ How to Run

From the project folder, simply run:

python main.py


The webcam will activate and the interactive whiteboard interface appears.

To quit:

q

👋 Usage (Hand Gestures)
🖊 Draw

Raise only your index finger

Keep your finger inside the whiteboard area

Move your hand to draw continuous lines

🎨 Choose Colors

Raise only your index finger

Tap the Colors button

Tap any of the color squares

📏 Change Pen Size

Tap the Pen button

Select a size from the list (5–20)

🧽 Eraser

Select the black box labeled “Eraser”

Use your finger to erase lines

🗑 Clear Entire Canvas

Tap Clear

📝 Toggle Whiteboard Visibility

Tap the Board button

🧩 Controls & UI Buttons
Button	Function
Colors	Show/hide color palette
Pen	Show/hide pen sizes
Eraser	Switch to eraser tool
Clear	Wipe entire drawing canvas
Board	Show/hide whiteboard

Each menu uses alpha blending to highlight which option is selected.

📦 Dependencies

The project uses:

opencv-python

mediapipe

numpy

Python 3.7+

Install them via:

pip install opencv-python mediapipe numpy

🛠 Troubleshooting
Webcam not detected
cap = cv2.VideoCapture(0)


Try changing 0 to 1 or 2.

MediaPipe errors

Ensure correct version:

pip install mediapipe==0.10.0

Lag or low FPS

Reduce webcam resolution

Close other applications using the GPU

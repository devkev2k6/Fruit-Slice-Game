AI-Powered Fruit Ninja (Computer Vision Edition)
A real-time, browser-based physics game that uses MediaPipe's Hand Tracking AI to turn your hand into a virtual blade. This project explores the intersection of Computer Vision, Kinematics, and WebGL rendering.
🚀 Live Demo
[INSERT YOUR GITHUB PAGES LINK HERE]
🛠️ The Tech Stack
Language: JavaScript (ES6+)
AI Framework: MediaPipe Hands
Rendering: HTML5 Canvas API
Physics: Custom-built 2D Kinematics engine
🧠 Technical Highlights
1. High-Speed Collision Detection (Line-Segment vs. Circle)
Standard distance-based collision detection fails during fast hand movements (the "ghosting" effect). To solve this, I implemented a Line-Segment Intersection algorithm. The engine calculates the shortest distance between the fruit's center and the line segment formed by the hand's position in the current frame vs. the previous frame.
Result: Pixel-perfect slicing even at high velocities.
2. Signal Smoothing (Lerp)
Raw data from AI hand landmarks can be jittery due to camera noise. I implemented Linear Interpolation (Lerp) to smooth the hand coordinates (sx += (targetX - sx) * factor).
Result: A butter-smooth "blade" trail that feels responsive and natural.
3. Procedural Physics & Momentum
When a fruit is sliced, the engine doesn't just delete the object. It:
Calculates the Swipe Angle using Math.atan2.
Spawns two "debris" objects that inherit the parent's velocity.
Applies perpendicular force to the halves based on the slice direction.
Manages an Object Pool to ensure memory efficiency and prevent lag.
📂 Project Structure
index.html - Contains the core logic, physics classes, and MediaPipe integration.
styles - Minimal CSS for an immersive "Augmented Reality" overlay.
🔧 How to Run Locally
Clone this repository.
Open index.html in any modern browser (Chrome/Safari recommended).
Ensure you are in a well-lit room and grant camera permissions.
# CV_FruitNinja_V1 🖐️🍎

A high-performance Augmented Reality (AR) experiment using **Computer Vision** to track hand movement and interact with physics-based objects in the browser.

## 📺 [Live Demo Link] 
https://devkev2k6.github.io/Fruit-Slice-Game/index.html

---

## 🚀 The Challenge
The goal was to build a low-latency "Fruit Ninja" clone that runs entirely on the client side without a backend. This required solving three specific technical hurdles:

### 1. The "Ghosting" Problem (Collision Math)
In fast-paced games, simple distance checks between a finger and an object fail because the finger "teleports" between frames. 
* **Solution:** I implemented a **Line-Segment vs. Circle** intersection algorithm. 
* **Logic:** The engine treats the movement between the current and previous frame as a solid blade, ensuring no fruit can pass through the "swing" undetected.

### 2. Signal Noise (Input Smoothing)
Webcam-based AI tracking is inherently jittery. 
* **Solution:** Applied **Linear Interpolation (Lerp)** to the raw X/Y coordinates.
* **Result:** A smoothed 35% weighted average that maintains responsiveness while removing high-frequency "hand shake."

### 3. Procedural Debris (Kinematics)
To make the game feel tactile, fruit "halves" aren't just animations. 
* **Logic:** Upon a slice, the fruit object is destroyed and replaced by debris that inherits the parent's velocity vector. 
* **Physics:** Added outward force perpendicular to the `Math.atan2` angle of the user's swipe to create a realistic "pop" effect.

---

## 🛠️ Built With
* **MediaPipe Hands** - Real-time ML pipeline for landmark detection.
* **HTML5 Canvas** - High-frequency 2D rendering.
* **Vanilla JavaScript** - No frameworks, just pure logic and math.

---

## 🕹️ Usage
1. Open the live link.
2. Grant camera permissions.
3. Stand in a well-lit area.
4. **Wave your hand** to initialize the tracking and start slicing.

---

## 👨‍💻 Author
**Debargha Sikdar** *Developing at the intersection of AI and Web Graphics.*

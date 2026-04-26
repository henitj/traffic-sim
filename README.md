## README.md

# Traffic-Sim

A sophisticated simulation of urban traffic dynamics. This project implements autonomous vehicle agents that navigate a multi-lane environment, reacting to surrounding traffic, lane boundaries, and obstacles through simulated sensors.

URL - https://traffic-sim-plum.vercel.app/

## 🚀 Features
* **Autonomous Driving Logic:** Vehicles calculate optimal steering and acceleration based on their environment.
* **Virtual Sensors:** Each vehicle utilizes a multi-ray sensor array to detect distances to other cars and road borders.
* **Neural Network Integration:** (Optional/Include if applicable) Supports brain-based decision-making for steering and speed control.
* **Dynamic Traffic Generation:** Procedurally spawns traffic to test the "ego" vehicle's maneuvering capabilities.
* **Collision System:** Robust bounding-box collision detection to handle accidents and boundary breaches.

## 🛠️ Technical Stack
* **JavaScript (ES6):** Core simulation logic and agent behavior.
* **HTML5 Canvas:** High-performance rendering of the road and vehicles.
* **CSS3:** UI for simulation controls and data overlays.

## 🕹️ How to Use
1. **Clone the repository:**
   ```bash
   git clone https://github.com/HenitJain/traffic-sim.git
   ```
2. **Launch:**
   * Open `index.html` in your browser.
3. **Controls:**
   * **Up/Down Arrows:** Manual acceleration/braking (if manual mode is enabled).
   * **Left/Right Arrows:** Manual steering.
   * **Save/Discard:** Most versions include buttons to save the current "best" neural network weights to local storage.

## 📂 Project Structure
* `index.html`: Main interface and canvas host.
* `car.js`: Defines vehicle properties, movement physics, and sensor logic.
* `road.js`: Handles lane generation and boundary mathematics.
* `sensor.js`: Implements the ray-casting logic for obstacle detection.
* `network.js`: (If applicable) The neural network architecture powering the AI.

## ⚙️ Technical Logic: Sensor Ray-Casting
The sensors function by casting rays at specific angles relative to the car's heading. For each ray, the simulation calculates the intersection point with road borders or other cars using linear interpolation:
$$P(t) = A + t(B - A)$$
The car's "brain" receives the distance (offset) from these intersections as input to determine the next action (turn left, turn right, or stay straight).

# Crowd-Density-Monitoring
This Crowd Density Monitor uses YOLOv8 and PPO Reinforcement Learning for smart surveillance. It features live ROI selection to calculate density ($people/m^2$). The RL agent adaptively adjusts inference rates—minimizing lag during congestion and saving power when empty. Built with OpenCV, it is a scalable solution for urban safety.

An intelligent crowd density estimation system that combines YOLOv8 computer vision with Reinforcement Learning (PPO) to optimize processing efficiency based on real-time congestion.

## Features

* **Live ROI Selection:** Interactive polygon drawing to define monitoring zones.

* **RL-Based Inference:** A Stable-Baselines3 agent adaptively changes cv2.waitKey delays to balance power consumption and safety.

* **Density Analytics:** Calculates people per square meter using the Shoelace formula for area calculation.

* **Visual Feedback:** Real-time status alerts (Empty, Low, Normal, Crowded) with color-coded overlays.

## Technical Architecture

* **Detection Layer:** YOLOv8 (Nano) identifies individuals.

* **Geometry Layer:** Point-in-polygon testing determines if detections fall within the user-defined ROI.

* **Intelligence Layer:** A Gymnasium-based environment feeds density data to a PPO agent, which selects the optimal frame-processing interval.

## Hardware & Software Requirements

* Python 3.8+

* Libraries: ultralytics, opencv-python, stable-baselines3, gymnasium

* Hardware: Webcam or RTSP stream (Tested on PC for maximum ML throughput).


## Usage

1. Run the script: crowd_density.ipynb

2. Select ROI: Left-click on the video feed to place points.

3. Finish: Press ENTER once the polygon is complete (minimum 3 points).

4. Monitor: The system will start tracking. Press q to exit.

## Future Scope

* Training the RL agent on historical traffic data for better predictive intervals.

* Integrating an MQTT broker to send alerts to IoT-based signage.

* Expanding to multi-camera support.

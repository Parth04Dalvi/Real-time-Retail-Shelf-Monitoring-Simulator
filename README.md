# Retail Shelf Monitoring Simulator
🤖 AI/CV Proof of Concept for Inventory Management
This project is a single-page web application that simulates a Computer Vision (CV) system used to monitor product inventory levels on retail shelves in real-time. It demonstrates the architecture required for object detection, bounding box visualization, anomaly alerting, and configuration persistence.

<img width="660" height="606" alt="image" src="https://github.com/user-attachments/assets/b0c0690b-a6b4-4367-aaea-332118b29bac" />


✨ Key Features & Technical Highlights
This simulator showcases several high-value skills sought after in software and data engineering roles:

Feature

Technical Skill Demonstrated

Real-time Bounding Box Overlays

Core Computer Vision concept: Object Localization and dynamic rendering of detected item zones.

Simulated CV Scan Loop

Use of setInterval to mimic a continuous, periodic data processing pipeline in a production environment.

Out-of-Stock Alerting

Implementation of Anomaly Detection logic based on stock thresholds.

Firebase Firestore Persistence

Mastery of Cloud Data Storage by saving and loading custom shelf layouts and product configurations (bounding boxes and max stock).

Alert Frequency Chart

Data aggregation and visualization using Chart.js to display performance trends over time.

Dynamic Configuration

User interface for defining target inventory zones (Ground Truth) using normalized coordinates.

Manual Stock Toggle

Interactive UI element demonstrating direct state manipulation and immediate visual feedback.

🛠️ Technology Stack
Frontend: HTML5, Tailwind CSS (for modern, responsive design)

Visualization: Chart.js (for time-series data visualization)

Persistence: Firebase Firestore (for saving and loading user-defined shelf configurations)

Core Logic: Vanilla JavaScript / ES Modules (for simulation and DOM manipulation)

🚀 How to Run the Simulator
This project is designed to run instantly in any modern web browser as a single file.

Open the file: Load retail_shelf_monitor/index.html in your browser.

Start Monitoring: Click the "Start Monitoring" button. The simulator will begin periodic scans (default: 2000ms).

Simulate Interaction: Click on any green bounding box in the camera feed to simulate a customer taking an item (reducing the stock).

View Alerts: Watch the Missing Items list and the System Log update instantly.

Configure: Use the Shelf Configuration Editor to add new products with custom bounding boxes.

Save/Load: Use the Save Config and Load Config buttons to save and retrieve your custom layouts using your persistent Firebase user ID.

📐 Data Structure (JavaScript)
The core data is stored in the inventoryState array, where each object represents a product's configuration and real-time status:

{
    id: 'ProductA',
    name: 'Premium Coffee',
    target: [50, 50, 300, 300], // [x_min, y_min, x_max, y_max] (Normalized 0-1000)
    stock: 3,         // Current stock level
    maxStock: 3,      // Max capacity (saved to Firestore)
    present: true     // Boolean derived from stock > 0
}

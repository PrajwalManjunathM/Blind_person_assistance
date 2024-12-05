# Traffic Sign and Object Detection System

This project integrates traffic sign detection, object detection, real-time video processing, and fall detection. It uses a combination of OpenCV, machine learning, Firebase Realtime Database, and PyQt5 for GUI development.

---

## **Features**
1. **Traffic Sign Detection**: Recognizes road signs from a video stream using a trained deep learning model.
2. **Object Detection**: Detects common objects in the video feed using a COCO pre-trained model.
3. **Fall Detection Alert**: Monitors a Firebase Realtime Database for fall detection events and sends WhatsApp alerts with the location.
4. **Voice Announcements**: Uses text-to-speech to announce detected objects and road signs.
5. **GUI Interface**: Provides a PyQt5-based graphical interface to display the live video feed and detection results.

---

## **Installation**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/traffic-sign-object-detection.git
   cd traffic-sign-object-detection
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Add your Firebase credentials file:
   - Place your Firebase service account JSON file in the project directory and name it `credentials.json`.

4. Ensure the following files are present:
   - `model_trained.p`: Pre-trained traffic sign detection model.
   - `coco.names`: Class labels for COCO object detection.
   - `ssd_mobilenet_v3_large_coco_2020_01_14.pbtxt`: Configuration file for the object detection model.
   - `frozen_inference_graph.pb`: Weights for the object detection model.

---

## **How to Run**
1. Start the program:
   ```bash
   python main.py
   ```

2. The GUI will display the live video feed, detected traffic signs, and objects.

---

## **Usage Guide**
### Key Features
- Press the "Trigger Function" button in the GUI to save the current video frame and run object detection.
- To stop the application, press `q` in the video window.

### WhatsApp Alerts
The application sends a WhatsApp message using `pywhatkit` when a fall detection event is detected in Firebase. Ensure you have WhatsApp Web linked to your phone.

---

## **Directory Structure**
```
traffic-sign-object-detection/
├── credentials.json          # Firebase service account credentials
├── model_trained.p           # Pre-trained traffic sign model
├── coco.names                # Class labels for COCO
├── ssd_mobilenet_v3_large_coco_2020_01_14.pbtxt  # Object detection config
├── frozen_inference_graph.pb # Object detection weights
├── requirements.txt          # Python dependencies
├── main.py                   # Main application script
└── Project_Folder/           # Folder to save captured frames
```

---

## **Known Issues and Limitations**
- Only `.wav` files are supported.
- Large audio files may take longer to process.
- Ensure the output directory is not empty; otherwise, the process will stop.

---

## **Customization**
### Updating the Detection Model
- Replace `model_trained.p` with a new traffic sign model if needed.
- Update the `coco.names` file to include additional object labels.

### Modifying Firebase Integration
- Change the Firebase database reference in the code to suit your database structure:
  ```python
  ref = db.reference("/fallStatus/fall_detected")
  ```

### WhatsApp Notification
- Update the phone number in the script to your desired recipient:
  ```python
  phone_number = "+919880738671"  # Replace with the recipient's number
  ```

---

## **Dependencies**
- Python 3.6+
- OpenCV
- Numpy
- PyQt5
- Pyttsx3
- PyWhatKit
- PyAutoGUI
- Firebase Admin SDK

---

## **Contributing**
Contributions are welcome! Please open an issue or submit a pull request.

---

## **License**
This project is licensed under the MIT License. See the `LICENSE` file for details.


# Moving-Object-Detection-using\_IPWEBCAM

A Python application for detecting and marking moving objects in real-time using an IP webcam feed. This project uses OpenCV for video capture, background subtraction, and contour detection to highlight objects in motion.

---

## 🚀 Features

* **Real-Time Processing**: Continuously fetches frames from an IP camera URL.
* **Background Subtraction**: Applies a running background model to isolate moving parts of the scene.
* **Contour Detection**: Identifies and draws bounding boxes around detected moving objects.
* **Customizable Parameters**: Easily adjust threshold values and minimum contour area for fine-tuning.

---

## 📋 Prerequisites

* Python 3.6 or higher
* Required Python packages:

  * `opencv-python`
  * `imutils`
  * `numpy`

---

## 🛠️ Installation & Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/MANOJ21K/Moving-Object-detection-using_IPWEBCAM.git
   cd Moving-Object-detection-using_IPWEBCAM
   ```

2. **(Optional) Create a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use venv\\Scripts\\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

---

## 🗂️ Usage

1. **Configure IP webcam feed URL**

   In `FaceRecognition(using_IPCAM).py`, update the `url` variable to match your camera stream endpoint:

   ```python
   url = 'http://<IP_ADDRESS>:<PORT>/shot.jpg'
   ```

2. **Adjust processing parameters (optional)**

   * `min_area`: The minimum contour area (in pixels) to be considered motion.
   * `delta_thresh`: Threshold for frame differencing.
   * `blur_size`: Kernel size for Gaussian blur to reduce noise.

3. **Run the script**

   ```bash
   python FaceRecognition\(using_IPCAM\).py
   ```

4. **Controls**

   * Press `Esc` to stop the video window and exit the application.

---

## 🔍 How It Works

1. **Video Capture**: Continuously fetches a JPEG snapshot from the IP webcam URL and decodes it into an OpenCV frame.
2. **Grayscale & Blur**: Converts each frame to grayscale and applies Gaussian blur to reduce noise.
3. **Background Model**: Maintains an average frame over time to represent the static background.
4. **Frame Differencing**: Computes the absolute difference between the current frame and the background model.
5. **Thresholding & Morphology**: Applies a binary threshold and dilates the result to fill in small holes.
6. **Contour Detection**: Finds contours in the thresholded image and draws bounding rectangles around those whose area exceeds `min_area`.

---

## ⚙️ Configuration

Edit these variables at the top of the script to tune performance:

| Variable       | Description                                         | Default    |
| -------------- | --------------------------------------------------- | ---------- |
| `url`          | IP webcam snapshot endpoint                         | -          |
| `min_area`     | Minimum contour area to detect motion               | `500`      |
| `delta_thresh` | Grayscale difference threshold for motion detection | `25`       |
| `blur_size`    | Gaussian blur kernel size (must be odd)             | `(21, 21)` |

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 🤝 Contributing

Contributions are welcome! Please open issues or pull requests for bug fixes and feature suggestions.

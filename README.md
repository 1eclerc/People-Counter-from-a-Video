# 🚶 People Counter Using OpenCV

This project implements a simple **people counting system** using OpenCV. It processes a video file, detects motion through background subtraction, and counts people crossing a predefined line in or out of a region of interest (ROI).

---

## 📌 Features

- Detects moving objects using background subtraction (MOG2)
- Tracks objects crossing a defined ROI line
- Counts number of people **entering (in)** and **leaving (out)**
- Displays live video feed with:
  - Bounding boxes
  - Count overlays
  - Real-time motion masks
- Basic noise filtering based on contour area, aspect ratio, and solidity

---

## 🎥 How It Works

1. The script loads `video.mp4`.
2. Applies **background subtraction** to detect moving foreground.
3. Uses **contour detection** and filters based on size and shape.
4. Defines a horizontal **ROI line** at y=300.
5. Increments `people_in` or `people_out` count when a person crosses the line.
6. Displays real-time frame updates until you press **`q`** to quit.

---

## 📂 Project Structure

```
├── counter.py         # Main people counting script
├── video.mp4          # Input video file
└── README.md          # This file
```

---

## ⚙️ Requirements

- Python 3.x
- OpenCV (`cv2`)
- imutils

Install dependencies:
```bash
pip install opencv-python imutils
```

---

## 🚀 How to Run

1. Make sure `counter.py` and `video.mp4` are in the same folder.
2. Run the script:
```bash
python counter.py
```
3. Press `q` to exit the video display.

---

## ⚠️ Notes

- The ROI line position is set to `y = 300`. You can change this by modifying:
```python
roi_line_position = 300
```
- Adjust the sensitivity by changing:
  - `min_contour_area`
  - `solidity` and `aspect_ratio` thresholds
- Currently designed for **top-down or fixed angle surveillance camera footage**.

---

## 📄 License

This project is for educational and experimental use. Contributions and improvements are welcome!

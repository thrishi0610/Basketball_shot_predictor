# 🏀 Basketball Shot Predictor using OpenCV & Computer Vision

This project is a computer vision-based application to **predict basketball shots** using trajectory analysis. It utilizes **OpenCV** and **cvzone** for real-time video processing and overlays prediction results on video frames. The application detects a colored ball in motion, fits a parabolic curve to its trajectory, and predicts whether the ball will go into the basket.

---

## 📽️ Overview

Basketball Shot Predictor analyzes a basketball's motion captured in video to determine whether it results in a successful shot or a miss. The system uses polynomial regression to estimate the ball's flight path and checks whether the predicted trajectory intersects the basket zone.

---

## 🎯 Key Features

- Real-time video input and frame-by-frame processing
- Ball detection using HSV color filtering
- Trajectory prediction using 2nd-degree polynomial fitting
- Visual overlay of the prediction and actual trajectory
- OpenCV-based display and rendering
- Support for multiple input videos and downloadable output

---

## 🗂️ Project Structure

BasketballShotPredictor/
├── README.md
├── Basketball_Shot_Predictor.ipynb
├── Videos/
│ ├── vid (1).mp4
│ ├── vid (2).mp4
│ └── ... (up to vid (7).mp4)
├── Output/
│ ├── output_video_1.mp4
│ └── ... (processed outputs)
└── requirements.txt


---

## 🧪 Technologies Used

- Python 3.9+
- OpenCV
- cvzone
- NumPy
- Google Colab (for processing and testing)

---

## 🏗️ Methodology

1. **Input Video Upload**  
   Upload up to 7 videos of basketball shots captured in a controlled environment.

2. **Color Detection**  
   Detect the ball using HSV color filtering to isolate the specific color range of the ball.

3. **Contour Tracking**  
   Use `cvzone.findContours()` to detect the ball and extract its center coordinates.

4. **Trajectory Fitting**  
   Apply a 2nd-degree polynomial regression to fit a curve through the detected positions of the ball.

5. **Prediction**  
   Determine if the trajectory will intersect with the basket area, based on X-range and Y-position checks.

6. **Rendering & Exporting**  
   Overlay the curve and prediction results on each frame. Export processed videos for download.

---

## 🎬 How to Run the Project in Google Colab

1. **Upload the Notebook & Videos**
   - Upload the `Basketball_Shot_Predictor.ipynb` file.
   - Upload your 7 basketball shot videos using:
     ```python
     from google.colab import files
     uploaded = files.upload()
     ```

2. **Run All Notebook Cells**
   - Make sure each video is processed in a loop.
   - Processed outputs will be saved as `output_video_1.mp4`, ..., `output_video_7.mp4`.

3. **Download Outputs**
   - Use the following code:
     ```python
     from google.colab import files
     for i in range(1, 8):
         files.download(f'output_video_{i}.mp4')
     ```

4. **Optional: Zip All Output Files**
   ```python
   import zipfile
   zipf = zipfile.ZipFile('AllOutputs.zip', 'w')
   for i in range(1, 8):
       zipf.write(f'output_video_{i}.mp4')
   zipf.close()
   files.download("AllOutputs.zip")

Requirements

Install dependencies via pip:
pip install opencv-python cvzone numpy

Dataset

Videos used for this project should:

Be shot from a fixed position

Have good lighting and contrast

Include a ball with a distinguishable color for easy detection

👩‍💻 Author
Thrishika R.
B.Tech – Artificial Intelligence & Machine Learning
St. Joseph’s College of Engineering, Chennai

🔗 Resources
OpenCV Documentation

cvzone Library




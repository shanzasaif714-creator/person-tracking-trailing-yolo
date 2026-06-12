# Person Tracking and Trailing in Video using YOLOv11 Models

A real-time person tracking and trailing system using YOLOv11 models (nano, small, 
large, extra-large). Each person is detected, assigned a unique ID, and tracked with 
a bounding box, label, and movement trail (polyline tail). Models compared across 
accuracy vs FPS on multiple environments.

## Results

### Model Comparison (Google Colab T4 GPU)
| Model    | Total Detections | Avg. FPS | Notes |
|----------|-----------------|----------|-------|
| YOLO11n  | 62              | 10.57    | Fastest; good for real-time applications |
| YOLO11s  | 97              | 9.70     | Most detections; outperforms overall |
| YOLO11l  | 60              | 8.45     | Lower detections; better precision likely |
| YOLO11x  | 63              | 7.91     | Slowest; minimal gain over smaller models |

### FPS Across Environments
| Environment | FPS Range |
|---|---|
| PyCharm (i5 6th gen, dual-core) | 3 – 4 FPS |
| Google Colab (without GPU) | 3 – 4 FPS |
| Google Colab (T4 GPU) | 9 – 10 FPS |

## Demo
▶️ [Watch Output Video](https://youtu.be/Eve93uPLR6c)

## Tech Stack
- Python
- Ultralytics YOLOv11
- OpenCV
- Google Colab
- PyCharm (local inference)

## Project Structure
- `object_tracking.ipynb` — Person detection and unique ID assignment (Google Colab)
- `object_tracking.py` — Person detection and unique ID assignment (PyCharm)
- `object_trailing.py` — Movement trail drawing for each individual (PyCharm)
- `tracking_summary.csv` — CSV file of tracking history and performance data

## Model Weights
The trained model weights are not included in this repository due to file size.  
📩 Feel free to reach out via [LinkedIn](https://www.linkedin.com/in/shanza-saif-704709357/) to request the model file.

## Outputs
- Processed video with unique IDs, bounding boxes, and movement trails
- CSV tracking history (`tracking_summary.csv`)
- Performance summary: speed vs accuracy trade-offs across YOLO11 model sizes

## How to Run

### Google Colab
1. Open `object_tracking.ipynb` in Google Colab
2. Connect to T4 GPU
3. Run all cells sequentially

### Local (PyCharm)
1. Clone this repository
2. Install dependencies: `pip install ultralytics opencv-python pandas`
3. Run detection: `python object_tracking.py`
4. Run trailing: `python object_trailing.py`

## Notebook
- 📓 View on GitHub: `object_tracking.ipynb` (above)
- ▶️ Run in Colab: [Open in Google Colab](https://colab.research.google.com/drive/1A7qyvl7f_8KMoRrohOCl2MXmT6fcSq0W?usp=sharing)

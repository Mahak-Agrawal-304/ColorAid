## ColorAid: AI-Based Image Enhancement for Color Vision Deficiency
**ColorAid** is an intelligent image enhancement system designed to improve visual accessibility for people with color vision deficiencies (CVD). By combining **Detectron2** for semantic object detection with advanced color science metrics, it automatically identifies visually confusing regions and enhances their distinguishability.

---

### Key Features
* **CVD Simulation:** Accurately simulates 8 types of color blindness, including Protanopia, Deuteranopia, and Tritanopia.
* **AI Object Detection:** Leverages **Mask R-CNN** via Detectron2 to segment objects and understand image context.
* **Perceptual Analysis:** Uses the **CIEDE2000 (\Delta E)** metric to identify objects that appear too similar to the user.
* **Adaptive Enhancement:** Performs localized color shifts in the **LAB color space** to maximize contrast while preserving aesthetics.
* **Auto-Tuning:** Features an automated parameter search to find the optimal enhancement settings for any specific image.

---

### Dependencies To run ColorAid, you need the following libraries:

* `torch`, `torchvision` (Deep learning backend) 
* `detectron2` (Object detection framework) 
* `gradio` (Web interface) 
* `opencv-python` (Image processing) 
* `scikit-image` (Color space conversions and \Delta E metrics) 
* `numpy`, `matplotlib`, `pandas` (Data handling and visualization) 



---

### Function Documentation
| Function | Description |
| --- | --- |
| `simulate_color_blindness` | Applies transformation matrices to an image to simulate specific CVD types. |
| `detect_objects` | Uses a Predictor to identify object instances and generate segmentation masks/edges. |
| `analyze_iou_and_lab_similarity` | Identifies object pairs that overlap (IoU) and have indistinguishable colors (\Delta E). |
| `adjust_similar_object_colors` | Applies a targeted color shift in the LAB space to specific object masks. |
| `auto_tune_and_enhance` | Iteratively tests parameter combinations to find the best enhancement configuration. |
| `run_cvd_enhancement` | The main pipeline that orchestrates simulation, detection, analysis, and enhancement. |
| `deltaE2000_heatmap` | Generates a plasma-colored heatmap visualizing the perceptual difference between images. |

---

### Installation & Usage
1. **Install requirements:**
```bash
pip install torch torchvision gradio scikit-image opencv-python
pip install 'git+https://github.com/Mahak-Agrawal-304/ColorAid.git'

```


2. **Run the application:**
```bash
python ColorAid.py

```


3. **Access the UI:** Open the local URL provided by Gradio to upload images and run the enhancement.

# **📄 INSTALLATION.md**
**CircuVision.AI – Installation Guide**  
**Version: 1.0**  
**Created by: Niraj Khadse**  
**Copyright © 2025 Niraj Khadse. All Rights Reserved.**  
**Strict Usage Policy: No usage without proper attribution to Niraj Khadse.**  

---

## **📌 Prerequisites**
Ensure your system meets the following requirements before proceeding:

- **Python 3.8+** (Recommended: Python 3.10)
- **pip** (Python package manager)
- **Virtual Environment (Optional but Recommended)**
- **NVIDIA CUDA (For GPU acceleration, if applicable)**  

---

## **📥 Installation Steps**

### **Step 1: Clone the Repository**
Run the following command in your terminal or command prompt to clone the project repository:
```bash
git clone https://github.com/yourusername/circuvision-ai.git
cd circuvision-ai
```

---

### **Step 2: Set Up a Virtual Environment (Optional but Recommended)**
A virtual environment ensures clean package management. Run the following command:

#### **For Windows:**
```bash
python -m venv vision_env
vision_env\Scripts\activate
```

#### **For macOS/Linux:**
```bash
python3 -m venv vision_env
source vision_env/bin/activate
```

If using Anaconda, you can create a virtual environment with:
```bash
conda create --name vision_env python=3.10
conda activate vision_env
```

---

### **Step 3: Install Dependencies**
Run the following command to install all necessary dependencies:
```bash
pip install -r requirements.txt
```

---

### **Step 4: Run Configuration Setup**
Ensure that all files are placed in the correct directories by running the **configuration script**:
```bash
python config_setup.py
```
This will:
- Create the necessary folder structure.
- Move files to the appropriate directories.
- Update the configuration file **(config.py)**.

---

### **Step 5: Verify Installation**
Run the following command to verify the installed packages:
```bash
pip list
```
Ensure that the following packages are installed:
- **torch**
- **torchvision**
- **flask**
- **opencv-python**
- **pytesseract**
- **pandas**
- **numpy**
- **matplotlib**
- **scipy**
- **shutil**

If any package is missing, install it manually using:
```bash
pip install <package_name>
```

---

### **Step 6: Start the CircuVision.AI Web Application (GUI)**
To launch the **Graphical User Interface**, run:
```bash
python User_Interface/app.py
```
After starting the server, open your browser and go to:
```
http://127.0.0.1:5000
```
> **You can now upload PCB images and process them for detection & BOM generation.**

---

### **Step 7: Running the Full Pipeline**
To run the **end-to-end detection pipeline**, execute:
```bash
python Backend/run_full_pipeline.py
```
This will:
- Detect components on PCB images.
- Crop detected components.
- Run OCR for text extraction.
- Generate the final **Bill of Materials (BOM)**.

---

### **Step 8: Running YOLOv5 Object Detection Manually**
If you want to run YOLOv5 object detection separately, use:
```bash
python AI_Models/YOLOv5/detect.py --weights AI_Models/YOLOv5/runs/train/exp4/weights/best.pt --source User_Interface/uploads --save-txt --save-crop
```
This command will:
- Run YOLOv5 on uploaded PCB images.
- Save detection results as text and cropped images.

---

## **🎯 Troubleshooting**
### **1. CUDA/GPU Not Detected**
If using **NVIDIA CUDA** and GPU acceleration isn't working, reinstall PyTorch with:
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```
Check if CUDA is available using:
```python
import torch
print(torch.cuda.is_available())
```

### **2. Flask Web App Not Loading**
If `http://127.0.0.1:5000` doesn’t open:
- Ensure all dependencies are installed (`pip install -r requirements.txt`).
- Restart the Flask server:  
```bash
python User_Interface/app.py
```
- If you get `jinja2.exceptions.TemplateNotFound: index.html`, move HTML templates into:
  ```
  User_Interface/templates/index.html
  ```

### **3. Permission Denied Errors on Windows**
If `PermissionError: [WinError 5] Access is denied` occurs:
- Run **Command Prompt as Administrator**.
- Retry the operation.

### **4. YOLO Model Not Found**
If you get `FileNotFoundError: best.pt not found`, ensure:
- The trained model is at:
  ```
  AI_Models/YOLOv5/runs/train/exp4/weights/best.pt
  ```
- If missing, download YOLOv5 weights and place them in this directory.

---

## **🎉 Congratulations!**
You have successfully installed **CircuVision.AI**.  
🚀 **Now, process PCB images and generate automated BOMs with ease!**  
📧 **For support or contributions, contact: nirajkhadse7255@gmail.com** 

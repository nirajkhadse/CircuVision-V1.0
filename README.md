# CircuVision.AI – AI-Powered PCB Component Recognition  
**Version: 1.0**  
**Created by: Niraj Khadse**  
**Copyright © 2025 Niraj Khadse. All Rights Reserved.**  

---

## 📌 Project Overview  
CircuVision.AI is an **advanced AI-driven PCB component recognition system** designed for **automated Bill of Materials (BOM) generation**. It utilizes **YOLOv5 for object detection**, **Tesseract OCR for text extraction**, and features an **interactive Flask-based GUI** for seamless user experience.  

## 🚀 Features  
✔ **Automated PCB Component Detection**: Identifies **capacitors, resistors, ICs, MOSFETs, microcontrollers, MOVs, film capacitors, transformers, chokes, optocouplers, etc.**  
✔ **Component Matching**: Designed to **match detected components** to standard online databases (e.g., DigiKey, Mouser) **without API integration**.  
✔ **BOM Generation**: Automatically generates an **Excel report** listing detected components, confidence levels, and OCR results.  
✔ **User-Friendly Web App**: Upload PCB images, process them, and download results **via a Flask GUI**.  
✔ **Fully Automated Pipeline**: End-to-end **processing** from **image upload → detection → OCR → BOM export**.  
✔ **Custom YOLO Training Support**: Easily train new YOLO models for improved detection accuracy.  
✔ **Strict Attribution Policy**: **This software CANNOT be used, modified, or redistributed without crediting Niraj Khadse.**  

---

## 📂 **Folder Structure**  

```bash
DeepTrace/
│── AI_Models/                  # AI Model-related files
│   ├── YOLOv5/                 # YOLOv5 object detection model
│   │   ├── detect.py           # Runs object detection
│   │   ├── crop_detected.py    # Crops detected PCB components
│   │   ├── runs/train/exp4/weights/best.pt  # Trained model weights
│   │   ├── (Other YOLOv5 files)
│
│── Backend/                    # Backend scripts & automation
│   ├── setup.py                # Runs the full pipeline
│   ├── run_pipeline.py         # Runs detection and processing
│   ├── run_full_pipeline.py    # Runs the entire end-to-end pipeline
│   ├── config_setup.py         # Organizes and moves files
│   ├── config.py               # Stores all system paths
│
│── User_Interface/              # User-facing GUI & uploads
│   ├── app.py                   # Flask Web App (GUI)
│   ├── templates/               # HTML templates (index.html, result.html)
│   ├── uploads/                 # Uploaded images go here
│   ├── results/                 # Stores processed images
│   ├── reports/                 # Stores generated BOM reports
│
│── Docs/                        # Documentation & Logs
│   ├── README.md                # Project Documentation
│   ├── folder_structure.txt      # Auto-generated folder structure log
│   ├── old_vs_new_mapping.json   # File movement logs
│
│── .gitignore                   # Ignore unnecessary files
│── requirements.txt              # Required Python dependencies
│── run.py                        # Master script to launch everything

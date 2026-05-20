Deep Learning Pipeline for Agricultural Pivot Detection & Tracking
An end-to-end, production-ready computer vision and geospatial data pipeline designed to detect, delineate, and track circular agricultural center-pivot irrigation systems using multi-temporal satellite imagery. This system fuses advanced deep learning architectures with classical computer vision and geospatial algorithms to achieve highly accurate, time-series spatial tracking.

Key Features
Custom Object Detection & Hyperparameter Optimization: Fine-tuned state-of-the-art YOLO models optimized specifically for detecting circular features in high-resolution remote sensing data.

Geospatial Integration: Robust processing of multi-channel temporal satellite imagery using advanced spatial frameworks.

Time-Series Tracking: Tracking logic that maps and monitors agricultural pivots across chronological data points using absolute geographical coordinates.

Hybrid Validation: Dual-validation pipeline leveraging classical computer vision metrics alongside deep learning inference to maximize spatial reliability.

System Architecture & Codebase Structure
The codebase follows professional, modular Python development patterns ensuring clean separation of concerns:

Plaintext
├── datadownload.py       # Automated satellite imagery retrieval and cloud filtering
├── packages.py           # Centralized dependency management and environment setup
├── params.py             # Configurable hyperparameters, thresholds, and spatial constants
├── raster.py             # Geospatial data processing, coordinate transforms, and CRS alignment
├── sort_polygons.py      # Spatial sorting, overlap handling, and geometric ordering
├── utils.py              # Auxiliary helper functions and mathematical validation routines
├── train.py              # Custom model training loop, dataset initialization, and logging
├── prediction.py         # Batch inference engine and deep learning prediction module
└── main.py               # Main execution entry point orchestrating the end-to-end pipeline
Technical Stack & Dependencies
Deep Learning Frameworks: PyTorch, Ultralytics YOLO

Geospatial & Raster Processing: GDAL, Rasterio, Shapely, PyProj

Computer Vision & Data Science: OpenCV, NumPy, Pandas, Scikit-Learn

Pipeline Orchestration: Modular Python API

Installation & Environment Setup
Clone the Repository:

Bash
git clone https://github.com/FarahAdel/agricultural-pivot-detection.git
cd agricultural-pivot-detection
Set Up a Virtual Environment:

Bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Install Dependencies:
Ensure your system has the underlying geospatial libraries (gdal) installed via your package manager, then run:

Bash
pip install -r requirements.txt
(Alternatively, initialize environment routines programmatically via packages.py)

Execution Guide
The entire end-to-end pipeline can be run from the centralized orchestration script.

1. Data Acquisition & Preprocessing
Configure your target geospatial bounding boxes and temporal constraints inside params.py, then fetch and clean the source satellite imagery:

Bash
python datadownload.py
2. Model Training
To train or fine-tune the custom detection head on your annotated dataset:

Bash
python train.py
3. Running Production Inference & Tracking
Execute the main pipeline to ingest multi-temporal rasters, generate localized predictions, execute tracking across time-series data, and output vectorized geometries:

Bash
python main.py
Evaluation & Metrics
The system evaluates bounding boxes, segmented boundaries, and tracking continuity through strict spatial constraints:

Intersection over Union (IoU): Validates spatial overlap correctness against verified ground truth boundaries.

Spatial Temporal Match Consistency: Tracks coordinate drift across historical data points to ensure temporal alignment precision.

Contribution & Best Practices
This project enforces PEP 8 styling guidelines and modular architectural patterns. Feel free to open issues or submit pull requests for performance optimizations regarding batch inference scheduling or cloud native integrations.

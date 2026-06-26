# Mask Detection — Fine-tuning YOLOv26

Short description:

This project contains a notebook for fine-tuning a YOLOv26-based mask detection model. All experiments, model weights, and training results are stored in the `runs/` folder.

Repository structure
- [mask-detection-on-fine-tuning-yolov26.ipynb](mask-detection-on-fine-tuning-yolov26.ipynb) — main notebook for fine-tuning and inference.
- [runs/detect/train/args.yaml](runs/detect/train/args.yaml) — latest training arguments and configuration.
- [runs/detect/train/results.csv](runs/detect/train/results.csv) — summary of training/validation metrics.s.

Requirements (example)

It is recommended to create a virtual environment and install dependencies before running the notebook.

```bash
python -m venv .venv
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```


```bash
pip install jupyterlab notebook ultralytics opencv-python matplotlib pandas seaborn torch torchvision
```

Running the notebook

1. Open [mask-detection-on-fine-tuning-yolov26.ipynb](mask-detection-on-fine-tuning-yolov26.ipynb) in Jupyter or VS Code.
2. Run the notebook cells in order to load the dataset, fine-tune the model, and perform inference.

Training & results

- Training outputs and metrics are stored in `runs/detect/train/` (see the files listed above).
- To load the best weights in the notebook, use: `runs/detect/train/weights/best.pt`.

Example of loading weights in the notebook:

```python
# Example using the Ultralytics API
from ultralytics import YOLO
model = YOLO('runs/detect/train/weights/best.pt')
results = model.predict(source='path/to/image_or_folder')
```

Reproduction & notes

- To reproduce the experiment, check `args.yaml` in the training folder for the parameters used.
- If you want cleaner experiment tracking, consider adding `requirements.txt`, `environment.yml`, and a separate README for each experiment.


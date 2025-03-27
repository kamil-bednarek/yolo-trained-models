# License Plate Recognition - YOLOv11 Model

A YOLOv11 object detection model trained on the License Plate Recognition dataset for detecting and localizing vehicle license plates in images.

## Model Information

- **Model Version**: YOLOv11n
- **Dataset**: [License Plate Recognition Dataset](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e)
- **Author**: Roboflow Universe Projects
- **License**: CC BY 4.0
- **Classes**: 1 (License_Plate)

## Performance Metrics

After 100 epochs of training:
- **mAP50**: 0.97232 (97.23%)
- **mAP50-95**: 0.71338 (71.34%)
- **Precision**: 0.98622 (98.62%)
- **Recall**: 0.94536 (94.54%)

For detailed metrics, see the [results.csv](./results.csv) file and the visualizations in this directory.

## Training Parameters

The model was trained with the following key parameters:
- **Epochs**: 100
- **Batch Size**: 16
- **Image Size**: 640x640
- **Optimizer**: Auto
- **Initial Learning Rate**: 0.01
- **Data Augmentation**: Mosaic, HSV, Flip

For full training parameters, check the [args.yaml](./args.yaml) file.

## Usage

```python
from ultralytics import YOLO

# Load the model
model = YOLO('path/to/weights/best.pt')

# Perform inference on an image
results = model('path/to/image.jpg')

# Process results
for result in results:
    boxes = result.boxes  # Boxes object for bounding boxes outputs
    masks = result.masks  # Masks object for segmentation masks outputs
    keypoints = result.keypoints  # Keypoints object for pose outputs
    probs = result.probs  # Probs object for classification outputs
```

## Model Weights

The model weights are available in the [weights](./weights) directory:
- `best.pt`: Best weights based on validation mAP
- `last.pt`: Weights from the last training epoch

## Dataset Description

The License Plate Recognition dataset contains annotated images of vehicle license plates. This model can be used for various applications including:

1. **Law Enforcement and Security**: Detecting license plates of vehicles involved in traffic violations or criminal activities
2. **Parking Management**: Automating entry, exit, and vehicle records in parking facilities
3. **Toll Collection**: Identifying vehicles passing through toll booths for automated toll collection
4. **Access Control**: Enabling automatic access for authorized vehicles to gated communities or private properties
5. **Traffic Monitoring**: Gathering real-time data about traffic patterns for urban planning

## Citation

If you use this model in your research or project, please cite the original dataset:

```bibtex
@misc{
    license-plate-recognition-rxg4e_dataset,
    title = { License Plate Recognition Dataset },
    type = { Open Source Dataset },
    author = { Roboflow Universe Projects },
    howpublished = { \url{ https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e } },
    url = { https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e },
    journal = { Roboflow Universe },
    publisher = { Roboflow },
    year = { 2024 },
    month = { oct },
    note = { visited on 2025-03-26 },
}
```

## License 

This model is made available under the CC BY 4.0 license as per the original dataset license. 
# Fire Detection - YOLOv11 Model

A YOLOv11 object detection model trained on the Amenazas dataset for detecting fires in images.

## Model Information

- **Model Version**: YOLOv11n
- **Dataset**: [Amenazas Dataset](https://universe.roboflow.com/cristhian-guerrero-e1tw1/amenazas)
- **Author**: Cristhian Guerrero
- **License**: Public Domain
- **Classes**: 1 (fire)

## Performance Metrics

After 100 epochs of training:
- **mAP50**: 0.65051 (65.05%)
- **mAP50-95**: 0.33004 (33.00%)
- **Precision**: 0.66407 (66.41%)
- **Recall**: 0.62885 (62.89%)

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

The Amenazas dataset contains annotated images of fires for detection purposes. It can be used for fire monitoring systems, safety applications, and automated alert systems.

## Citation

If you use this model in your research or project, please cite the original dataset:

```bibtex
@misc{
    amenazas_dataset,
    title = { Amenazas Dataset },
    type = { Open Source Dataset },
    author = { Cristhian Guerrero },
    howpublished = { \url{ https://universe.roboflow.com/cristhian-guerrero-e1tw1/amenazas } },
    url = { https://universe.roboflow.com/cristhian-guerrero-e1tw1/amenazas },
    journal = { Roboflow Universe },
    publisher = { Roboflow },
    year = { 2024 },
    month = { jul },
    note = { visited on 2025-03-27 },
}
```

## License 

This model is made available under the Public Domain as per the original dataset license. 
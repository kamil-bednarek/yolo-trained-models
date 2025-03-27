# My Game Pics - YOLOv11 Model

A YOLOv11 object detection model trained on the My Game Pics dataset for detecting wildlife animals in trail camera footage from East Texas.

## Model Information

- **Model Version**: YOLOv11n
- **Dataset**: [My Game Pics Dataset](https://universe.roboflow.com/my-game-pics/my-game-pics)
- **Author**: My Game Pics
- **License**: CC BY 4.0
- **Classes**: 5 (Coyote, Deer, Hog, Rabbit, Raccoon)

## Performance Metrics

After 100 epochs of training:
- **mAP50**: 0.96167 (96.17%)
- **mAP50-95**: 0.70844 (70.84%)
- **Precision**: 0.94973 (94.97%)
- **Recall**: 0.90475 (90.48%)

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

This dataset contains annotated pictures of animals from trail cameras in East Texas. It can be used for hunting applications, monitoring animal population health, counting deer sightings, and automatically filtering trail cam footage.

## Citation

If you use this model in your research or project, please cite the original dataset:

```bibtex
@misc{
    my-game-pics_dataset,
    title = { My Game Pics Dataset },
    type = { Open Source Dataset },
    author = { My Game Pics },
    howpublished = { \url{ https://universe.roboflow.com/my-game-pics/my-game-pics } },
    url = { https://universe.roboflow.com/my-game-pics/my-game-pics },
    journal = { Roboflow Universe },
    publisher = { Roboflow },
    year = { 2025 },
    month = { mar },
    note = { visited on 2025-03-27 },
}
```

## License 

This model is made available under the same license as the dataset: CC BY 4.0. 
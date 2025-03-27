# YOLO Built Models Repository

A centralized collection of pre-built YOLO (You Only Look Once) object detection models trained on specific datasets. This repository serves as a community resource hub for researchers, developers, and practitioners looking for ready-to-use models across various domains.

## Purpose

This repository aims to:

- Provide a curated collection of high-quality pre-trained YOLO models
- Make state-of-the-art object detection accessible to everyone
- Facilitate knowledge sharing among the computer vision community
- Enable quick adoption of models for specific use cases without retraining
- Ensure proper attribution to dataset creators and model trainers

## Quick Model Selection

Looking for a model that detects specific objects? Check our [Model Catalog](./MODEL_CATALOG.md) for a complete overview of all available models, searchable by class and use case.

## Repository Structure

The repository is organized by YOLO versions:

```
yolo-built-models/
├── v8/
│   ├── dataset-name-1/
│   ├── dataset-name-2/
│   └── ...
├── v9/
├── v10/
├── v11/
│   └── my-game-pics/
└── ...
```

Each model directory contains:
- Model weights in the `weights/` folder (typically `best.pt` and `last.pt`)
- Training and validation results
- Evaluation metrics and visualizations
- Configuration file (`args.yaml`)
- A detailed README.md file with model-specific information

## Available Models

For a complete, up-to-date list of all available models with their classes and performance metrics, please refer to our [**Model Catalog**](./MODEL_CATALOG.md).

Current model categories include:
- Wildlife detection models (coyote, deer, hog, rabbit, raccoon)
- *(more categories to come as the repository grows)*

Each model in this repository comes with detailed documentation and citation information in its own directory.

The models are trained using [Ultralytics](https://github.com/ultralytics/ultralytics) implementation of YOLO, and many utilize datasets from [Roboflow Universe](https://universe.roboflow.com/).

## Using the Models

To use a model from this repository:

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/yolo-built-models.git
   cd yolo-built-models
   ```

2. Navigate to the desired model's directory:
   ```bash
   cd v11/my-game-pics
   ```

3. The model weights can be found in the `weights/` folder. Use `best.pt` for inference:
   ```python
   from ultralytics import YOLO

   # Load the model
   model = YOLO('path/to/best.pt')

   # Perform inference
   results = model('image.jpg')
   ```

## Contributing

We welcome contributions! To add your own trained YOLO model:

1. Fork this repository
2. Create a directory for your model under the appropriate YOLO version folder
3. Add your model files including:
   - Model weights (in a `weights/` subfolder)
   - Training configuration
   - Evaluation results
   - A README.md with information about the model, dataset, and performance

4. Create a pull request with a clear description of your model

### Contribution Requirements

Each contributed model should include:
- Clear reference to the dataset used for training
- Attribution to the author/creator
- Basic performance metrics
- Brief description of the model's intended use case
- Any specific instructions for using the model

## License

This repository is open source and available under the [MIT License](LICENSE).

## Acknowledgements

Thanks to all contributors who have shared their trained models to benefit the community!

Special thanks to:
- [Ultralytics](https://github.com/ultralytics/ultralytics) for developing and maintaining the YOLO framework
- [Roboflow](https://roboflow.com/) for hosting many of the datasets used in these models

---

*Note: When using these models, please ensure you comply with the license terms of both this repository and the original datasets used for training.*

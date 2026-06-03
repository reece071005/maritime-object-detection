# Fine-Tuning DETR for Maritime Object Detection

This project fine-tunes a pretrained DETR (DEtection TRansformer) ResNet-50 model for maritime object detection using the Singapore Maritime Dataset in COCO format.

The objective is to detect and localise maritime objects such as vessels, ferries, speed boats, sail boats, kayaks, buoys, and other maritime targets using bounding boxes.

---

## Project Overview

The project includes:

- Dataset validation and cleaning
- COCO annotation parsing
- Dataset splitting into training, validation, and testing sets
- DETR image preprocessing using Hugging Face Transformers
- Transfer learning and fine-tuning of a pretrained DETR ResNet-50 model
- Comparison of multiple training configurations
- Evaluation using object detection metrics
- Visualisation of model predictions on unseen images

---

## Dataset

This project uses the Singapore Maritime Dataset available through Roboflow Universe:

https://universe.roboflow.com/maritime-cumkb/singapore-maritime

Download the dataset in COCO format and extract it into:

```text
SingaporeMaritime.coco/
```

The dataset is not included in this repository due to its size.

---

## Model

The model used for this project is:

```text
facebook/detr-resnet-50
```

The pretrained COCO classification layer was replaced and adapted to the maritime object classes contained within the Singapore Maritime Dataset.

---

## Experiments

Three fine-tuning experiments were performed:

| Experiment | Learning Rate | Weight Decay | Epochs |
|------------|--------------|--------------|--------|
| Experiment 1 | 1e-5 | 0.0001 | 5 |
| Experiment 2 | 1e-5 | 0.0001 | 10 |
| Experiment 3 | 5e-5 | 0.0001 | 5 |

Experiment 2 achieved the strongest overall performance and was selected as the final model.

---

## Best Results

| Metric | Value |
|--------|------:|
| mAP | 0.3491 |
| mAP@50 | 0.5443 |
| mAP@75 | 0.3601 |
| Mean Recall | 0.4634 |

---

## Getting Started

Install the required packages:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
MAAI901_Assignment_2.ipynb
```

and run all cells in sequence.

---

## Requirements

Main libraries used:

- Python
- PyTorch
- Hugging Face Transformers
- TorchMetrics
- pycocotools
- Pillow
- Matplotlib
- NumPy
- tqdm

---

## Notes

The dataset and trained model checkpoints are not included in this repository due to GitHub file size limitations.

Running the notebook will generate model checkpoints automatically inside the `experiments/` directory during training.

---

## Author

Reece Bridle

MAAI901 – Deep Learning for Visual Data

University of Wollongong in Dubai
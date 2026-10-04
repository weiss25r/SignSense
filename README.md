# SignSense

## Description
This repository is related to the project for the [Machine Learning](https://www.dmi.unict.it/farinella/ML/) course, which was held at the Department of Mathematics and Computer Science of the University of Catania by prof. Giovanni Maria Farinella.  
The project development team is composed of Lorenzo La Rocca, Raffaele Terracino, and Edoardo Tantari.  
The goal of the project is to build and compare different **object detection** models capable of detecting and classifying road signs. For this project, a subset of 19 classes was selected from all possible European road signs.

This subset includes the following road signs:
* mandatory left turn sign  
* mandatory right turn sign  
* yield sign  
* no entry sign  
* stop sign  
* green traffic light  
* red traffic light  
* speed limit signs from 20 to 120 km/h  

Among the state-of-the-art one-stage architectures, [YOLOV12](https://docs.ultralytics.com/models/yolo12/) was selected. For the two-stage approach, [Faster_RCNN_ResNet50](https://docs.pytorch.org/vision/main/models/generated/torchvision.models.detection.fasterrcnn_resnet50_fpn.html) was used. 

## Project structure
- `demo/` – contains the streamlit web app for running inference on images and videos
- `docs/` – contains the technical report describing data collection, models, experiments, source code and demo
- `models/` – contains metrics and checkpoints of trained models
- `scripts/` – contains scripts for dataset pre-processing
- `src/` – contains the source code for training and evaluating the models
  - `yolo/` - contains a notebook for training, evaluation and inference on YOLO v12 using the **Ultralytics** library 
  - `Faster_RCNN/` - contains a notebook and scripts for training, evaluation and inference on Faster R-CNN, written using **Pytorch**
- `requirements.txt` – list of python dependencies to run scripts, notebooks and the demo

## Running the demo
After installing the dependencies listed in `requirements.txt`, move to  `demo/` and run the following command:

```bash
streamlit run main.py
```

## Demo screenshots

### Inference on images
![](docs/screen_demo.png)
### Inference on videos
![](docs/screen_demo_video.png)

## Notes
The first time you launch the web app, it will be slower than subsequent launches due to the download of the trained 315 MB FasterRCNN model from [HuggingFace](https://huggingface.co/).

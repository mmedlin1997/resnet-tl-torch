# resnet-tl-torch
Transfer learning image classification demo, using Resnet model in PyTorch 

Transfer learning begins with ResNet 1000 output model and replaces with 2 outputs. Then training by 2 different techniques: 
1. Fine-tuning - train output layer weights, retrain all other weights
2. Fixed feature extraction - train only output layer weights, freeze all other weights.

Program has two modes: training and production. In training models are saved ONNX model format. In production, ONNX models are loaded and test dataset images are fed 1-by-1 through the model. 

## Usage
Select target processor with command line option -d. Options are: cpu, cuda, cuda:0
```bash
python app.py -d cuda
```
Enable training and/or production inference modes with command line toggles: -t,--train; -p,--prod 
```bash
python prod.py -d cuda -t
python prod.py -d cuda -p
```

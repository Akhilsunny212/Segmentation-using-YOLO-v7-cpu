# Segmentation-using-YOLO-v7-cpu
Implementation of Segmentation using YOLO v7 in cpu

<h2>Object Detection:</h2> Object detection models identify objects in an image and enclose them within bounding boxes. They answer the question of "what objects are in this image and where are they?"


<h2>Semantic Segmentation:</h2> Semantic segmentation models classify each pixel of an image into a class, without differentiating between different instances of the same class. For example, in an image with multiple cars, semantic segmentation will label all cars as the same class without distinguishing between each car.

<h2>Instance Segmentation:</h2> Instance segmentation combines the nuances of both tasks above. It not only classifies each pixel of an image into a class (like semantic segmentation) but also differentiates between distinct instances of the same class. Using the previous example, instance segmentation would label all cars but also differentiate between each individual car, even if they are of the same type.

Set up the workspace where you're operating; I've set it up using Anaconda.

<h2>Create a Python 3.7 virtual environment using Conda:</h2>
conda create -n yolov7 python=3.7
conda activate yolov7



clone the repo from [WongKinYiu/yolov7/seg
](https://github.com/WongKinYiu/yolov7/tree/u7/seg)
<h2>Install dependencies from the requirements.txt file</h2>
pip install -r requirements.txt!

<h2>Preparing the Data</h2>
Obtain the dataset from Kaggle and use the Roboflow tool for image annotation.
<h2>Structuring Data for Training</h2>
Ensure your data is structured as follows:

<p align="center">
  <img src="https://github.com/Akhilsunny212/Segmentation-using-YOLO-v7-cpu/blob/main/image_path.png?raw=true" >
</p>
<h2>Configuration File Creation</h2>
n the data directory, create a file named custom.yaml and insert the following code:

train: "path to train folder"
val: "path to validation folder"
nc: 1 # Number of classes
names: ['car']

<h2>Model Configuration</h2>
Update yolov7-segmentation/models/segment/yolov7-seg.yaml with the correct number of classes (nc: 1).

<h2>Training the Model</h2>
Execute the following command to start training:

python segment/train.py --data data/custom.yaml --batch 4 --weights "yolov7-seg.pt" --cfg "models/segment/yolov7-seg.yaml" --epochs 10 --name yolov7-seg --img 640 --hyp "data/hyps/hyp.scratch-high.yaml"
Adjust batch and epochs according to your needs. A runs directory will be created upon training completion.

<h2>Checking the Output</h2>
The trained model will be saved as best.pt in yolov7-segmentation/runs/train-seg/yolov7-seg/weights/.

<h2>Model Inference</h2>
To test the model on an image or video, run:

python segment/predict.py --weights "runs/train-seg/yolov7-seg/weights/best.pt" --source "image.jpg/video.mp4" --trk

Results will be saved in yolov7-segmentation/runs/predict-seg/exp.





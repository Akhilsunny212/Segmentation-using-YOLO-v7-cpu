# Segmentation-using-YOLO-v7-cpu
Implementation of Segmentation using YOLO v7 in cpu

<h2>Object Detection:</h2> Object detection models identify objects in an image and enclose them within bounding boxes. They answer the question of "what objects are in this image and where are they?"

<h2>Semantic Segmentation:</h2> Semantic segmentation models classify each pixel of an image into a class, without differentiating between different instances of the same class. For example, in an image with multiple cars, semantic segmentation will label all cars as the same class without distinguishing between each car.

<h2>Instance Segmentation:</h2> Instance segmentation combines the nuances of both tasks above. It not only classifies each pixel of an image into a class (like semantic segmentation) but also differentiates between distinct instances of the same class. Using the previous example, instance segmentation would label all cars but also differentiate between each individual car, even if they are of the same type.

Set up the workspace where you're operating; I've set it up using Anaconda.

<h2>Create a Python 3.7 virtual environment using Conda:</h2>
conda create -n yolov7 python=3.7
conda activate yolov7

clone the repo from WongKinYiu/yolov7/seg

<h2>Install dependencies from the requirements.txt file</h2>
pip install -r requirements.txt!
clone the repo from WongKinYiu/yolov7/seg

<h2>Preparing the Data</h2>
Obtain the dataset from Kaggle and use the Roboflow tool for image annotation.
Structuring Data for Training
Ensure your data is structured as follows:
<ul>
<li>yolov7-segmentation/data</li>
<ul>
  <li>train</li>
  </ul>
  <ul>
    <li>images (contains all training images)</li>
    <li>labels (contains all training labels)</li>
    </ul>
  <ul>
  <li>valid</li>
    </ul>
  <ul>
    <li>images (contains all training images)</li>
    <li>labels (contains all training labels)</li>
     </ul>
    </ul>

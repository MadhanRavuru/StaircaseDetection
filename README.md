# Training YOLO with Custom Dataset in PyTorch

Detecting single class (stairs) using YOLO Object detection framework. The project uses yolov3 for staircase detection

In the *data/StaircaseDetection* folder, we have the training images along with annotated labels generated using *bbox.py*. As the dataset size is small, we have augmented the images.

The initial weights for model are from coco dataset with 80 classes.

Train using the *Train.ipynb* notebook to get weights for our model. Place it in config folder.

# Object detection

Place the test image in *image* folder and run *PyTorch_Object_Detection.ipynb* notebook. we get the image with bounding boxes.

**Observation**
When the input image has stairs with reasonable case, we get good stair-case detection.
To make it work for any scale, the training should be performed with many scales of resolution of images.

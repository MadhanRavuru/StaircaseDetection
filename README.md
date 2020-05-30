# YOLO with Custom Dataset in PyTorch

This article shows how to train on custom dataset
https://towardsdatascience.com/training-yolo-for-object-detection-in-pytorch-with-your-custom-dataset-the-simple-way-1aa6f56cf7d9

# Training for Staircase Detection in floor plans

Detecting single class (stairs) using YOLO Object detection framework. The project uses yolov3 for staircase detection

High quaity architectural images from [Cubicasa5k](https://zenodo.org/record/2613548#.XtDCHMYzZuQ) dataset is considered for training. However, many images do not contain stairs in them. I handpicked some images with stairs for training. Further challenging images were selected by googling to generate more robust model for challenging plans.

In the *data/StaircaseDetection* folder, we have the training images along with annotated labels generated using *bbox.py*. As the dataset size is small, we have augmented the images. Even after augmentation, training set has around only 250 images.

The initial weights for model are the weights from coco dataset with 80 classes.

Train using the *Train.ipynb* notebook to get weights for our model. *checkpoints* folder will be created with weights stored for certain epochs. Place them in *config* folder with name *yolov3.weights*.

# Object detection - Testing

Place the test image in *image* folder and run *PyTorch_Object_Detection.ipynb* notebook. we get the image with bounding boxes.

**Observation**
When the input image has stairs which are identifiable(reasonable staircase size compared to image), we get good stair-case detection.
The model cannot detect very small stairs in a bigger building plan image. We can crop the bigger image to get images with stairs of reasonable size to perform detection.

As you can see, *future.jpg* inside the images folder, has no good stair detection.
But the cropped versions of it, for ex, *future2.jpg* and *future3.jpg* have good stair detection.

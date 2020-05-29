# Training YOLO with Custom Dataset in PyTorch

Detecting single class (stairs) using YOLO Object detection framework. The project uses yolov3 for staircase detection

High quaity architectural images from [Cubicasa5k](https://zenodo.org/record/2613548#.XtDCHMYzZuQ) dataset is considered for training. However, many images do not contain stairs in them. I handpicked some images with stairs for training. We can further select images from dataset to have more robust model.

In the *data/StaircaseDetection* folder, we have the training images along with annotated labels generated using *bbox.py*. As the dataset size is small, we have augmented the images. Even after augmentation, training set has around only 250 images.

The initial weights for model are from coco dataset with 80 classes.

Train using the *Train.ipynb* notebook to get weights for our model. Place it in *config* folder.

# Object detection - Testing

Place the test image in *image* folder and run *PyTorch_Object_Detection.ipynb* notebook. we get the image with bounding boxes.

**Observation**
When the input image has stairs which are identifiable(resonable stair size compared to image), we get good stair-case detection.
The training was not performed for small stairs in a bigger building plan image, and so we couldn't detect them.

As you can see, *future.jpg* inside the images folder, has no good stair detection.
But the cropped versions of it, *future2.jpg* and *future3.jpg* have good stair detection.

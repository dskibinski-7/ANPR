# ANPR

## Automatic number plate recognizer

The purpose of the project was to create a system that is able to detect licence plates from the image and detect their numbers. [Current state of the model.](ckpt-6.index)

### Model and dataset
We used [tensorflow pre-trained model](https://github.com/tensorflow/models) that can be downloaded [here.](http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz)
This model was trained on [COCO 2017 dataset](https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset) with training images scaled to 320x320. 
Our model was fully trained on the [Car Licence Plate Detection dataset](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection?resource=download) from Kaggle. <br />
This dataset contains 443 images with bounding box annotations of the car license plates within the image. The collection includes images of cars with visible number plates. The images are taken from a variety of perspectives, most with one visible vehicle, but there are also examples with more objects. 
The dataset includes number plates from various countries, as well as custom ones. <br />
Example input images: <br />
| <img src="example_input1.png"/>  | <img src="example_input2.png"/> | <img src="example_input3.png"/> |
| ------------- | ------------- | ------------- |

The output is an image with found boundaries (considering a certain threshold of model confidence) of the licence plate: <br />
<p align="center">
  <img src="example_detection.png"/>
</p>

  
### Recognizing numbers
Firstly we preprocessed images with detected licences manually using the OpenCV library and a model for characters detection that was used in our other project but the results were unsatisfying. 
That's why we switched to [EasyOCR library](https://github.com/JaidedAI/EasyOCR) which outperformed our previous solution. <br />
<p align="center">
  <img src="example_recognition.png"/>
</p>

### Further work
Further works are related to the Master thesis and will be based on comparing different methods of licence plate detection and recognition. The objective is to create a system capable of processing video. <br />
#TODO
- [x] Describe dataset
- [ ] Describe results

# overlap-crop-and-recover-image
In some image segmentation task (such as nuclei segmentation), because of large image size, it can not be input into the neural network directly. It is a good choice to crop large images into small ones as input of neural network and overlapping crop can significantly increase the number of training images. But one of the defects of this method is that the edge information may be lost which may lead to bad segmentation result, for example, some cells are cut in half in the edge of cropped images. In order to solve this problem, this programme uses the method of overlapping crop to get the small overlapped images. After putting the cropped images into the neural network and getting the segmentation resulting images, only the middle part of each resulting image is taken and the edge part is discarded, and all the middle parts are recovered to the  segmentation result with original image size.
# visualization effect
original image:

![image](https://github.com/flyingdingding/overlap-crop-and-recover-image/blob/master/test_images/resize_2.png)

cropped images:

![image](https://github.com/flyingdingding/overlap-crop-and-recover-image/blob/master/test_images/resize_3.jpg)

recovered image:

![image](https://github.com/flyingdingding/overlap-crop-and-recover-image/blob/master/test_images/resize_2.png)

## Prerequisites
- Python 3.x
- numpy
- pillow

### Run programme
Below script gives you an example of running a sample programme.
```
python main.py --cropped_image_height 256 --cropped_image_width 256 --overlap_coefficient 2
```

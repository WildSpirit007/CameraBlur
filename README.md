CameraBlur:Portrait mode using DeeplabV3+ Semantic Image Segmentation 
=====================================================================
A simple android app to implement Portrait mode using a single sensor like in Pixel 2 (well not exactly exactly like Pixel 2's). This app allows you to either click image from your phone or select an image from storage and apply the blur. This app can run on ARM32 bit `ARM v7A` as well as ARM64 `ARMv8-A`.

## Downloads

Download apk from [here](https://github.com/Gauravv97/Android-Portrait-Blur-using-DeeplabV3--Semantic-Image-Segmentation-/raw/master/apk/v0.0.2/CameraBlur%201025px.apk)

## Demo

![Demo](SampleImages/Demo.gif)

## Some Samples

<p align="center">
    <img src="SampleImages/Image1.jpg" width="49%">   <img src="SampleImages/Blurred1.jpg" width="49%"></br>
    <img src="SampleImages/Image2.jpeg" width="49%">   <img src="SampleImages/Blurred2.jpg" width="49%"></br>
    
</p>


## Features

* Select image from storage or click them using camera
* Blur a variety of subjects (most centered subject will be selected rest will be background).
* SoftBlur around edges

## For developers

I have 3 pre trained models of diffrent crop sizes `Default 1025 px`. You can use any one of them but with increased crop size the processing time also increases (by a lot), so use them as per your requirement. Crop size is the size of image that the input image will be resized to and sent for processing. The output dimensions are always less than crop size.

For using 1536 px: Copy `InputSize 1536px\frozen_inference_graph.pb`and paste it in `CameraBlur\app\src\main\assets\`.

Then change 
`CameraBlur\app\src\main\java\com\anondev\gaurav\camerablur\DeeplabProcessor.java`line 28 

From 

	public final static int INPUT_SIZE = 1025;

to 

	public final static int INPUT_SIZE = 1536; 
## Attributions/Thanks/External code

This application wouldn't be possible without the great material produced by the community. I would like to give special thanks to the authors of essencial parts I've got on the internet and used in the code:

- DeepLabv3+:
```
@article{deeplabv3plus2018,
  title={Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation},
  author={Liang-Chieh Chen and Yukun Zhu and George Papandreou and Florian Schroff and Hartwig Adam},
  journal={arXiv:1802.02611},
  year={2018}
}
```

- MobileNetv2:

```
@inproceedings{mobilenetv22018,
  title={Inverted Residuals and Linear Bottlenecks: Mobile Networks for Classification, Detection and Segmentation},
  author={Mark Sandler and Andrew Howard and Menglong Zhu and Andrey Zhmoginov and Liang-Chieh Chen},
  booktitle={CVPR},
  year={2018}
}
```



* [Tensorflow's deeplab](https://github.com/tensorflow/models/tree/master/research/deeplab)
* A special thanks to [dailystudio for implementing mobilenet model on TFMobile](https://github.com/dailystudio/ml/tree/master/deeplab) without his help this project wouldn't have been sucessful. Also Without the advice given by [Liang-Chieh Chen](https://github.com/aquariusjay), we couldn't have successfully exported the model to mobile devices.
* [Stack Blur Algorithm by Mario Klingemann](http://quasimondo.com)

## Photo Credits

* Marcus Pinho, [Pexels](https://www.pexels.com/photo/woman-wearing-red-and-black-feather-hat-923345/)

* Sonnie Hiles, [unsplash](https://unsplash.com/photos/10wjs03JJv8)

## About

Copyright 2018 Gaurav Chaudhari, and licensed under the Apache License, Version 2.0. No attribution is necessary but it's very much appreciated. Star this project if you like it!



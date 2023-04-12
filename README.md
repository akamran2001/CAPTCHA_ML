# CAPTCHA_ML
- Using Machine Learning to train models that indentify different types of CAPTCHAs

# Models

## Alphanumeric CAPTCHAs
- ```letter_captchas.ipynb``` classifies CAPTCHAs composed of letters and numbers 

## Goggle reCAPTCHAs
- ```recaptcha.ipynb``` classifies Google reCAPTCHAs composes of images of real world objects
- Uses a pre-trained image segmentation [model](https://github.com/CSAILVision/semantic-segmentation-pytorch) trained on the MIT image segmentation datatset with over 150 classes
- Is able to solved 3x3 captchas composed of multiple images, of 4x4 captchas where one image is broken down into a grid
- ![reCAPTCHA examples](https://developers.nopecha.com/static/recaptcha.png)
- Install model ```pip install git+https://github.com/CSAILVision/semantic-segmentation-pytorch.git@master```
  
## Image CAPTCHAs (outdated)
- ```image_captchas.ipynb``` classifies CAPTCHAs that are images of objects in real life 
- Our first attempt at classifying images of real world objects
- Low accuracy (hovering aaround 50%)
- Limited number of classes in our [dataset](https://www.kaggle.com/datasets/mikhailma/test-dataset)
  
## CAPTCHA Classifier
- ```captcha_type.ipynb``` classifies if a CAPTCHA is alphanumeric, 3x3 reCAPTCHA (non segmented images) or 4x4 reCAPTCHA (one segmented image)

## Complete Pipeline
- ```main.ipynb``` combines our previous models to classify any of the 3 types of CAPTCHAs

# Helpers

## Web Scraper
- ```scrape.ipynb``` Scrapes the Google [reCAPTCHA demo](https://www.google.com/recaptcha/api2/demo) to get hundreds of images of CAPTCHAs used by Google. These images are labeled by what the CAPTCHA is asking the user to look for

## Captcha Generator
- ```gen_captcha.ipynb``` uses the images in the Kaggle [dataset](https://www.kaggle.com/datasets/mikhailma/test-dataset) of image based CAPTCHAs to generate 3x3 CAPTCHA images that can be used for training. Web scraping gives us better data but given our large existing dataset this is a fast way to get CAPTCHAs without scraping the web.

# Data Sources
- Alphanumeric CAPTCHAs from Kaggle https://www.kaggle.com/datasets/fournierp/captcha-version-2-images
- Google ReCaptcha dataset of image based CAPTCHAs from kaggle https://www.kaggle.com/datasets/mikhailma/test-dataset
- Google' reCAPTCHA demo for CAPTCHA images used in the real world https://www.google.com/recaptcha/api2/demo
  
# Model Credits
- Pre-trained image segmentation [model](https://github.com/CSAILVision/semantic-segmentation-pytorch) trained on the MIT image segmentation datatset with over 150 classes
- Weights for the pre-trained model http://sceneparsing.csail.mit.edu/model/pytorch/ade20k-resnet50dilated-ppm_deepsup/
- References for pre trained model
  - Semantic Understanding of Scenes through ADE20K Dataset. B. Zhou, H. Zhao, X. Puig, T. Xiao, S. Fidler, A. Barriuso and A. Torralba. International Journal on Computer Vision (IJCV), 2018. (https://arxiv.org/pdf/1608.05442.pdf)
  - Scene Parsing through ADE20K Dataset. B. Zhou, H. Zhao, X. Puig, S. Fidler, A. Barriuso and A. Torralba. Computer Vision and Pattern Recognition (CVPR), 2017. (http://people.csail.mit.edu/bzhou/publication/scene-parse-camera-ready.pdf)
- Inspiration for model design of Alphanumeric CAPTCHA classifier https://github.com/DrMahdiRezaei/Deep-CAPTCHA/blob/master/Captcha_Solver_numerical.ipynb
# CAPTCHA_ML
<<<<<<< HEAD
- Using Machine Learning to train models that indentify different types of CAPTCHAs

## Alphanumeric CAPTCHAs
- ```letter_captchas.ipynb``` classifies CAPTCHAs composed of letters and numbers 
  
## Image CAPTCHAs
- ```image_captchas.ipynb``` classifies CAPTCHAs that are images of objects in real life 
  
## Alphanumeric or Image CAPTCHAs
- ```letter_or_image.ipynb``` classifies if a CAPTCHA is alphanumeric or image based 

## Data Sources
- Alphanumeric CAPTCHAs from Kaggle https://www.kaggle.com/datasets/fournierp/captcha-version-2-images
- Google ReCaptcha dataset of image based CAPTCHAs from kaggle https://www.kaggle.com/datasets/mikhailma/test-dataset

## Folder structure
```
+-captchas/
  |
  +-letters/
  | |
  | +-p5g5m.png
  | |
  | +-e72cd.png
  | |
  | +-pgmn2.png
  | |
  | +-6cm6m.png
  | |
  | +-68wfd.png
  | |
  | +-... <additional files>
  |
  |
  |
  +-images/
    |
    +-Hydrant/
    | |
    | +-Hydrant (431).png
    | |
    | +-Hydrant (962).png
    | |
    | +-Hydrant (827).png
    | |
    | +-Hydrant (574).png
    | |
    | +-... <additional files>
    |
    +-Car/
    | |
    | +-Car (1964).png
    | |
    | +-Car (25).png
    | |
    | +-Car (1067).png
    | |
    | +-Car (958).png
    | |
    | +-... <additional files>
    |
    |
    |
    +-Bridge/
    | |
    | +-Bridge (180).png
    | |
    | +-Bridge (495).png
    | |
    | +-Bridge (27).png
    | |
    | +-... <additional files>
    |
    +-Stair/
    | |
    | +-Stair (1491).png
    | |
    | +-Stair (48).png
    | |
    | +-Stair (1468).png
    | |
    | +-... <additional files>
    |
    +-Other/
    | |
    | +-Other (1029).png
    | |
    | +-Other (537).png
    | |
    | +-Other (167).png
    | |
    | +-... <additional files>
    |
    +-Motorcycle/
    | |
    | +-Motorcycle (64).png
    | |
    | +-Motorcycle (72).png
    | |
    | +-Motorcycle (48).png
    | |
    | +-... <additional files>
    |
    +-Bus/
    | |
    | +-Bus (360).png
    | |
    | +-Bus (730).png
    | |
    | +-Bus (225).png
    | |
    | +-... <additional files>
    |
    +-Chimney/
    | |
    | +-Chimney (21).png
    | |
    | +-Chimney (126).png
    | |
    | +-Chimney (99).png
    | |
    | +-... <additional files>
    |
    +-Bicycle/
    | |
    | +-Bicycle (108).png
    | |
    | +-Bicycle (558).png
    | |
    | +-Bicycle (734).png
    | |
    | +-... <additional files>
    |
    +-Crosswalk/
    | |
    | +-Cross (669).png
    | |
    | +-Cross (393).png
    | |
    | +-Cross (239).png
    | |
    | +-... <additional files>
    |
    +-Traffic Light/
    | |
    | +-Tlight (409).png
    | |
    | +-Tlight (370).png
    | |
    | +-Tlight (720).png
    | |
    | +-... <additional files>
    |
    +-Palm/
      |
      +-Palm (577).png
      |
      +-Palm (127).png
      |
      +-Palm (824).png
      |
      +-... <additional files>
```
=======
## Models

### Alphanumeric CAPTCHAs
- `letter_captchas.ipynb` classifies CAPTCHAs composed of letters and numbers. 
- Example:
  
  !['Letter Captcha Accuracy'](outputs/letter_captchas.png)

### Google reCAPTCHAs
- `recaptcha.ipynb` classifies Google reCAPTCHAs composed of images of real-world objects.
- Uses a pre-trained image segmentation model trained on the MIT image segmentation dataset with over 150 classes.
- Is able to solve 3x3 captchas composed of multiple images, of 4x4 captchas where one image is broken down into a grid.
- ![reCAPTCHA examples](https://developers.nopecha.com/static/recaptcha.png)

- Examples:
    - !['Bus'](outputs/recaptcha_bus.png)
    - !['Car'](outputs/recaptcha_car.png)
    - !['Hill'](outputs/recaptcha_hill.png)
    - !['Traffic'](outputs/recaptcha_traffic.png)

### Image CAPTCHAs (outdated)
- `image_captchas.ipynb` classifies CAPTCHAs that are images of objects in real life. 
- This was our first attempt at classifying images of real-world objects.
- Has low accuracy (hovering around 50%).
- Has a limited number of classes in our dataset: https://www.kaggle.com/datasets/mikhailma/test-dataset
  
### CAPTCHA Classifier
- `captcha_type.ipynb` classifies if a CAPTCHA is alphanumeric, 3x3 reCAPTCHA (non-segmented images), or 4x4 reCAPTCHA (one segmented image).

### Complete Pipeline
- `main.ipynb` combines our previous models to classify any of the 3 types of CAPTCHAs.

## Helpers

### Web Scraper
- `scrape.ipynb` scrapes the Google reCAPTCHA demo to get hundreds of images of CAPTCHAs used by Google. These images are labeled by what the CAPTCHA is asking the user to look for.

### CAPTCHA Generator
- `gen_captcha.ipynb` uses the images in the Kaggle dataset of image-based CAPTCHAs to generate 3x3 CAPTCHA images that can be used for training. Web scraping gives us better data, but given our large existing dataset, this is a fast way to get CAPTCHAs without scraping the web.

## Data Sources
- Alphanumeric CAPTCHAs from Kaggle: https://www.kaggle.com/datasets/fournierp/captcha-version-2-images
- Google reCAPTCHA dataset of image-based CAPTCHAs from Kaggle: https://www.kaggle.com/datasets/mikhailma/test-dataset
- Google reCAPTCHA demo for CAPTCHA images used in the real world: https://www.google.com/recaptcha/api2/demo
  

  
## Model Credits
- Pre-trained image segmentation [model](https://github.com/CSAILVision/semantic-segmentation-pytorch) trained on the MIT image segmentation datatset with over 150 classes
- Weights for the pre-trained model http://sceneparsing.csail.mit.edu/model/pytorch/ade20k-resnet50dilated-ppm_deepsup/
- References for pre trained model
  - Semantic Understanding of Scenes through ADE20K Dataset. B. Zhou, H. Zhao, X. Puig, T. Xiao, S. Fidler, A. Barriuso and A. Torralba. International Journal on Computer Vision (IJCV), 2018. (https://arxiv.org/pdf/1608.05442.pdf)
  - Scene Parsing through ADE20K Dataset. B. Zhou, H. Zhao, X. Puig, S. Fidler, A. Barriuso and A. Torralba. Computer Vision and Pattern Recognition (CVPR), 2017. (http://people.csail.mit.edu/bzhou/publication/scene-parse-camera-ready.pdf)
- Inspiration for model design of Alphanumeric CAPTCHA classifier https://github.com/DrMahdiRezaei/Deep-CAPTCHA/blob/master/Captcha_Solver_numerical.ipynb

# Usage
- Download all the required libraries using ```pip install -r requirements.txt```
- Install [tensorflow](https://www.tensorflow.org/install)
>>>>>>> segmentation

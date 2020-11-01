# TRY-IT Mobile Application
![LOGO](https://github.com/AnandShivansh/TRY-IT/blob/master/app/src/main/ic_launcher-playstore.png)


## Description
TRY-IT is a virtual dressing room application for >= Android 6.0.

It allows users to see how an outfit will look on them by using image processing and a body pose-estimation model.

<br/><br/>
## Screenshots
<br>  <img src="https://github.com/AnandShivansh/TRY-IT/blob/master/Screenshots/MainPage.jpeg" height=650 width=300>
 <img src="https://github.com/AnandShivansh/TRY-IT/blob/master/Screenshots/AddOutFit_from_gallery.jpeg" height=650 width=300>
<img src="https://github.com/AnandShivansh/TRY-IT/blob/master/Screenshots/Share_from_online_store.jpeg" height=650 width=300>
<img src="https://github.com/AnandShivansh/TRY-IT/blob/master/Screenshots/Select_outfit.jpeg" height=650 width=300></br>
<img src="https://github.com/AnandShivansh/TRY-IT/blob/master/Screenshots/Camera_Preview.jpeg" height=650 width=300></br>

<br/><br/>
## How does it work ?
### Add Outfit
TRY-IT allows users to add their own outfit from gallery.<br/>
The selected outfit is processed according to a sensitivity rate given by the user.<br/>
User selects a category to store outfit.<br/>
The outfit stored in database.<br/><br/>

Image processing methods to extract outfit given below;
  * Add alpha channel to image
  * Boolean Masking (Binary Threshold)
  * Noise Removal (Gaussian Blur)
  * Generate mask to make background transparent
  * Apply generated mask
  * Find largest contour to remove unnecessary area
  * Crop largest contour

### Fit Outfit on Camera Preview
TRY-IT uses a tensorflow-lite model to estimate certain points on user's body during camera preview.<br/> 
By using these estimated points, the outfit is placed on screen by calculating its size and position.<br/><br/>


The model estimates 14 points on user's body;<br/> 
_Top, Neck, Left Shoulder, Left Elbow, Left Wrist, Right Shoulder, Right Elbow, Right Wrist, Left Hip, Left Knee, Left Ankle, Right Hip, Right Knee, Right Ankle._<br/><br/>


There are 4 outfit categories;<br/>
_"Top", "Long Wears", "Trousers", "Shorts and Skirts"_
<br/><br/>

According to its category, the outfit size and position are calculated by using;<br/>
* Top --> Left Shoulder, Right Shoulder, Left Hip
* Long Wears --> Left Shoulder, Right Shoulder, Left Knee
* Trousers --> Left Hip, Right Hip, Left Ankle
* Shorts and Skirts --> Left Hip, Right Hip, Left Knee


<br/><br/>
## Software and Tools
* Android Studio 3.2.1
* TensorFlow-Lite
* OpenCV 4.1
* SQLite


<br/><br/>
## Future Development
  ### Functional
  * Users will be allowed to create outfit combinations
  * Users will be allowed to take screenshot during preview with a button

  ### System
  * Semantic segmentation to extract outfit in a more efficient way
  * 3D modeling for a more realistic result
  * Sharing the outfit image from various online stores and trying them at home by using jsoup

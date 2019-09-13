# Write-up Hackathon(Engagement Quotient)

Record of all notable cases

## Various Face Detection methods

* Haar Cascade Face Detector in OpenCV
* DNN Face Detector in OpenCV
* HoG Face Detector in Dlib

### 1. Haar Cascade Face Detector in OpenCV
Haar Cascade classifier is based on the Haar Wavelet technique to analyse pixels in the image into squares by function. This uses “integral image” concepts to compute the “features” detected. Haar Cascades use the Ada-boost learning algorithm which selects a small number of important features from a large set to give an efficient result of classifiers then use cascading techniques to detect face in a image.

* **Pros**
  * Simple Architecture
  * Detects faces at different scales

* **Cons**
  * The major drawback of this method is that it gives a lot of False predictions.
  * Doesn’t work on non-frontal images.
  * Doesn’t work under occlusion

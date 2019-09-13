# Write-up Hackathon(Engagement Quotient)

Record of all notable cases

## Various Face Detection methods

* Haar Cascade Face Detector in OpenCV
* DNN Face Detector in OpenCV


##

### 1. Haar Cascade Face Detector in OpenCV
Haar Cascade classifier is based on the Haar Wavelet technique to analyse pixels in the image into squares by function. This uses “integral image” concepts to compute the “features” detected. Haar Cascades use the Ada-boost learning algorithm which selects a small number of important features from a large set to give an efficient result of classifiers then use cascading techniques to detect face in a image.

* **Pros**
  * Simple Architecture
  * Detects faces at different scales

* **Cons**
  * The major drawback of this method is that it gives a lot of False predictions.
  * Doesn’t work on non-frontal images.
  * Doesn’t work under occlusion


### 2. DNN Face Detector in OpenCV
This model is based on Single-Shot-Multibox detector and uses ResNet-10 Architecture as backbone. The model was trained using images available from the web. We use caffemodel and prototxt files for loading caffe model. The model used is of resolution of 300x300, Hence, we resize the frames to 300x300. The frame is converted to a blob and passed through the network using the forward() function. The output detections is a 4-D matrix, where
* The 3rd dimension iterates over the detected faces(detections.shape[2]).
* The fourth dimension contains information about the bounding box and score for each face. For example, detections[0,0,i,2] gives the confidence score for the first face, and detections[0,0,i,3:7] give the bounding box.
The output coordinates of the bounding box are normalized between [0,1]. Thus the coordinates should be multiplied by the height and width of the original image to get the correct bounding box on the image.

* **Pros**
	* Most accurate
	* Runs at real-time on CPU
	* Works for different face orientations – up, down, left, right, side-face etc.
	* Works even under substantial occlusion
	* Detects faces across various scales ( detects big as well as tiny faces )

##

The DNN based detector overcomes all the drawbacks of Haar cascade based detector, without compromising on any benefit provided by Haar.

## Live Videostream

* **Odomantus**
	* The Odomantus is added to meeting as test user to take snapshots of the live meeting.
	* Odomantus only takes snapshots for first 20 seconds of the meeting.(Approx. 20 snapshots)
	* It does not work properly when the TP end point has more than one camera.
* The meeting is not recorded unless some content is shared or active speaker is present....the bug is somewhere along the line. 


## Automatic Recognition of Indian Sign Language in Video

Research Paper can be downloaded from the  [**link**](http://csi-india.org.in/communications/Dr.%20Anand%20Singh%20Jalal.pdf).

The aim of this research paper is to design a user independent framework for **automatic recognition of Indian Sign Language** which is capable of recognizing various one handed dynamic isolated signs and interpreting their meaning. 


![Screenshot (312).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626088556006/gM2F9IpTs.png)

The proposed approach consists majorly of three steps: 
preprocessing, feature extraction and recognition.

### Previous work

Mr. Agrawal proposed a two stage recognition approach for 23 alphabets. Signs are produced by wearing red gloves on both hands for segmentation purposes. The segmented images serve as an input to the feature extraction and recognition phase. <br>

In ***stage-I***, the features that are describing the overall shape of gestures were calculated and recognition is done through training feature vector without the use of any classifier. <br>
In ***stage-II***, a recognition criterion was tough and the feature vector had a binary coefficient. <br>
***Finally***, an output was given whether the gesture is correct or not. <br>

M.A. Mohandes proposed a method for the recognition of the two handed Arabic signs using the Cyber Glove and support vector machine. Principal Component Analysis (PCA) feature is used for feature extraction. 
This method is consisting of 20 samples of 100 sign by one signer. 
15 samples of each sign were used for training a Support Vector Machine to perform the recognition. 
The system was tested on the remaining 5 samples of each sign. <br>
A recognition rate of 99.6% on the testing data was obtained.

![Screenshot (311).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626088847578/Fomqq7iO0.png)
**Figure**: Approaches in Sign Language Recognition a) Glove based b) Vision based

**Note**:  Several methods have been proposed to solve the three main problems of vision-based gestural interfaces, namely hand segmentation and detection, tracking and recognition.

#### Proposed Methodology
 The three main components of this framework are preprocessing module, feature extraction module and recognition module. 

![Screenshot (299).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626089152576/4DU0CImCv.png)
**Figure**: Framework of proposed system

In the **first step**, i.e. the preprocessing, skin color detection is done followed by face elimination and key frame extraction.<br>
In **feature extraction** phase, various hand shape features like circularity, extent, convex deficiency and hand orientation are considered. <br>
For **hand motion**, a new feature is proposed called the Motion Direction Code. <br>
Finally, in the **recognition** phase, a Multiclass Support Vector Machine is used to classify the signs and recognize them. 

### Preprocessing
#### Hand Detection by Face elimination


![Screenshot (300).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090114003/AN-Xf8GUZ.png)
*Figure**: Hand Segmentation Algorithm

#### Key frame Extraction 



![Screenshot (301).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626089554660/Qw9o6z6j0.png)
**Figure**: Illustration of preprocessing steps (a) Sample 12 frames from Video
sequences of sign “Only” from our data set (b) Skin color segmentation result (c) Hand
detection result <br>


The basic approach is to select frames from video in which there is a significant change in either position or shape. <br>

![Screenshot (302).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626089647334/2nAkwt-Ly.png)
**Figure**: Frames extracted by the key frame extraction algorithm


![Screenshot (303).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626089783705/jKYn4VTnz.png)
**Figure**: Key frame Extraction Algorithm

For **position change**, the centroid feature is taken into account.  The *centroid of every frame* is computed and the distance between the centroid of every frame (starting from the first) and its successive frame is computed. If the distance is greater than a particular threshold, then the frame is selected, otherwise, it is skipped. Here, the threshold used can’t be fixed or kept static as the amount of change in position varies with every sign. So dynamic threshold (Dth) is used, which is calculated as a function of the average distance between the centroid of every keyframe. 

### Feature Extraction
#### Hand Motion
**Motion Direction Code**<br>

![Screenshot (304).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090259710/CTMfmGYPx.png)
**Figure**: Motion direction for key frames

MDC is the concatenation of all these numbers depicting the code for hand motion trajectory.

![Screenshot (305).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090368729/JBeMaZ9Pj.png)
**Figure**: Sequence of numbers assigned to motion trajectory


![Screenshot (306).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090494897/PFfe0lQta.png)
**Figure**: Algorithm to computer MDC

### Recognition
#### Multi-clas Support Vector Machine
SVM as a classifier is gaining popularity because of its various features like the ability to accurately separate the classes even for a large dataset with small training samples. <br>
SVMs have applications in pattern recognition like face detection, handwritten digit and character recognition, information and image retrieval, gender classification, prediction, text detection and categorization, and many more. 

### Results


![Screenshot (308).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090687160/pbzn1jAP1.png)


![Screenshot (309).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090740610/YIiDMCfvz.png)

**Figure**: Snapshot of GUI depicting the result of multiple signs by multiple signers.

![Screenshot (310).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1626090897621/iCfv5w0S5.png)

**Figure**: Classification results of the proposed approach.
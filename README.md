# Object-Detection-Using-YOLOv3-Algorithm



ABSTRACT
Unnamed aerial vehicles are widely being used in monitoring traffic signals and are in surveillance.  With the Arrival of deep learning, the Accuracy of object detection has increased drastically. Today self-driving vehicles need real time object detection with high accuracy. Traditional object detection based algorithms follow a procedure where the object has to be passed in various layers which are very slow. CNN based methods like faster-RCNN provide very high accuracy. YOLO is single stage object detection algorithm as the name suggests You Only look Once. The enhanced version of YOLO are YOLOv2 and YOLOv3 which are comparatively very accurate and provide high speed object detection as it reduces the number of layers in network. This paper is concerned with object detection with YOLOv3 algorithm which is a high end object detection algorithm. YOLOv3 may not be one of the most accurate algorithms but it is very useful in the context of the self-driving cars which needs real time object detection, without loss of too much of the accuracy. The difference between recognition and detection algorithms is that a recognition algorithm does only predict the class labels while detection algorithm also predicts the location of the object. As YOLO only uses the convolutional layers that makes it fully convolutional network (FCN).

INTRODUCTION
Object detection is a computer technology which is used for detecting real time object in the environment, the object can be in real time environment or image or video. The major achievements of object detection are of real time object and pedestrian detection. It is used in computer task such as face detection, recognizing face, video object co-segmentation. It is also widely used in putting a track on  objects, for example tracking a ball during a basketball match, tracking movement  of a footballer legs, or tracking movement of beings. 

 
PROBLEM IDENTIFICATION:-
There are different methodologies which are utilized beforehand for the object detection and recognition. The first approach is called as divide and conquers approach in which the locale is separated into four areas and all the district are gone through the convolutional neural network. The accompanying region go from that are then prepared and the area in which item is identified is set apart from others. This methodology was not effective as this only feature the zone where item was available. 
Another methodology was the successor of the primary methodology where the system chooses area was again partitioned into four regions and from that four another regions are wretched. Again, the chosen area is partitioned into four locales until we get our article. The issue with this methodology was that there were many numbers of boxes which make much confusion.

RCNN: - RCNN is successor methodology of object detection in which there are three functions that this algorithm process. In the very first step we input the image and then convolutional neural network. Then the image is divided into frames and by and region of interest are selected by some predefined method like selective search. And then these frames are passed in CONVNET and in the next step we reshape the frames to give to next step and these ROI are recognized by the class specifiers. RCNN utilizes specific hunt to remove these containers from an image (these boxes are called areas).

Fast RCNN: - Fast RCNN is the updated version of RCNN which came later this year. As we know R-CNN, Fast R-CNN uses  Selective search approach to make object propose but instead of this extract all of them simultaneously and using SVM classifiers, it concentrated the CNN on the complete image processing and then made use of all ROI Pooling on the map of specifications with a finalized feed forward toward network in order to lift on classification and regression. Following technique came out to be a much faster and due to the ROI pooling, it become point to point differentiable and a lot easy to train the model. But there was still a big drawback to this method as it still relied on Selective Search.

LITERARTURE SURVEY: -
1.	 This paper introduces RCNN and fast RCNN and seen the drawback and limitations in these algorithms. Later introduced Yolo v2 and Yolo 9000 immediate detection algorithms. Yolov2 is one of its kind and faster than other algorithms. It can run on variety of image size. YOLO 9000 is an ultimate algorithm for detecting objects over count than 9000 objects by optimizing detection and classify it, we use the word tree for combining dataset from many joint and source optimization technique to make module train it simultaneously on coco and ImageNet. YOLO9000 makes a big leap towards closing the data size gap between the classification and detection.

DATA REPRESENTATION IN COCO IMAGENET AND WORDTREE:-
 
2.	Most of our techniques is generalize extent of object detection. Our word tree represents the ImageNet with richer and enhanced comprehensive output for space image classification, data-set combination uses the hierarchic classification. It can be used in segmentation and classification domains. Training technique like multi scale learning could provide the opportunity over the many visual task. 
3.	This paper focuses on improving the detection result with the help of another powerful matching algorithm for allocating weak labels for classification of data at the time of training. Computer vision is inherited with the massive amount of leveled data. This paper will keep on looking another method to bring different sources and structure of data at a place to make a stronger model to virtual world.  

PROPOSED METHODOLOGY
The best algorithm for object detection before the introduction of YOLOV3 was the YOLO9000 which can process 9000 objects in an image within a fraction of second. When we look into other algorithm for object detection like fast - RCNN, which used to carry out detection on many region proposals and therefore ends up achieving the predicted image many times on various grids in the image, YOLO architectures is much more likely fully Convolutional Neural Network (FCNN). A single-handed convolutional network is focused on the particular image. The network segments the image into many grids. This is further divided into regions and bounding boxes with probabilities of different region and category. The bounding boxes which are generated are then used to predict by the weights of the probability measured, due to comparisons applied with the SVM. As an only convolutional neural network is used to predict the multiple bounding boxes, the work is completed much faster as compared to other algorithms. YOLO works on complete images and it directly increases the performance. This model helps in object detection which has several benefits over other methods used on object detection. YOLO v2 used  darknet-19 in which there are 19 layer network supplemented and 11 extra layers for object detection. YOLO v3 uses a different Darknet which has 53 layer network trained on Imagenet. For detection 53 extra layers are added into it which gives us 106 layer those are fully convolutional underlying architecture for the Algorithm. That is why YOLO v3 is slower in comparison  to YOLO v2.
 
The newer architecture that are introduced  ostentation of residual skip connections, and up sampling. The most important feature of v3 is that it makes detections at three different scales. In YOLO v3, the discovery is finished by applying 1 x 1 recognition portions on include maps of three unique sizes at three better places in the system. The state of the discovery part is 1 x 1 x (B x (5 + C) ). Here B is the quantity of jumping boxes a cell on the element guide can foresee, "5" is for the 4 bouncing box traits and one article certainty, and C is the quantity of classes. In YOLO v3 prepared on COCO, B = 3 and C = 80, so the part size is 1 x 1 x 255. The component map created by this part has indistinguishable stature and width of the past element maps, and has identification qualities along the profundity as depicted previously.   

YOLO v3 makes forecast at three scales, which are accurately given by down examining the elements of the info picture by 32, 16 and 8 individually. 

The main identification is made by the 82nd layer. For the initial 81 layers, the picture is down examined by the system, with the end goal that the 81st layer has a step of 32. In the event that we have a picture of 416 x 416, the resultant element guide would be of size 13 x 13. One discovery is made here utilizing the 1 x 1 location part, giving us an identification include guide of 13 x 13 x 255.Then, the element map from layer 79 is exposed to a couple convolutional layers before being up tested by 2x to components of 26 x 26. This component map is then profundity linked with the element map from layer 61. At that point the joined element maps is again oppressed two or three 1 x 1 convolutional layers to combine the highlights from the previous layer (61). At that point, the subsequent location is made by the 94th layer, yielding a discovery include guide of 26 x 26 x 255. 

A comparable methodology is followed once more, where the element map from layer 91 is exposed to not many convolutional layers before being profundity connected with a component map from layer 36. Like previously, a couple 1 x 1 convolutional layers follow to meld the data from the past layer (36). We make the last of the 3 at 106th layer, yielding component guide of size 52 x 52 x 255. 
In this Algorithm 13 x 13 layer distinguishes huge items 52 x 52 layer identifies littler articles and 26 x 26 layer recognizes the medium size articles. 
This all out utilizations 9 boxes you should wind up utilizing K-Means bunching to create 9 grapple boxes in the event that you are utilizing your own dataset.

Loss Function

 Loss function in YOLO v2 was like this-
 


The Changes are there in YOLO v3 loss Function-
	
 


CONCLUSION
 
We present YOLOv2 and YOLO9000, continuous identification frameworks. YOLOv2 is cutting edge and quicker than other identification frameworks over an assortment of discovery datasets. Moreover, it tends to be kept running at an assortment of picture 
sizes to give a smooth tradeoff among precision and speed . YOLO 9000 is a continuous structure for recognition for objects counted  than 9000 item classes by together advancing recognition furthermore, order. We also use WordTree for consolidate information from different sources and our joint streamlining method to prepare at the same time on coco and imagNet. YOLO 9000 is a solid advance regarding shutting the dataset size hole among identification and characterization. 
A considerable lot of our systems sum up outside of item discovery. Our Word Tree portrayal of ImageNet offers a more extravagant, increasingly point by point yield space for picture order. Dataset blend utilizing progressive order would 
be valuable in the grouping and division spaces. Preparing systems like multi-scale preparing could give advantage over an assortment of visual undertakings. 
For the updates we plan to utilize comparative methods for pitifully directed picture division. We additionally plan to improve our location results utilizing all the more dominant coordinating methodologies for allocating feeble marks to arrangement information during preparing. PC vision is honored with a gigantic measure of named information. This paper will keep looking for approaches to bring various sources and structures of information to make more grounded methods of the visual world.





# Live Streaming From DJI Drone and Plant Disease Diagnostics on Server, Raspberry Pi and Android Phone
![System Architecture](https://github.com/SomiaImdad/Plant-Disease-Diagnostics-using-UAV-and-Android-APP/blob/master/diagram.jpg)
Plant diseases causes many significant damages and losses in crops around the world. Some suitable measures on disease identification should be introduced to prevent damages and minimize losses. Early Detection of Disease helps in increasing the crop productivity as well as in minimizing expense. Technical approaches using machine learning and computer vision are actively researched to achieve intelligence farming by early detection on plant disease. The accuracy of object detection and recognition systems has been drastically improved by the recent development in Deep Neural Networks. By using these systems and implementation of computer vision and machine learning techniques, plant diseases can be detected. Here we have used transfer learning based approach to diagnose diseases of different plants using its images captured by camera devices either drone or smartphone. Our goal is to build a market oriented product for Plant Disease Detection, a smartphone app compatible with both smartphone camera and drone camera. The target group of the user is those who request a quick diagnosis on common leaf disease at any time of the day i.e. Farmers, agricultural industries, agricultural consultants and Government Agencies &amp; Departments.
In agriculture sector, plant diseases and pests are a major challenge. An accurate and fast detection of plants diseases could help to develop an early treatment method while at the same time significantly reducing economic losses. 
Techniques based on image processing are used to detect plant diseases without causing any secondary impact in plant. However, the accuracy is still a challenge in Computer Vision. In intelligent systems, most important issue is the use of proper dataset. Our technique is applicable on all kinds of plants but for testing, we focus on the recognition and identification of diseases that affect tomato plants (we are not working on pest detection due to lack of dataset). Economically, tomato is the most important vegetable crop around the world, and its production has been significantly increased through the years. Several diseases that affect tomato plants are the main part of this study. Testing is done on some samples of our collected dataset which contains different diseases of tomato plants. The tomato diseases on which testing is done are late blight and bacterial spot. 
It is a transfer learning-based approach in order to detect diseases in tomato plants using drone or smartphone camera. It will help the Farmers, agricultural industries, agricultural consultants and Government Agencies & Departments to perform quick diagnosis on common leaf disease at any time. Most probably this is the first time someone doing in the UET Taxila.
Our system uses images of diseased plants taken from different tomato farms and fields, thus we don’t need to analyze samples in laboratory. We collected dataset of images gathered from fields and greenhouses using drone and android mobile camera. Techniques like image annotation, image augmentation are applied on images to increase the dataset and accuracy of images. For training those images, an open-source software library called Tensor Flow is used. Farmers will be able to take advantage from this application whenever they want early detection of plants diseases, they can do it easily by using android app. 
MedCrafter AGRI-DRONE has following features: 
1.	Detect plant disease more precisely. 
2.	Save time required for infield scouting & actions. 
3.	Help the farmer to identify crop’s progress accurately and in replanting decisions. 
4.	Help in preventing unnecessary waste of financial resources. 
5.	Smart phone diagnostic app will keep farmer updated about crop at a single click. 
Since this project is android based also, so users can access this tool from multiple android devices to recognize different image targets. This application just requires input images captured by various camera devices with different resolutions, such as cell phone and other digital cameras. The goal of this project is to develop a market-oriented product for Plant Disease Diagnosis, a smartphone app compatible with both smartphone camera and drone camera. Moreover, it can efficiently deal with different size of objects, different illumination conditions and background variations contained in the surrounding areas of diseased plant. This is not much time consuming as compared to older ways of plant disease detection techniques. The idea is productive and as well as innovative. Application like this is never created in the history of UET Taxila.  
The MedCrafter AGRI-DRONE provides a practical and real time market-oriented product that can be used in different fields without employing any complex and expensive technology. It also considers the possibility that a plant can be simultaneously affected by more than one disease in the same plant.  

Group Members: 
Somia Imdad (14-CS-50) https://github.com/SomiaImdad (14-CS-50@uettaxila.edu.pk)
Muhammad Usama bin Islam (14-CS-66) https://github.com/UsamaIslam (14-CS-66@uettaxila.edu.pk)
Abdul Haseeb (14-CS-03) https://github.com/Rad1C4L (14-CS-03@students.uettaxila.edu.pk)

Biggest Achievement is streaming live video using DJI drone to PC for disease detection. 
Code will be uploaded soon.

Working (Got help from DJI documentation):
On Live feed
For live feed video same process is followed. The only obstacle is to livestream the video 
from the drone to the mobile phone. Which is achieved by following these steps
1. First, we initialize and set the instance as NativeDataListener to receive the frame 
data.
2. Then we send the data from camera to the ffmpeg library for parsing of individual 
frames.
3. Then we get the parsed data from ffmpeg and cache the data to a frameQueue
4. Now we initialize MediaCodec as decoder and then check whether there is any i-
frame in the MediaCodec. If not, then we get the default i-frame from the SDK 
resources and insert it at the head of the frame queue. Then dequeue the framed data 
from frameQueue and then feed it into the MediaCodec.
5. Get the output byte buffer from MediaCodec, if a surface is available for viewing the 
video and is configured by the MediaCodec, the output byte buffer only needs to be 
released. If not, the output YUV data should invoke the callback and pass it out to 
external listener, it should also be released.
6. Release the ffmpeg and the Media Codec, Stop the decoding thread.
The YUV data is then compressed into JPEG image and streamed to server in form of 
MJPEG (motion JPEG)

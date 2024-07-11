# Moving Object Detection and Speed Tracking

This repository contains the code and data for the project "Moving Object Detection and Speed Tracking," which focuses on identifying vehicles and calculating their speed using camera videos for traffic surveillance.

Description

Traffic surveillance systems are crucial for safety and security, but traditional methods can be expensive and ineffective. This project aims to improve surveillance by implementing advanced moving object detection and speed tracking algorithms using videos from mounted cameras. The project explores various detection approaches, focusing on background subtraction to identify changes in object positions and calculate their speeds. This method ensures accurate detection and tracking, providing a more efficient solution for traffic surveillance.

Technologies Used

Python
OpenCV
dlib
Tasks Breakdown

Vehicle Detection
We are using the Haarcascade classifier to identify vehicles.

Vehicle Tracking (Assigning IDs to Vehicles)
We have used the correlation tracker from the dlib library.

Speed Calculation
We calculate the distance moved by the tracked vehicle in a second in terms of pixels, and then convert this to meters. With the distance traveled per second in meters, we determine the speed of the vehicle.

How to Run the Project

Follow these steps:

1)Clone the repository:
git clone https://github.com/KavyaSharma01/Moving-object-detection-and-speed-tracking.git

2)Change directory into the project folder:
cd vehicle-speed-check

3)Create a virtual environment:
python -m venv venv

4)Activate the virtual environment:
./venv/bin/activate

5)Install the required dependencies:
pip install -r requirements.txt

6)Run the detect and speed trackk.py script:
python detect and speed track.py

Note:
We have estimated these values manually for the current road to calculate pixels per metre(ppm). Therefore, the value will vary from road to road and have to be adjusted to be used on any other video.
If I talk about the part how we estimated ppm, we need to know the actual width in metres of the road(you can use google to find the approximate width of the road in your country). Also, we have taken the video frame and calculated the width of the road in pixels digitally. Now, we have the width of the road in metres from the real world and in pixels from our video frame. To map the distances between these two worlds, we have calculated pixels per metre by dividing distance of road in pixels to metres.
d_pixels gives the pixel distance travelled by the vehicle in one frame of our video processing. To estimate speed in any standard unit first, we need to convert d_pixels to d_metres.
Now, we can calculate the speed(speed = d_meters * fps * 3.6). d_meters is the distance travelled in one frame. We have already calculated the average fps during video processing. So, to get the speed in m/s, just (d_metres * fps) will do. We have multiplied that estimated speed with 3.6 to convert it into km/hr.



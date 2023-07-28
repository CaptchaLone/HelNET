## Helmet Detection Model

This model is used to detect whether a person had helmets on or not. It is trained using PyTorch and the Open Images dataset. The idea is that if the model detects a person going into a contruction site without a helmet the program would warn the person.


## The Algorithm
The algorithim is using a camera and a Nvidia Jetson Nano to detect whether if there is a person with helmet in the picture. It uses a 4GB Jetson Nano, and so it uses a preflashed SD card flashed from the NVIDIA webpage. It uses the SSD-Mobilenet object detection model to detect people and helmets in the image, then it determine whether the helmet appeared on the person's head. Then it will print out the result of whether the person is wearing a helmet or not. It is up to the user to interepret the information.

Note: I ran this model on a realivly low epoch with information that was askew. Let's just say the results are not very accurate.
## Running this project
1. Connect to your Jetson Nano via VSCode. 
2. Connect your Webcam (preferably Logitech or any other USB webcam)
3. Ensure that you have the proper things installed. You will need a Jetson Nano preflashed with Nvidia firmware, install PyTorch on the nano (git clone https://github.com/dusty-nv/pytorch-ssd.git) , and download the helmet detection model onto your computer.
4. Next, run these codes on your Jetson Nano:
```
cd pytorch-ssd
pip install -r requirements.txt
wget https://nvidia.box.com/shared/static/djf5w54rjvpqocsiztzaandq1m3avr7c.pth -O   models/mobilenet-v1-ssd-mp-0_675.pth
pip3 install -v -r requirements.txt
```
5. Then run the following code - $ python3 final_project2.py --network=facenet (webcam name here)
6. You should see a video popup of your face. Note how it is not a smooth stream of images. It should be a headshot of you and your face, and there should be some blakc space.
7. The model is up and running, and so you should just put your face in clear view infront of the camera and watch as it tries to predict your age!

[View a video explanation here](video link)

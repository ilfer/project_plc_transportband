# Vision Camera

![image](https://user-images.githubusercontent.com/79916453/167299916-faa6185a-dd1d-4513-ae7f-20c76f8f9509.png)

## About
The goal with this vision camera, the mako g040 is to detect objects on the conveyor belt. The idea was to sort 1 euro and 2 euro coins. After detecting these coins, they are sorted in 1 of the 3 ways shown in the picture below.  

![image](https://user-images.githubusercontent.com/79916453/167300240-2ec606e6-9eff-4201-9052-19dcc6887c20.png)

## Materials and methods

- Mako G-040 GigE Vision Camera
- Depending on which purpose the lens is:  
 Kowa CCTV LENS: LM8JC 2/3" 8mm/F1.4  
 Kowa CCTV LENS: LM12NCL 1/2" 12mm/F1.4
 - Power over Ethernet injector
 - ethernet cable

## Installation
To set up a Vision camera on twincat, the following steps were taken:
Go to the infosys.beckhoff.com and go to the "twincat 3" folder.  
From here go to the "TFxxxx | Twincat 3 Functions" folder and a you go to the "TF7xxx - Vision" folder.  
Then you need to go to the "TF7000-TF7300 | Vision" folder.

Here you follow the steps at the Setup instructions folder and download the TF7xxx-Vision.exe file which can be found at this [Link](https://www.beckhoff.com/nl-be/products/automation/twincat/tfxxxx-twincat-3-functions/tf7xxx-tc3-vision/tf700x.html).

After everything is done correctly you can start a twincat project. The following steps to display the VISION configuration follow the steps in the "Displaying a Vision node and creating an application" folder. After these steps, follow the steps in the "Creating a GigE Vision camera" folder to configure the camera correctly.
To make the camera work connect the output of your PoE injector to your laptop and replace the ethernet settings in the network center to an ip address that is in the range as your camera.

Once the camera is found you can activate it. You can find the activity status in the General tab here with both the IP address and other information.  
![image](https://user-images.githubusercontent.com/79916453/167303314-0a3ea377-0df7-4d78-8fcb-8b016d0c0aaa.png)  

To see the image, go to the configuration Assistant and press the start Acquisition button. Turn on De-Bayering for color and change the ExposureTimeAbs value.
![image](https://user-images.githubusercontent.com/79916453/167303422-76ab87ce-681d-4763-b14f-28679832270d.png)

If there are problems searching for the camera in the Camera Initialization Assistant tab, you can use a separate software to search for the ip, the "Advanced IP Scanner" application. But the IP address for this Mako G040 camera is 169.254.251.174.


## Software
For the software, follow the steps in the "Creating a PLC project " folder.

![image](https://user-images.githubusercontent.com/79916453/167301104-7572d2ef-f887-4ae1-b4ce-8a11850f697d.png)

Explanation:  
With the above code, you can display your camera image using ADS image Watch.


## Result
A stand was built for the camera so that it can detect objects at a certain distance. This distance must be set by the two lenses. One is for a somewhat larger distance to detect objects such as coins and one for very short distances e.g. SMD components.
![image](https://user-images.githubusercontent.com/79916453/167303162-b441f92c-fbc5-440e-9b8e-06df78abd5fc.png)

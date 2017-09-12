. If you don't have # CWIN17-TensorFlow
Cow Detector in TensorFlow

Overview
This repo contains everything you need over and above a TensorFlow install to teach a TensorFlow Convolutional Neural Network (CNN) to recognise cows from other animals. It's intented to be used at the CWIN17 Hackathon. In more deatil this includes:

1. 10,000 images of cows and 30,000 images on other animals conatined in cowdata.7z zip file
2. Links of to TensorFlow to aid install. WIndows has been chosen as the OS because it's universally available to the hackathon teams
3. Instructions how to teach the CNN using the images in the cowdata.7z zip file
4. Instructions how to classify anaimal images.

Data

cowdata.7z is a zip file containing. You need to download it and unzip into your working directory. If you don't have an app to unkip a 7z file get one from www.7-zip.org . This will create a data folder and subfolders for cows and other animals. You'll notice that the images are quite small.


TensorFlow Install

Go here https://www.tensorflow.org/install/ for the TEnsorFlow install

Choose the windows install https://www.tensorflow.org/install/install_windows ( feel free to use other OS's but you're on your own )

Select the option for TensorFlow with CPU support only assuming you don't have a separate GPU in your laptop

Choose the option "native" pip as the install mechanism

If you don't have a Powershell install for windows 10 suggest you install as follows:

Click left lower corner Windows and start typing Powershell. Select the "Windows Powershell (x86)" option

Install pyhton 3.6 from here https://www.python.org/downloads/release/python-362/ If you have python installed you may want to upgrade to 3.6.2

Probably easiest to go for the executable installer. Check python is installed by using powershell and typing:

PS C:\users\lefrost> python

You may need to close your PowerShell window and restart it. This should start the python interpretter. 

Python 3.6.2 (v3.6.2:5fd33b5, Jul  8 2017, 04:57:36) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.

CTRL+z and ENTER will quit you out of it.

Back to the TensorFlow install instructions. Use "pip" to install TenSorFlow

C:\> pip install --upgrade tensorflow

This will result in lots of python scripts being downloaded and will hopefully end with a sucessfully installed message.

Validating your TensorFlow install. Follow the instructions to validate your install

$ python

Enter the short program. You can copy the code line by line and paste it into the python interactive shell via PowerShell.

Note you may get a warning about the tensorflow library not being compiled to use AVX indtructions even though its available on your machine. Ignore this as it just means the learning process takes slightly longer.







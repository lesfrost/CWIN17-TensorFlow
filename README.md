
CWIN17-TensorFlow
Cow Detector in TensorFlow
==========================

Overview
========

This repo contains everything you need over and above a TensorFlow install to teach a TensorFlow Convolutional Neural Network (CNN) to recognise cows from other animals. It's intented to be used at the CWIN17 Hackathon. In more deatil this includes:

1. 10,000 images of cows and 30,000 images of other animals conatined in cowdata.7z zip file
2. Links to TensorFlow to aid install. Windows has been chosen as the OS because it's universally available to the hackathon teams
3. Instructions how to teach the CNN using the images in the cowdata.7z zip file
4. Instructions how to classify animal images.

Data
====

cowdata.7z is a zip file containing images of cows and other animals. You need to download it and unzip into your working directory. If you don't have an app to unkip a 7z file get one from www.7-zip.org . This will create a data folder and subfolders for cows and other animals. You'll notice that the images are quite small.


TensorFlow Install
==================


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
t
CTRL+z and ENTER will quit you out of it.

Back to the TensorFlow install instructions. Use "pip" to install TenSorFlow


> pip install --upgrade tensorflow



This will result in lots of python scripts being downloaded and will hopefully end with a sucessfully installed message.

Validating your TensorFlow install. Follow the TensorFlow install instructions to validate your install

$ python
Enter the short program. You can copy the code line by line and paste it into the python interactive shell via PowerShell.

Note you may get a warning about the tensorflow library not being compiled to use AVX indtructions even though its available on your machine. Ignore this as it just means the learning process takes slightly longer.

Training our Cow network
========================

In order to train our animal detector we are going to develop a python script. If you want a python editor suggest you download atom here http://atom.io . Go for the windows installer.


.Download the cow_trainer.py file into the same working folder as you downloaded the data zip file.
The python code has quite a few dependencies that have to be downloaded.

This is where it gets slightly complex because a lot of the maths packages required are in C, Cython and Fortran code for which most people don't have compilers so you need to download the precompiled execuatble code to match your CPU architecture. The best way to do this is from the http://www.lfd.uci.edu/~gohlke/pythonlibs/

Let's start with scipy. Go here http://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy and download the right file for your version of python (3.6 ) and your processor architecture e.g. scipy‑0.19.1‑cp36‑cp36m‑win_amd64.whl . Dowload this to the Downloads folder

cd C:\Users\[user]\Downloads
pip install scipy-0.19.1-cp36-cp36m-win_amd64.whl

Now go here http://www.lfd.uci.edu/~gohlke/pythonlibs/#scikit-image and download the scikit_image‑0.13.0‑cp36‑cp36m‑win_amd64.whl .

$ cd C:\Users\[user]\Downloads
$ pip install scikit_image‑0.13.0‑cp36‑cp36m‑win_amd64.whl

Now go here http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy and download the numpy‑1.13.1+mkl‑cp36‑cp36m‑win_amd64.whl

$ cd C:\Users\[user]\Downloads
$ pip install numpy‑1.13.1+mkl‑cp36‑cp36m‑win_amd64.whl

$ pip install sklearn
$ pip install tflearn

We should now have all the dependencies to train our CNN

cd cowdetector ( the folder where you installed cow_detector.py )
$ cow_trainer.py

Should now get lots of messages about training 

The training can take Mup to 6 hours depending on the processing power of the computer your're running it on. The training python script does 100 epoches ( iterations )

Running the Classifier ( Is it a cow or not ? )
===============================================

Now we can run the CNN classifier on some test images and see if they are cows or not

Download the test_images.7z zip file and unzip into your working directory. This will give you a number of animal images to test out your classifier.

$ classifier.py fox_1.jpg

PS C:\Users\lefrost\environments\my_env> .\classify.py .\fox_1.jpg
2017-09-12 16:12:50.477863: W C:\tf_jenkins\home\workspace\rel-win\M\windows\PY\36\tensorflow\core\platform\cpu_feature_
guard.cc:45] The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and
 could speed up CPU computations.
2017-09-12 16:12:50.478745: W C:\tf_jenkins\home\workspace\rel-win\M\windows\PY\36\tensorflow\core\platform\cpu_feature_
guard.cc:45] The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine an
d could speed up CPU computations.
It's not a cow
[  1.41226870e-08   1.00000000e+00]
PS C:\Users\lefrost\environments\my_env>


Try the zebra file next and see what you think?

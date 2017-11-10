# OpenCV Installation (Python)

---

### Last revision
> 2017 november 10

### Most Recent OpenCV Version (by this date)
> 3.3.1

---

## Windows
### 1. Python
 - Go to [**PYTHON DOWNLOAD PAGE**](https://www.python.org/downloads/release/python-2714/) and search for desired version **at the bottom of page**.
 - **Warning**: DO NOT insta-click on highlighted download button! (it will download the 32-bit version!).

### 2. OpenCV
 - Go to [**OPENCV RELEASES PAGE**](https://opencv.org/releases.html) and download preferred version **for Windows**.
 - **Warning**: pre-compiled files for most recent version (3.3) currently are not working!
 - Navigate to <opencv_root> folder (the one with several subfolders and files).
 - Find the subfolder containing Python build. It may be the 32-bit version or the 64-bit one depending on your system.  
Some examples:  
32-bit: <opencv_root>/build/python/<version_number_2_or_3>/x86/  
64-bit: <opencv_root>/build/python/<version_number_2_or_3>/x64/  
 - Copy **cv2.pyd** to **site-packages** subfolder of Python installation directory.  
You can also find it by running the Python script below:  
```
import site
print site.getsitepackages()
```  
There will probably 2 paths, but the correct one is the folder containing several other packages. It is usually located at <python_root>/Lib/site-packages

### 3. Install Pip
 - Right click [**THIS FILE**](https://bootstrap.pypa.io/get-pip.py) and **Save File As** get-pip.py.
 - Open a console and run the file above  
```python get-pip.py```

### 4. Install numpy
 - ```python -m pip install numpy```

### 5. Test installation
 - Open a console.
 - Start Python environment by running: ```python```
 - Test numpy: ```import numpy```
 - Test opencv: ```import cv2```

### Problems?
If something goes wrong during cv2 installation, you may have installed it in wrong environment such as:  
 - Another version of Python: Python 2 / Python 3
 - A temporary virtual environment
 - Anaconda environment

---

## Linux
### 1. Python
Linux distros are provided with Python installed already. But you may want to update it.

### 2. Dependencies
 - Install Python dependencies:
```
sudo apt-get install build-essential
sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
```

### 3. OpenCV
 - Clone the [**OPENCV SOURCE REPO**](https://github.com/opencv/opencv)  
```git clone https://github.com/opencv/opencv.git```

 - Navigate to root folder  
```cd ~/opencv```

 - Create a build directory. Choose a name ("release/", "build/" ...)  
```mkdir build```

 - Enter the build directory and build OpenCV.  
```
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..
```
- As this build may take 30 minutes or even 1 hour, you can dedicate all of your cores to this task by adding the flag **-j<number_of_cores>** to the end of previous command.  
**Warning**: *If you use all of your cores, you probably won't be able to use your PC for another task until the build is finished!*  
8 core example:  
```cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local .. -j8```

 - Install obtained build  
```
make
sudo make install
```

### 4. Test installation
 - Open a console.
 - Start Python environment by running: ```python```
 - Test numpy: ```import numpy```
 - Test opencv: ```import cv2```

### Problems?
If something goes wrong during cv2 installation, you may have installed it in wrong environment such as:
 - Another version of Python: Python 2 / Python 3
 - A temporary virtual environment
 - Anaconda environment

---

# KCF tracker in Python

Python implementation of
> [High-Speed Tracking with Kernelized Correlation Filters](http://www.robots.ox.ac.uk/~joao/publications/henriques_tpami2015.pdf)<br>
> J. F. Henriques, R. Caseiro, P. Martins, J. Batista<br>
> TPAMI 2015

It is translated from [KCFcpp](https://github.com/joaofaro/KCFcpp) (Authors: Joao Faro, Christian Bailer, Joao F. Henriques), a C++ implementation of Kernelized Correlation Filters. Find more references and code of KCF at http://www.robots.ox.ac.uk/~joao/circulant/

### Requirements
- Python 2.7
- NumPy
- Numba (needed if you want to use the hog feature)
- OpenCV (make sure you can `import cv2` in python)

### Usage
```shell
git clone https://github.com/uoip/KCFpy.git
cd KCFpy
python run.py
```
It will open the default camera of your computer, you can also open a different camera, or a video
```shell
python run.py 2
```
```shell
python run.py test.avi  
```
Try different options (hog/gray, fixed/flexible window, singlescale/multiscale) of KCF tracker by modifying the arguments in line `tracker = kcftracker.KCFTracker(False, True, False)  # hog, fixed_window, multiscale` in run.py.


### Contribution
I have struggled to make the python implementation as fast as possible, but it's still 2 ~ 3 times slower than its C++ counterpart, furthermore, the use of Numba introduce some unpleasant delay when initializing tracker, I'll be happy if you can help further optimize the code.
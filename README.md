# ADIP & CV (CS60052) Assignment 2

## Installation:
Follow this link to download [Miniconda](https://docs.conda.io/en/latest/miniconda.html "Miniconda Page"). Then, to install required packages, and create environment, run
```bash
conda env create -f environment.yml
```

inside the project directory. Activate `conda` environment by running

```bash
conda activate adip-assignment-2
```

Assuming the OS you run is Linux based, run the `run.sh` script for effortless
viewing of the results. Each `slide` will show after 4 seconds. If the OS is
**not** Linux based, then you can run each of the lines in the `run.sh` file
successively.

All functions are heavily doucumented, and the operations are all
automatic. Where it is not, like the selection of the rectangular area, the best
result by experimentation is presented. Chance is that you won't have to, but
feel free to change any parameter.

## Experimental Results:
Read function docstrings for a overview of all the functions, and what they
do. There are many parameters involved, but I have tried to make it as automatic
as possible, inspired by recent Scan apps. Image wise results:

* **PataChitraPuri_1.jpg** - Runs completely automatic.
* **PataChitraPuri2.jpg** - It **can** run completely automatic, but since the
main painting is above many other paintings, in automatic run, it can't
distinguish the borderline (neither can I at first glance, frankly). I have
provided an approximate bounding rectangle, so that the results are better.

The algorithm for tranformations work on an approximate quadrilateral
calculation from the (estimated) four corner points in the image. Then all
results from all operations are stored asnd shown as a slideshow, with the title
depicting which "operated" image is shown. For further information regarding any
function or OpenCV method, please visit [OpenCV Documentation Page](https://docs.opencv.org/4.5.5/index.html "OpenCV Documentation").

## Usage:
```bash
# Creating and activating conda environment
conda env create -f environment.yml
conda activate adip-assignment-2

# See all options; accessing the help menu
python assignment.py --help

# Without any option, it runs with the PataChitraPuri_1,jpg image, if present
python assignment.py

# Set time interval in seconds between image "slides", here it is 2.5s
python assignment.py --interval 2.5

# Everything automatic, except if corners are hard to detect
python assignment.py --image myimage.jpg

# Manually select four corners, overriding automatic mechanism
python assignment.py --image myimage.jpg --manual

# NOTE: Provide either mask or rectangular area. Providing both as input is
# just counter-intuitive, and the program will run with --rect flag only.

# Manually provide the rectangular part of the image whose foreground we
# need to extract, for example, from (x=1,y=2) of width 600 and height 400
python assignment.py --image myimage.jpg --rect 1 2 600 400

# Manually provide mask for the image
python assignment.py --image myimage.jpg --mask mymask.jpg
```


### Author Information:
	• Name : Aritra Sen.
	• Roll no. : 19ME10101.
	• Department : Mechanical Engineering.
	• Subject : Advanced Digital Image Processing & Computer Vision (CS60052).

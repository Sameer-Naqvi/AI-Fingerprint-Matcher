# Fingerprint Matcher Using AI

## Overview
This project is a fingerprint matcher that uses AI to compare and identify fingerprint images. The program leverages the Scale-Invariant Feature Transform (SIFT) algorithm to detect key points and compute descriptors for matching fingerprints. It searches for the best match from a dataset of real fingerprint images against an altered sample fingerprint.

## Features
**SIFT Algorithm:** Utilizes SIFT to detect and compute key points and descriptors for fingerprint images.

**FLANN Based Matcher:** Employs the FLANN (Fast Library for Approximate Nearest Neighbors) based matcher for finding the best matches between the descriptors of the sample and dataset images.

**Real-Time Matching:** Outputs the best match along with the matching score.

**Visual Result:** Displays the matched fingerprints side by side, highlighting the key points that contributed to the match.

## Prerequisites
Python 3.x

OpenCV (cv2) library

## Installation
**Install OpenCV:** pip install opencv-python

**Download the Dataset:** Ensure you have the SOCOFing dataset available, which should include both the Altered and Real fingerprint images.

## Usage
**Place the Sample Image:** The sample image to be matched should be placed in the path specified within the code (SOCOFING/Altered/Altered-Hard/150__M_Right_index_finger_Obl.BMP).

**Run the Script:** Run the Python script to start the fingerprint matching process.

python fingerprint_matcher.py

## View the Results:

The program will output the filename of the best matching fingerprint along with the matching score.\

The matching fingerprints will be displayed in a window, showing the corresponding key points.

## How It Works

**Image Loading:** The program first loads the sample fingerprint image and then iterates through a subset of 1000 real fingerprint images from the dataset.

**Key Point Detection:** For each image, the SIFT algorithm is used to detect key points and compute descriptors.

**Descriptor Matching:** The FLANN-based matcher is used to find the best matches between the sample and each image from the dataset.

**Best Match Selection:** The program calculates the match score based on the ratio of good matches to key points and keeps track of the best match.

**Result Display:** The best-matched fingerprint is displayed along with the key points and the matching score.

## Customization
**Dataset Size:** By default, the program checks 1000 images from the SOCOFing/Real dataset. You can modify the number of images processed by changing the slicing parameter in the code.

**Matching Threshold:** The matching threshold (0.1 * q.distance) can be adjusted for more or less strict matching.

## Known Issues
**Performance:** The program currently processes images sequentially, which might be time-consuming for larger datasets. Optimizations such as parallel processing can be implemented for faster results.

**Dataset Path:** Ensure the paths to the dataset are correct; otherwise, the program will fail to load images.

## Acknowledgments
**SOCOFing Dataset:** Special thanks to the creators of the SOCOFing dataset for providing the fingerprint images used in this project.




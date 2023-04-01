# Edge-Detection-FPGA

This project aims to develop an edge detection system using Field Programmable Gate Arrays (FPGA). The FPGA-based edge detection system will be designed to handle high-resolution images and operate at high speeds. The system will use popular edge detection algorithms such as Sobel, and Canny to detect edges in images. The project will also explore the feasibility of using different edge detection algorithms for various image processing applications.

Keywords: Edge Detection, FPGA, Hardware, Real-time Processing, Image Processing, Verilog, Vivado

## Current updates

## Introduction

Edge detection is an image processing technique for finding the boundaries of objects within images. It works by detecting discontinuities in brightness. Edge detection is used for image segmentation and data extraction in areas such as image processing, computer vision, and machine vision. The points at which image brightness changes sharply are typically organized into a set of curved line segments termed edges. The same problem of finding discontinuities in one-dimensional signals is known as step detection and the problem of finding signal discontinuities over time is known as change detection. Edge detection is a fundamental tool in image processing, machine vision and computer vision, particularly in the areas of feature detection and feature extraction.
## Objectives

## Sobel Edge Detection
The Sobel filter is used for edge detection. It works by calculating the gradient of image intensity at each pixel within the image. It finds the direction of the largest increase from light to dark and the rate of change in that direction. The result shows how abruptly or smoothly the image changes at each pixel, and therefore how likely it is that that pixel represents an edge. It also shows how that edge is likely to be oriented. The result of applying the filter to a pixel in a region of constant intensity is a zero vector. The result of applying it to a pixel on an edge is a vector that points across the edge from darker to brighter values.The sobel filter uses two 3 x 3 kernels. One for changes in the horizontal direction, and one for changes in the vertical direction. The two kernels are convolved with the original image to calculate the approximations of the derivatives.
![image](https://user-images.githubusercontent.com/121241278/229300999-5acf342c-9e8f-4785-bcc8-5268632ddecd.png)



### 3.1 Mathematical Background:


## Designing the Unit:

## Simulation:

## Results and Conclusions:

## References:

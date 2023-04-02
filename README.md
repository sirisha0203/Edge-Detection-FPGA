# Edge-Detection-FPGA

This project aims to develop an edge detection system using Field Programmable Gate Arrays (FPGA). The FPGA-based edge detection system will be designed to handle high-resolution images and operate at high speeds. The system will use popular edge detection algorithms such as Sobel, and Canny to detect edges in images. The project will also explore the feasibility of using different edge detection algorithms for various image processing applications.

Keywords: Edge Detection, FPGA, Hardware, Real-time Processing, Image Processing, Verilog, Vivado

## Introduction

Edge detection is an image processing technique for finding the boundaries of objects within images. It works by detecting discontinuities in brightness. Edge detection is used for image segmentation and data extraction in areas such as image processing, computer vision, and machine vision. The points at which image brightness changes sharply are typically organized into a set of curved line segments termed edges. The same problem of finding discontinuities in one-dimensional signals is known as step detection and the problem of finding signal discontinuities over time is known as change detection. Edge detection is a fundamental tool in image processing, machine vision and computer vision, particularly in the areas of feature detection and feature extraction.
## Sobel Edge Detection
The Sobel filter is used for edge detection. It works by calculating the gradient of image intensity at each pixel within the image. It finds the direction of the largest increase from light to dark and the rate of change in that direction. The result shows how abruptly or smoothly the image changes at each pixel, and therefore how likely it is that that pixel represents an edge. It also shows how that edge is likely to be oriented. The result of applying the filter to a pixel in a region of constant intensity is a zero vector. The result of applying it to a pixel on an edge is a vector that points across the edge from darker to brighter values.The sobel filter uses two 3 x 3 kernels. One for changes in the horizontal direction, and one for changes in the vertical direction. The two kernels are convolved with the original image to calculate the approximations of the derivatives.

![image](https://user-images.githubusercontent.com/121241278/229300999-5acf342c-9e8f-4785-bcc8-5268632ddecd.png)

The kernels can be applied separately to the input image, to produce separate measurements of the gradient component in each orientation (call these G x and G y).
These can then be combined together to find the absolute magnitude of the gradient
at each point and the orientation of that gradient. The gradient magnitude is given
by sqrt(Gx^2 + Gy^2).

## Designing the Unit:
MATLAB IMPLEMENTATION : 
We used MATLAB as golden reference and verification purposes.
![image](https://user-images.githubusercontent.com/121241278/229340475-4b97942d-661d-4624-9216-1f26c0973f85.png)
Here we can see that there 2 nested loops. The use of these loops are to cover the whole 2-D matrix of the image and leave the edges. Inside this loop we are doing element-wise matrix multiplication of a 3X3 matrix with a sobel mask.

VERILOG IMPLEMENTATION : 
The MATLAB code was taken as foundation code. The hardware implementation was done on Xillinx platform. The synthesizable code was burnt on to a basys3 fpga board.
The code is divided into several modules for making it more understandable and feasible. The functional description of the modules are as following:

• topcontroller : This module is the central module of our code. It calls other modules such as Uart and sobel. This code initializes registers, matrices and blockrams. The crux of the code lies in the FSM that we have designed. The 4 state FSM first receives data from pc through the UART and fills it in the image blockram. Then next state uses a sophisticated algorithm to extract a sub-matrix from a single dimension blockram. The next state uses a trigger flag(received from sobel module) to store the data received into filtered image blockram which is initialized for filtered image after sobel module sends out the computed data. The last state sends the data to pc through UART.

• sobel: This module performs a 3X3 element-wise matrix multiplication. We used a optimizing method of loop unrolling to reduce the delay in matrix multiplication. We also used a floating point ip to calculate square root.

• Uart: This module is mainly for transferring and receiving data from pc to fpga and viceversa.

Steps to make a synthesizable code: We first made our RTL level code in verilog. The next step was to make it synthesizable. We had to remove dependencies such as
hierarchical referencing, loops and commands such as $realtobits etc.
We used a test-bench to verify our working of the code. We sent data through a loop to the uart and received data from uart. Main purpose the implementation was to verify working of our code and as mentioned we used MATLAB as our golden reference.
## Simulation:

## Results and Conclusions:

## References:

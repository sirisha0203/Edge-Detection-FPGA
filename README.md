# Edge-Detection-FPGA

This project aims to develop an edge detection system using Field Programmable Gate Arrays (FPGA). The FPGA-based edge detection system will be designed to handle high-resolution images and operate at high speeds. The system will use popular edge detection algorithms such as Sobel, and Canny to detect edges in images. The project will also explore the feasibility of using different edge detection algorithms for various image processing applications.

Keywords: Edge Detection, FPGA, Hardware, Real-time Processing, Image Processing, Verilog, Vivado

## Current updates

## Introduction

Edge detection includes a variety of mathematical methods that aim at identifying edges, curves in a digital image at which the image brightness changes sharply or, more formally.
## Objectives

## Sobel Edge Detection

The Sobel Algorithm involves convolving the image with a kernel to extract edge information in a particular direction or angle. Typically, the Sobel technique is applied in two directions: horizontal (x) and vertical (y). This method takes the first-order derivative with respect to x and y to obtain edge details. However, this technique can be implemented in more than two directions, as shown in this project. The kernel Gx is used for the horizontal direction, and the kernel Gy, which is the transpose of Gx, is used for the vertical direction. While it is commonly used on grayscale images, it can also be applied to color images, but this may increase the complexity and reduce efficiency.

### 3.1 Mathematical Background:

The Sobel filter is a method used to highlight edges in an image, and it employs two 3x3 matrices, or kernels. One kernel highlights edges in the horizontal direction, while the other highlights edges in the vertical direction. To obtain approximations in the horizontal and vertical directions, the filter convolves with the Gx and Gy kernels, respectively.

     | 1        | 2        | 3        |
Gx = | 4        | 5        | 6        | * A  (1)
     | 7        | 8        | 9        |                

           Longtitudinal Template

     | 1        | 2        | 3        |
Gx = | 4        | 5        | 6        | * A    (2)
     | 7        | 8        | 9        |

          Latitudinal Template

In the above matrixes, A represents the original image, Gx and Gy represent the kernels that are convolved with the horizontal and vertical kernels.

## Designing the Unit:

## Simulation:

## Results and Conclusions:

## References:

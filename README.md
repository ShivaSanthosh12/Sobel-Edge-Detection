#SOBEL EDGE DETECTOR
Overview:
This project implements a Sobel edge detection processor on an FPGA using Verilog hardware description language (HDL). Sobel edge detection is a popular technique in image processing for detecting edges in images by applying convolution operations with specific kernels.

Modules:
imageProcessTop:
  Top-level module interfacing with the AXI (Advanced eXtensible Interface) protocol.
  Interfaces with image data, controls the flow of data between modules, and handles interrupts.
  Instantiates the 'imageControl', 'conv', and 'outputBuffer' modules.
imageControl:
  Manages the control flow of image processing operations.
  Tracks pixel data, detects the end of lines, and generates interrupts.
  Interfaces with line buffer modules for data storage and retrieval.
conv:
  Performs convolution operations using Sobel kernels to detect edges.
  Utilizes two Sobel kernels to calculate horizontal and vertical edge gradients.
  Computes the sum of squared gradients and thresholds the result to generate edge detection.
lineBuffer:
  Implements line buffers for temporary storage of pixel data.
  Facilitates parallel access to pixel data for convolution operations.

Functionality:

  Upon receiving valid pixel data, the 'imageControl' module manages the flow of data through the processing pipeline.
  The 'conv' module convolves the incoming pixel data with Sobel kernels to compute edge gradients.
  Edge detection results are thresholded to generate binary edge maps.
  Line buffers are employed for efficient pixel data storage and retrieval during convolution operations.

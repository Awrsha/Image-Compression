# Image Compression using DCT, SVD and Wavelet Transform

## Overview

This project implements various image compression techniques like Discrete Cosine Transform (DCT), Singular Value Decomposition (SVD) and Wavelet Transform in Python using OpenCV and other libraries. 

The goal is to compare different compression algorithms and achieve high compression ratios with minimal loss of quality.

## Algorithms

### Discrete Cosine Transform (DCT)

- Applies 2D DCT on the image divided into 8x8 blocks
- Quantizes the DCT coefficients to reduce precision
- Inverse DCT reconstructs compressed image

### Singular Value Decomposition (SVD)

- Performs SVD on the image matrix
- Sets smaller singular values to 0 to reduce dimensions
- Obtains compressed image by multiplying remaining singular vectors

### Wavelet Transform 

- Applies 2D Wavelet Transform to decompose image into frequency sub-bands
- Keeps high energy coefficients, sets others to 0 
- Inverse transform reconstructs compressed image

## Usage

The project contains Python scripts implementing each algorithm.

To compress an image:

```
python DCT.py test.jpg compressed_output.jpg quality
```

This applies DCT on the input image and saves compressed image to output path. 'quality' parameter controls compression level.

Similarly for SVD:

```
python SVD.py test.jpg compressed_output.jpg num_values
``` 

'num_values' controls how many singular values to retain.

And for wavelet compression:

```
python WT.py test.jpg compressed_output.jpg num_coeffs 
```

'num_coeffs' sets the number of wavelet coefficients to keep.

Lower quality/num_values/num_coeffs gives higher compression but loses more details.

## Results

The techniques can achieve upto 90% compression on typical images with reasonable quality. DCT performs better on smooth regions while wavelets preserve edges better.

![Results](results.png)

## References

- DCT algorithm adopted from OpenCV docs
- SVD implementation based on scikit-image 
- Wavelet compression uses PyWavelets library

Let me know if you need any clarification or have additional suggestions for improving the README!

# Automated  Pill Counting Using Digital Image Processing in MATLAB

## Project Overview
This project presents an automated system for counting the number of white pills present in a digital image using fundamental digital image processing techniques implemented in MATLAB. The system successfully eliminates manual counting errors in pharmaceutical packaging, quality control, and inventory management by leveraging a structured pipeline of filtering, thresholding, and morphological analysis.

---

## Screenshots & Visual Results
*  Displays the raw, unaltered input image of the white pills captured against a contrasting background.  
  ![Original Image](screenshot1.png)

*  Shows the intermediate processing stages, including the grayscale conversion, filtered outputs, and Otsu's binary mask.  
  ![Processing Stages](screenshot2.png)

*  Demonstrates the final output featuring overlaid bounding boxes and sequential numeric labels over each identified pill, along with the total count displayed in the title.  
  ![Final Results](resultshot.png)

---

## Table of Contents
1. Introduction
2. Objectives
3. Literature Background / Theoretical Concepts
4. System Requirements
5. Proposed Methodology
6. Algorithm and Flowchart
7. MATLAB Implementation (Code)
8. Detailed Explanation of Code Modules
9. Results and Discussion
10. Advantages
11. Limitations
12. Applications
13. Future Scope
14. Conclusion
15. References

---
## To READ the full Content :
*For a full walkthrough and detailed explanation, visit the [Automated Pill Counting Blog Post](https://haneenthecreate.blogspot.com/2026/08/automated-pill-counting-using-digital.html).*



## 1. Introduction
Digital Image Processing (DIP) uses computer algorithms to manipulate and analyze digital images for industrial automation, quality inspection, and medical applications. Accurately counting tablets or capsules during packaging and quality assurance is critical, and manual methods are slow and prone to errors. This project automates white pill counting using MATLAB's Image Processing Toolbox.

## 2. Objectives
* Design an automated image processing pipeline to detect and count white pills.
* Apply averaging and median filtering for noise reduction.
* Implement automatic thresholding via Otsu's method.
* Utilize morphological operations to refine segmented regions.
* Label connected components and validate results visually with bounding boxes.

## 3. Theoretical Concepts
* **Grayscale Conversion**: Reduces 3-channel RGB matrices to a single intensity channel to lower computational complexity.
* **Filtering**: Mean filters smooth general intensity variations while median filters preserve sharp object boundaries against noise.
* **Otsu's Method**: Automatically calculates the optimal threshold by minimizing intra-class variance.
* **Morphological Operations**: Employs operations like opening, closing, and hole-filling with a disk structuring element to clean up shapes.
* **Connected Component Labeling**: Assigns unique integers to grouped foreground pixels to determine the total count.

## 4. System Requirements
* **Software**: MATLAB R2018a or later with the Image Processing Toolbox (compatible with Windows, macOS, and Linux).
* **Hardware**: Standard PC/laptop with a minimum of 4 GB RAM and a digital image of white pills.

## 5. Proposed Methodology
1. **Image Acquisition**: Load the RGB image using `imread()`.
2. **Grayscale Conversion**: Convert to a single channel using `rgb2gray()`.
3. **Noise Removal**: Filter using median and averaging techniques.
4. **Contrast Enhancement**: Stretch intensity ranges with `imadjust()`.
5. **Thresholding**: Apply Otsu's thresholding via `graythresh()` and `imbinarize()`.
6. **Morphological Refinement**: Clean objects using `imopen`, `imclose`, and hole-filling.
7. **Connected Component Labeling**: Isolate and count regions via `bwlabel()`.
8. **Visualization**: Overlay bounding boxes and centroids using `regionprops()`.

## 6. Algorithm & Flowchart Summary
* Input Image $\rightarrow$ Grayscale Conversion $\rightarrow$ Median Filtering $\rightarrow$ Contrast Adjustment $\rightarrow$ Otsu Thresholding $\rightarrow$ Morphological Cleanup $\rightarrow$ Component Labeling $\rightarrow$ Visualization & Count Report.


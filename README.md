# Neural Style Transfer: VGG-19 Implementation

This repository contains an implementation of the Neural Style Transfer (NST) algorithm as described by Gatys et al. (2016). The project utilizes a pre-trained **VGG-19 network** to extract content and style representations, blending them through a custom optimization process.

## Project Objective
The goal is to synthesize a new image that preserves the semantic objects of a **Content Image** while adopting the artistic textures and color palettes of a **Style Image**.



## Technical Implementation
* **Network Architecture:** We utilize a pre-trained **19-layer VGG network**.
* **Content Representation:** Captured from the deeper convolutional layers (e.g., `block5_conv2`) to ensure high-level object recognition.
* **Style Representation:** Extracted from multiple layers (`block1_conv1` through `block5_conv1`) using **Gram Matrices** to identify multi-scale correlations in textures.
* **Optimization:** We implemented a weighted loss function and performed gradient descent on the output image pixels using the **Adam Optimizer**.



## Experimental Setup (The 4 Combinations)
We tested the algorithm across four distinct pairings using iconic artistic styles and campus landmarks:
1.  **Style A:** *A Sunday Afternoon on the Island of La Grande Jatte* (Seurat) + **Content 1:** *Alma Mater*
2.  **Style A:** *A Sunday Afternoon on the Island of La Grande Jatte* (Seurat) + **Content 2:** *Butler Library*
3.  **Style B:** *Impression, Sunrise* (Monet) + **Content 1:** *Alma Mater*
4.  **Style B:** *Impression, Sunrise* (Monet) + **Content 2:** *Butler Library*

## Parameter Study & Findings
We conducted an ablation study on the factors affecting the output quality:

### Relative Weights ($\alpha/\beta$)
* **Finding:** The ratio of content weight ($\alpha$) to style weight ($\beta$) is the most critical factor. Increasing the $\alpha/\beta$ ratio yields an image that more closely resembles the original photo, while decreasing it leads to a more abstract, "painterly" result.

### Training Iterations
* **Finding:** We monitored progress over 1,000 iterations. While the structure is established early, the finer stylistic nuances and color depth continue to evolve throughout the training process.



### Random Seeds
* **Finding:** Initializing the output image with different random seeds (noise) results in slight variations in the final color distribution and local textures, but the overall content structure remains robust.

## Team Members
Haosheng Ai, Zi Fang, Weiwei Song, Changhao He

## References
[1] Gatys, L. A., Ecker, A. S., and Bethge, M. (2015). **A Neural Algorithm of Artistic Style.** arXiv:1508.06576.  
[2] **Neural style transfer | TensorFlow Core.** https://www.tensorflow.org/tutorials/generative/style_transfer  
[3] Singh, M. (2017). **Artistic Style Transfer with Convolutional Neural Network.** Medium; Data Science Group, IITR.  
[4] TensorFlow (2018). **Neural Style Transfer: Creating Art with Deep Learning using tf.keras and eager execution.** Medium.  
[5] SreeHarshaNelaturu. **Tensorflow Implementation of Neural Artistic Style Transfer using VGG-19.** GitHub.

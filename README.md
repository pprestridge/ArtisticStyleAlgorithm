# Nueral Style Transfer

This notebook is an attempt to recreate the work done by [Gatys et al. (2015)](https://arxiv.org/abs/1508.06576) to generate new images using a content and style image.

![generated image](https://user-images.githubusercontent.com/17886837/131258021-be7baa79-1f43-4148-9bf3-d3a7c84f95ed.PNG)

## Pre-Trained Convolutional Model

For this notebook, we will utilize a network architecture and set of weights that have already been developed and trained. Tensorflow offers a few famous options to choose from, but we will be using the VGG19 network from [Simonyan et al(2015)](https://arxiv.org/abs/1409.1556), which has been developed to understand the effect of a conv. net's depth on its performance. The VGG19 proved that deep networks (16-19 layers) can be highly effective with small (3x3) convolutional filters.

## Cost Functions

The optimization proposed in the paper is flips the way the optimization is completed. The Nueral Net and its weights are frozen, and instead, the generated piece of art is updated so that an overal cost function is reduced. There are two cost functions which are used to ensure the generated image retains information from the content and style images. There is a content cost function and a style cost function which are added together to define the overall cost function.

The content cost function is used to quantify the difference between the feature representations of the content image and generated image. Intuitively if the encodings of the two images are similar, then two original images are also similar. This cost function ensures the generated image maintains enough information from the original image.

The style cost function considers the difference bewteen the feauture representations of the syle image and the generated image, and it is computed by comparing interim activations within the Convolutional Nueral Net between the style image and the generated image. In the paper, 5 different layers were selected and evenly weighted. My understanding is that the selection of style layers is somwhat arbitrary, but it's best practice to select and weight layers evenly across the network. For now, let's assign them manually; however, later in the notebook, I'd like to look and how selecting layers and their weights affect the generated image. 

## Image Selection

For the content image, I chose an iconinc image from my hometown, and for the style image, I chose Starry Night by Van Gogh (The most common choice from my research).

![contentstle](https://user-images.githubusercontent.com/17886837/131258010-22a48f1a-c1af-440e-9180-669d03203218.PNG)

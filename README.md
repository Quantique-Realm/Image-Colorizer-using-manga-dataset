# Image-Colorizer-using-manga-dataset
Image Colorizer using GAN which has been trained on pair of colored and uncolored manga panels

**Architecture of the GAN Model Trained**
The GAN architecture used here is of Deep Convolution GANs (DCGANs)
Key Characteristics of DCGAN

	1.	Convolutional Layers:
	•	DCGANs utilize convolutional layers instead of fully connected layers. Your code employs convolutional and transposed convolutional layers (also known as deconvolutions) in both the generator and discriminator, which is a hallmark of DCGANs.
	2.	Transposed Convolution:
	•	The generator uses transposed convolutions (implemented with Conv2DTranspose) to upsample the feature maps back to the image size. This is common in DCGANs, which aim to generate high-resolution images.
	3.	Batch Normalization:
	•	The use of batch normalization after convolutional layers helps stabilize training and improve convergence. This is a key technique introduced in the DCGAN paper to allow deeper networks without running into issues like vanishing gradients.
	4.	Leaky ReLU and ReLU Activations:
	•	The activation functions used in the network (Leaky ReLU in the encoder and ReLU in the decoder) align with the DCGAN practices, as they help mitigate the dying ReLU problem and maintain non-linearity throughout the network.
	5.	Final Layer Activation:
	•	The output layer uses the tanh activation function, which is also standard in DCGANs. The use of tanh helps to scale the pixel values between -1 and 1, which is especially important when working with image data that has been normalized.

**Generator**
The Generator has three upsampling layers which is considered the encoded and three downsampling layers which is considered as the decoder

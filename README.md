# Image-Colorizer-using-manga-dataset
Details:
DATASET USED :

Image Colorizer using GAN which has been trained on pair of colored and uncolored manga panels

**Architecture of the GAN Model Trained**
The GAN architecture used here is of Deep Convolution GANs (DCGANs).
Key Characteristics of DCGAN are:

1.	**Convolutional Layers:**
	•	DCGANs utilize convolutional layers instead of fully connected layers. Your code employs convolutional and transposed convolutional layers (also known as deconvolutions) in both the generator and discriminator, which is a hallmark of DCGANs.
2.	**Transposed Convolution:**
	•	The generator uses transposed convolutions (implemented with Conv2DTranspose) to upsample the feature maps back to the image size. This is common in DCGANs, which aim to generate high-resolution images.
3.	**Batch Normalization:**
	•	The use of batch normalization after convolutional layers helps stabilize training and improve convergence. This is a key technique introduced in the DCGAN paper to allow deeper networks without running into issues like vanishing gradients.
4.	**Leaky ReLU and ReLU Activations:**
	•	The activation functions used in the network (Leaky ReLU in the encoder and ReLU in the decoder) align with the DCGAN practices, as they help mitigate the dying ReLU problem and maintain non-linearity throughout the network.
5.	**Final Layer Activation:**
	•	The output layer uses the tanh activation function, which is also standard in DCGANs. The use of tanh helps to scale the pixel values between -1 and 1, which is especially important when working with image data that has been normalized.

**Generator**

**Input Layer:** The generator takes a grayscale image of shape (IMG_HEIGHT, IMG_WIDTH, 1).

**Downsampling:**

•	Four Convolutional Layers: Each layer performs downsampling using a kernel size of 4x4 and strides of 2.

•	Batch Normalization: Applied after each convolution to stabilize and accelerate training.

•	Leaky ReLU Activation: Introduced after each convolution to allow for non-linear transformations and to avoid dead neurons.

**Upsampling:**

•	Three Transposed Convolutional Layers: These layers perform upsampling with strides of 2, effectively increasing the spatial dimensions of the feature maps.

•	ReLU Activation: Applied after each transposed convolution to introduce non-linearity.

•	A transposed convolutional layer generates an output feature map that is larger than its input, allowing the model to synthesize higher-resolution images.

**Output Layer:**

•	The final layer uses a tanh Activation Function to produce color images with pixel values ranging from -1 to 1, which is suitable for generating realistic RGB images.


**Discriminator**

**Input Layer:** Accepts images with four channels (RGBA).

**Convolutional Layers:**

•	Three Conv2D Layers: Each layer increases the number of filters (64, 128, and 256) and uses a kernel size of 4x4 with a stride of 2 to downsample the input while extracting features.
 
•	Leaky ReLU Activation: Applied after each convolution to introduce non-linearity and prevent dead neurons.
 
•	Batch Normalization: Used after the second and third layers to stabilize learning and improve convergence.
 
**Flatten Layer:** Converts the output from the last convolutional layer into a one-dimensional vector.

**Output Layer:** A Dense layer with a single neuron and a sigmoid activation function, providing the probability that an image is real (1) or fake (0).

**RESULTS**

Since the dataset used was the 1000 colored images and grayscaled images of manga panels of black clover manga. It gives better results for colorization of manga panels than of real grayscaled images.
<br>
Manga_panel1
![WhatsApp Image 2024-10-05 at 10 56 17 PM](https://github.com/user-attachments/assets/8aff95d5-d28e-41cf-ab77-c0f6045d3caa)
<br>
Manga_panel2

![image](https://github.com/user-attachments/assets/c0b0da78-697b-4ac3-9bb6-07dc733873de)

<br>
Grayscaled real image
![WhatsApp Image 2024-10-05 at 10 52 15 PM](https://github.com/user-attachments/assets/37725ba2-cd80-4992-a807-5f73828c4306)
<br>




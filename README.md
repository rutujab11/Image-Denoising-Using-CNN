# Image-Denoising-Using-CNN
Recovering meaningful information from noisy images to restore the true image for obtaining high quality images using CNNs

## Introduction
Image denoising is to remove noise from a noisy image, so as to restore the true image. However, since noise, edge, and texture are high frequency components, it is difficult to distinguish them in the process of denoising and the denoised images could inevitably lose some details. With the presence of noise, possible subsequent image processing tasks, such as video processing, image analysis, and tracking, are adversely affected. Therefore, image denoising plays an important role in modern image processing systems.
The state-of-the-art deep learning denoising methods, typically based on CNNs are in rapid use today. Our aim is to use CNN on the training and testing data to help denoise the input image.


•	Autoencoders
Autoencoders are a class of Neural Networks that try to reconstruct the input itself. They are unsupervised in nature. A general structure of Autoencoders include an Encoder and Decoder. It is just like a normal neural network. It can be made like a simple neural network with the output layer producing the same output shape of the input.

![image](https://user-images.githubusercontent.com/55191928/140600999-be0a9f6c-4288-4588-9b2b-64ec8ce55aac.png)

a.	Encoder
The first part of the autoencoder is the encoder part. The job of the encoder part is to encode the information into a smaller denser representation. The idea is that this dense representation can be used to decode to the original input.

b.	Decoder
The decoder takes this dense representation made by the encoder and tries to reconstruct the output.
One of the many reasons to train an auto encoder is Dimensionality Reduction (representing some input in some lower spatial resolution without losing its meaning). The compression depends on the size of the last encoder layer. The encoded presentation is a dense representation and can be used as an encryption and compression for input. This encoded layer is also called bottleneck layer.


•	Convolutional Autoencoder
The above approach can be used with a convolutional neural network. We can use up-sampling or deconvolutional layers to decode and use simple convolutional layers to down-sample (encode).
A convolutional autoencoder looks like this: 
![image](https://user-images.githubusercontent.com/55191928/140601034-4b9fb194-37df-4aa1-b6f4-531a4c741db5.png)

Encoding	          Decoding
Conv2D (14,14,32)	  Conv2DTanspose (3,3,128)
Conv2D (7,7,64)	    Conv2DTanspose (7,7,64)
Conv2D (3,3,128)	  Conv2DTanspose (14,14,32)


## Dataset 
Fashion-MNIST is a dataset of Zalando's article images—consisting of a training set of 60,000 examples and a test set of 10,000 examples. 
Each example is a 28x28 grayscale image, associated with a label from 10 classes:
•	0 T-shirt/top
•	1 Trouser
•	2 Pullover
•	3 Dress
•	4 Coat
•	5 Sandal 
•	6 Shirt
•	7 Sneaker
•	8 Bag
•	9 Ankle boots

## Results
![image](https://user-images.githubusercontent.com/55191928/140601106-86ee784a-add4-4d50-8e00-bb6893ec4c7e.png)

Loss of pixels after training & testing the model: 0.2765


References

•	https://medium.com/red-buffer/autoencoders-guide-and-code-in-tensorflow-2-0-a4101571ce56
•	https://link.springer.com/article/10.1186/s42492-019-0016-7
•	https://www.iosrjournals.org/iosr-jece/papers/Vol.%2011%20Issue%201/Version-1/L011117884.pdf
•	https://vciba.springeropen.com/articles/10.1186/s42492-019-0016-7


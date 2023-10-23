# Audio-Denoising
Audio signals can be depicted through various representations, ranging from raw time series to intricate time-frequency decompositions. The selection of a suitable representation is pivotal for optimal system performance. Spectrograms, a type of time-frequency decomposition, are recognized as an efficacious representation for audio processing tasks. These are essentially 2D images that encapsulate sequences of the Short Time Fourier Transform (STFT). These images have time and frequency on their axes, and the intensity of the image showcases the potency of a particular frequency component over time. This characteristic design of spectrograms facilitates the direct application of Convolutional Neural Network (CNN) architectures, which are conventionally used for images. Among the two types of spectrograms, magnitude and phase, the former captures a more significant portion of the signal's structure, while the latter presents limited temporal and spectral patterns.

We employ the U-Net architecture—a Deep Convolutional Autoencoder augmented with symmetric skip connections. Originally conceived for the realm of Biomedical Image Segmentation, we have innovatively repurposed the U-Net to cater to the task of spectrogram denoising.

For the network's ingress, we utilize the magnitude spectrograms derived from perturbed vocal signals. Concomitantly, the egress of the network is designed to model the Noise Residual, determined by the difference between the magnitude spectrograms of the noisy and pristine voices. To ensure the data's compatibility with our model's architecture and to enhance training stability, both the ingress and egress matrices undergo a comprehensive global scaling, ensuring their values lie within the bounded range of -1 to 1.


## Dataset and training 

I provide the implementation in both Pytorch and Tensorflow.

The dataset used in this roject is a private one from [Thales](https://www.thalesgroup.com/fr), so unfortunately I cannot share it. However, the principles of this work could be applied to any similar setting. 

![](assets/predicted_vs_gt_truth.png)

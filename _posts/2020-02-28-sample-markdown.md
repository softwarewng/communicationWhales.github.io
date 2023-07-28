---
layout: post
title: AI and Deep Learning in Unraveling the Mysteries of Whale Communication
tags: [test]
comments: true
---

Intro-Project Ceti and Basic Concepts.

**Here is some bold text**

## Detection
To collect data about the whales one has properly to distinguish whale sounds from the other ocean of sounds you get underwater.  The program taking care of this crucial first step is **Orca Spot**.


### Orca-Spot
#### ORCA-SPOT is an automatic killer whale sound detection toolkit that uses deep learning techniques, specifically convolutional neural networks (CNNs), to analyze large bioacoustic datasets
ORCA-SPOT architecture is built upon the principles of a ResNet. 
ResNet is a form of convolutional neural network used primarily for image processing.
The developers chose ResNet 18 as a base design for the Orca Spot. 
![Experiment between different Variants of ResNet](https://communicationWhales.github.io/assets/img/Resultsorca-spot.png)

ResNet18 is the smallest and simplest among the ResNet variants. It proved to be a strong competitor due to its speed and efficiency. The ResNet18 architecture's training and inference times were the shortest, making it a favorable option where real-time results are crucial. It can process 45-minute Orchive tape in 2 minutes Its accuracy was only about 0.5% less on average compared to the more complex ResNet50. 
Although ResNet34 has almost double the layers of Resnet18, it did not show any substantial improvement. Moreover, Resnet101 is the most complex among the ones tested, and did not provide a significant boost in accuracy compared to its counterparts. 
##### Architecture
![](https://communicationWhales.github.io/assets/img/Orca-Spot.png)
The developers of Orca-Spot modified the original ResNet design in specific ways to better handle its task of distinguishing killer whale sounds from noise. 
For example, in traditional ResNet architecture, the max-pooling layer with a stride of 2 would cause a loss of resolution early in the network, which is disadvantageous for handling high-frequency subtle killer whale signals. ORCA-SPOT circumvents this by keeping the resolution as high as possible for as long as possible, by removing max-pooling in the first residual layer. 

The second modification includes a global average pooling layer, in which output is connected to a fully connected layer with 512 neurons. This layer then projects its output onto two classes: "killer whale" and "noise", providing the final decision of the model.
##### Training the model 
In order to train the model, the audio clips were turned  into 44.1kHz mono wav-signal and then converted into power spectrograms. To increase the variety of data the model trains on, intensity, pitch, time, and noise augmentation, were randomly scaled between two fixed ranges.  

During the development and training of the Orca-Spot two models were created with different normalization approaches.
The **Orca-Spot 2** model applies dB-normalization within a fixed range of 0–1, as a mean/standard deviation normalization approach in **Orca-Spot 1** leads to high false-positive rates because when the standard deviation is close to zero in silent recordings, any small variation in the signal might be magnified by the normalization process, leading to extreme values and thereby higher false-positive rates.   
Using dB-normalization (decibel normalization) the audio signal's intensity (or loudness) is adjusted to fit within this specified range. In this case, the loudest signal is set as 1 and the quietest signal is set as 0, and everything else falls proportionally in-between, which helps avoid creating extreme values even if the original recording is very quiet
##### Results
 ![](https://communicationWhales.github.io/assets/img/results_2.png)
**Orca Spot 1** was tested on 19,056 audio clips: 16,646 segments true killer whale sounds 2,410 falsely classified. 
**Orca Spot 2**  was tested on 19,211 audio clips: 17,451 segments true killer whale sounds
1,760 segments falsely




 





###  Orca-Clean
text

## Classification

### Orca-Feature
The Orca-Feature is a deep learning model that can classify and differentiate between different call types. This model can operate without the need for pre-existing labels or classifications. The pipeline is less prone to human error, as it offers a more objective approach when it analyses the sound, which eliminates human bias.

The structure of the model is somewhat close to the Orca-Spot and Orca-Clean. It is also a convolutional neural Network, that is based on ResNet18.
 The model contains an under-complete autoencoder, that tries to accurately learn and reconstruct the input of the spectrogram image.
 ![](https://communicationWhales.github.io/assets/img/Autoencoder.png "This image shows the results from the Autoencoder reconstructing the original image from various whale type calls")  
The autoencoder contains an encoder path, where it uses an encoder function on the input sample to get a hidden representation. Then a decoder path with a decoder function to reconstruct the original input. So, the main goal is to generate an output, that is as close as possible to the original input and that process enables Feature learning, which allows the model to understand important characteristics of each spectrogram image. 
![](https://communicationWhales.github.io/assets/img/archiauto.png)  
After the model learns the salient features of each spectrogram image, spectral clustering, an unsupervised learning technique, is used to group similar spectrogram images on the basis of features together.

To Properly evaluate unsupervised Clustering, a comparison has been made to the supervised Classification model. This model has the same structure as Orca-Spot. However, the output is connected to a 12-D layer, to classify between 12 different call types, that have been trained to recognize. 

![](https://communicationWhales.github.io/assets/img/matrix.png)
The confusion matrix clearly visualizes the comparison between the supervised(left) and unsupervised(right). The supervised classification reached around 85% accuracy, whereas, for the unsupervised model, there were a lot of misclassifications and reached around 60% accuracy. Nevertheless, does it mean the model was wrong?

 ![](https://communicationWhales.github.io/assets/img/classifications.png)
In the image above in cluster c we have two different spectrogram images, which the clustering algorithm grouped together. However, humans classified them as different call types, specifically N07 and N09. This raises the question, did the humans misclassify them, or did the unsupervised clustering?  

### Orca-Slang
#### Multi-Stage Semi-Supervised 
## Communication- Language Model
In order to build Communication-Language Model, acoustic building blocks need to be identified. This includes recognizing basic units or phonetics in the whale vocalizations, by looking for patterns in their vocalizations, much like vowels and consonants in human speech. 
Moreover, we need to identify the grammatical structure, like determining the rules that govern the arrangement of these basic units, much like the syntax in human languages. Furthermore, in order to prevent building a "whale-chat bot" that can communicate with sperm whales without our understanding, we need to link the behavioral date with the codas.
As far as we know, a Language Model hasn't been implemented yet, however, a roadmap has been laid out. They intend to use unsupervised translation. An example here shows how it should work.
//animation
We have here two different languages. Each word produces multi-dimensional vector representations known as embeddings. When these embedding of different words are grouped together they create a geometrical shape. If the shape of these different languages is aligned, it means that they have the same meaning. With this unsupervised method, correlation can be established directly from the embeddings themselves without the need for supervision. But for this to work, we'll need a lot of **DATA**. Not just codas, but also behavioral data, .....  data. 









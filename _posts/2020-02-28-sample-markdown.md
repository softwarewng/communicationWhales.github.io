---
layout: post
title: AI and Deep Learning in Unraveling the Mysteries of Whale Communication
tags: [test]
comments: true
---

Intro-Project Ceti and Basic Concepts.

**Here is some bold text**

## Detection
To collect data about the whales one has properly distinguish whale sounds from the other ocean of sounds you get underwater.  The program taking care of this crucial first step is Orca spot


### Orca-Spot
#### ORCA-SPOT is an automatic killer whale sound detection toolkit that uses deep learning techniques, specifically convolutional neural networks (CNNs), to analyze large bioacoustic datasets:In this study, deep neural networks were trained on 11,509 killer whale (Orcinus orca) signals and 34,848 noise segments. The resulting toolkit ORCA-SPOT was tested on a large-scale bioacoustic repository – the Orchive – comprising roughly 19,000 hours of killer whale underwater recordings.
ORCA-SPOT is a specific architecture built upon the principles of a ResNet. 
ResNet is a form of convolutional neural network used primarily for image processing.
The model was proposed in 2015 by Kaiming He and his team at Microsoft Research in a paper titled "Deep Residual Learning for Image Recognition".
ResNet18: This is the smallest and simplest among the ResNet variants evaluated in the experiment. It proved to be a strong competitor due to its speed and efficiency. The ResNet18 architecture's training and inference times were the shortest, making it a favorable option where real-time results are crucial. Its accuracy was only about 0.5% less on average compared to the more complex ResNet50. 
However, it modifies the original ResNet design in specific ways to better handle its task of distinguishing killer whale sounds from noise. Key modifications include:

In traditional ResNet architecture, the max-pooling layer with a stride of 2 would cause a loss of resolution early in the network, which is disadvantageous for handling high-frequency subtle killer whale signals. ORCA-SPOT circumvents this by keeping the resolution as high as possible for as long as possible.

The output from the global average pooling layer is connected to a fully connected layer with 512 neurons. This layer then projects its output onto two classes: a standard approach for binary classification problems in machine learnin "killer whale" and "noise", providing the final decision of the model.

Both ORCA-SPOT-1 (OS1) and ORCA-SPOT-2 (OS2) models are built upon the ResNet18 architecture and have identical network hyperparameters. They were trained on underwater sound recordings to classify segments as either "noise" or "killer whale". 
OS1 implements a mean/standard deviation normalization approach, while OS2 applies dB-normalization within a fixed range of 0–1. The dB-normalization in OS2 was introduced to counteract issues with the standard deviation close to zero in silent recordings, which led to high false-positive rates in OS1. 
OS1 uses the mean/standard deviation normalization approach, which is also called Standard Scaling or Z-score normalization. In this method, the mean is subtracted from individual data points and then divided by the standard deviation. The result is that the data is centered around 0 (mean is 0) with a unit standard deviation. 
OS2 uses dB-normalization (decibel normalization) within a fixed range of 0-1. This means the audio signal's intensity (or loudness) is adjusted to fit within this specified range. In this case, the loudest signal is set as 1 and the quietest signal is set as 0, and everything else falls proportionally in-between. 
The decision to switch to dB-normalization in OS2 was driven by a problem observed with the original approach in OS1. Specifically, when OS1 encountered silent or very quiet recordings, the standard deviation (a measure of how spread out the data is) would be very close to zero. When this happens, any small variation in the signal might be magnified by the normalization process, leading to extreme values and thereby higher false-positive rates, i.e., incorrectly identifying noise as "killer whale" sounds. 
 
The dB-normalization method used by OS2 is more robust to this problem because it works within a fixed range (0–1), which helps avoid creating extreme values even if the original recording is very quiet. This makes it better suited for audio data with a wide dynamic range or recordings that have periods of silence 
OS2 was trained on a larger dataset than OS1, containing an additional 6,109 noise samples from the AEOTD corpus, which were not part of the training set of OS1. This was done to improve the model's ability to generalize and to be more robust to noise. 
The performance of both models was evaluated using various metrics such as accuracy, true-positive-rate (TPR), false-positive-rate (FPR), positive-predictive-value (PPV), and Area Under the Curve (AUC). OS2 performed slightly better than OS1, largely due to the changed normalization approach and additional noise samples 
 **result orca**
 





###  Orca-Clean
text

## Classification

### Orca-Feature
 It operates without the need for pre-existing labels or classifications on the data, making it more versatile for analyzing new, unlabeled data.
The pipeline is less prone to human errors such as misclassifications, offering a more objective approach to data analysis.
The pipeline is capable of robustly analyzing large volumes of data, an essential feature when dealing with extensive recordings of orca sounds.
It eliminates the subjective aspect of human perception from the process, providing an unbiased analysis based on data alone.
 Despite being fully unsupervised, it achieved an accuracy of approximately 60.0% on a problem involving the classification of sounds into 12 categories.
The depth of analysis provided by the pipeline enables the discovery of new and previously unknown sub-call types, expanding our understanding of orca communication

### Orca-Slang
#### Multi-Stage Semi-Supervised 
## Communication- Language Model
in order to build the communication model we need to identify acoustic building blocks
The first step is to identify the basic units or phonetics in the whale vocalizations. This involves looking for patterns and discrete units within the vocalizations, much like the vowels and consonants in human speech. The process is similar to the spoken term discovery in human speech processing and could be achieved by using unsupervised machine learning techniques. These techniques would identify and classify repeated patterns, hence, forming a basis for understanding the structure of the whale language. 
After the basic units of the whale language are identified, the next step would be to determine the rules that govern the arrangement of these basic units, much like the syntax in human languages. This involves looking for higher-level hierarchical structures across the basic units. Techniques from natural language processing (NLP) for unsupervised grammar induction can be used here. These techniques can help in generating hypotheses about the grammatical structure of whale communication. 
 
Inferring Meaning: Once the structure of the whale language is understood, the next key question is to understand the semantics, i.e., what do these vocalizations mean. Techniques from machine learning and NLP can be used to associate meaning with sequences of clicks or codas. Models capable of learning mappings between sequences and continuous groundings can be useful here. 
 
Understanding Discourse and Social Communication: Sperm whale communication happens in a social context and understanding the discourse-level structure is crucial. This step would involve identifying rules that govern conversational turns, adaptations based on audience, and other such aspects. Predictive models capable of generating probable vocalizations given a conversation history and context could be built for this purpose. 
 
Redundancy and Fault Tolerance: Communication systems often have redundancy and fault tolerance mechanisms built-in to counter imperfections. Identifying these in sperm whale communication would require distinguishing variations due to redundancy from dialectal and individual variations. 
 
Language Acquisition: Understanding how young whales learn the language can provide further insights into the structure and function of the language. Continuous data acquisition on calf-mother pairs could provide insights into the order of acquisition of different aspects of the language. 
 
The complexity of the task necessitates the use of a combination of unsupervised learning techniques, deep learning models, NLP techniques, and methods for grammar induction, among others. The success of the task would largely depend on the availability of large-scale bioacoustic data and careful interpretation of the models' output 




![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg)

It can also be centered!

![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg){: .mx-auto.d-block :}


## Local URLs in project sites {#local-urls}

When hosting a *project site* on GitHub Pages (for example, `https://USERNAME.github.io/MyProject`), URLs that begin with `/` and refer to local files may not work correctly due to how the root URL (`/`) is interpreted by GitHub Pages. You can read more about it [in the FAQ](https://beautifuljekyll.com/faq/#links-in-project-page). To demonstrate the issue, the following local image will be broken **if your site is a project site:**



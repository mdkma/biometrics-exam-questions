# Past Questions and Answers

Mar 6, 2017 | [Derek Mingyu MA](http://derek.ma) | <derek.ma@connect.polyu.hk>

## Knowledge Structure

### L1-2 | Introduction

* User Authentication

What you know, what you have, what you are/do

* History of Automatic biometrics

* Biometrics Definitions

Automated methods of recognizing individuals based on their traits. A physical characteristics or personal behavioral trait used to recognize the identity, or verify the claimed identity of an enrollee

Enrollment
Template
Matching -> matching score

Evaluation Method

* Biometrics Systems

### L3 | Image Processing

### L4-6| Pattern Recognition

### L7-9 | Traditional Uni-Model Techs: Physical Features

### L10 | New Biometrics Tech

### L11-12 | Traditional Uni-Model Techs: Behavioral Features

## Review Points

1. Iris vs Retina
2. Voice feature
3. Statistics-based and Knowledge-based face detection & location
4. Process: enrollment, template/feature vector and matching score
5. Euclidean distances and Hamming distances
6. Biometrics authentication: statistical, syntactic and NN
7. Feature of signature
8. PCA
9. Contrast enhancement methods: power law function
10. Fingerprint features, global and local
11. Image processing: Convolution
12. Select minimum feature vector
13. Filter operations for edge extraction: High-pass filter and Laplacian edge filter
14. face recognition process

## Past Questions: Explanations

### 16-A1

> As you know, there are two doors used in the current E-Channel border application. The first one could need to show a personal HK ID card, and the second to obtain user's fingerprint and match with the record in the DB. If only one door to be used, how to implement this application? Please draw the necessary flowcharts to point out the common functions and the differences between these two doors and the one door E-Channel border application.
> 
> Please point out some common characteristics and differences with the necessary flowchart between identification and verification.

Lec2-35

One door is using the identity identification. While the two door design is using the identity verification. 

Identification: who are you, one to many matching, much harder, because an identification system must perform a large number of comparisons.

Verification: are you who you say you are, one to one matching

Flowchart: Lec2-37

**More**:
Some systems use hierarchical or classification methods to speed up the searching. But these methods would introduce errors.

Hierarchical approach uses some simple features and fast matching algorithm to retrieve a small set of templates for further recognition using complex algorithm.

Classification approach cuts down the DB in several (fuzzy/non-fuzzy) groups. The input feature is classified to one/several group.


### 16-A2

> There are two kinds of biometrics from an eye, i.e. Iris and Retina. Please define their features and explain each advantages and disadvantages.
> 
> 13-C1: what kinds of features can you find from a retina image?

#### Retina features
Physical features 

* vessels: blood transfer
* optic disk: the nerves of eye connected to brain

Pathological features

* red lesion
* bright lesion

#### Retina +/-

Advantages

* accuracy
* stability of biometrics Sample
* resistant to fraud
* small temple

Disadvantages

* difficulty to use
* consumer perceptions
* static design
* cost
* not convenient if you wear glasses or are concerned about having close contact with the reading device

#### Iris features

* trabecula meshwork, a tissue that gives the appearence of dividing the iris in a radial fashion
* rings
* furrows
* freckles
* corona

#### Iris +/-

Advantages

* high level of accuracy
* unique structure for each iris
* capable of reliable identification as well as verification

Disadvantages

* potentially low contrast pattern in dark irises
* some user don't accept eye-based technology
* high cost capture devices or inconvenient devices
* not easy to use since light sensitivity of humans
* accuracy decreases when users wear eyeglass, obscured by eyelashes, lenses/reflections
* any unusual lighting situations may affect the ability of the camera to acquire its subject

### 13-A1, 12-A1

>Please compare the features between two kinds of biometrics: Back Vein and Palmprint, and then explain which one is more accurate, why?
>
> Please compare the features between two kinds of biometrics: Hand Shape and Palmprint, and then explain which one is more accurate, why?

Features of Palmprint: Lec10-14

Geometry features: finger width; length, width, thickness and area of a palm

Texture Feature

Line Features: principal lines and wrinkles

Point Features: minutiae point; delta point; datum point

Palm Vein

### 16-A3

> The following two models are from the different speakers saying the same vowel. Please try to define some necessary features to divide these two models.
![q3](img/3.png)
> What kind of features could be extracted from voice biometrics? Please list at least 3 features in detail.

Feature set: cadence, frequency, pitch and tone of an individual's voice

Features used in real system:

* frequency-ban analysis
* identification from spectrograms(energy distribution of speech signal)
* use of coarticulation(analyze the points of spectrograph where coarticulation takes place)
* formant frequencies(position of the resonances can determine the differences between the speakers)
* pitch contours(variation of the pitch during the period of utterance)
* features derived from linear prediction

### 16-A4

> Face detection & location is an important stage in face recognition. There are two main types, i.e., Statistics-based and Knowledge-based, to implement this function. Each type could include a few methods. Could you show at least one method for each type and roughly explain how to work?

Statistics-based method

* Subspace method

Find the subspace of face images which shown common features of faces, which is a good representation of face

* NN method

Two-class classification: face/non-face. Need to train the NN with face and non-face images. But many kinds of non-face images which are not collected, and slow.

Knowledge-based method

* Distribution ruler of gray-value-based
* Contour ruler
* Color information

Detect faces with the use of color information of face, as usually color of faces are different from that of background color in an image.

* Movement information
* Symmetry information

### 16-A5

> Explain following basic concepts:
> 1) Enrollment
> 2) Template/Feature Vector
> 3) Matching Score

Enrollment:
The process by which a user's biometrics data is initially **acquired, assessed, processed and stored** in the form of a template for ongoing use in a biometrics system.

Template:
A mathematical representation of biometrics data-skeletonized features of a detailed image and typical values of biometrics indicators of an individual. It update over time, which can be stored in central database, mobile devices and smart cards.

Feature Vector:
It frequently happens that we can measure a fixed set of $d$ features for any objects or event that we want to classify. We can think of our feature set as a feature vector $x$, where $x$ is the $d$-dimensional column vector. We can also think of $x$ as being a point in a $d$-dimensional feature space.

Matching scores:
The matching result between two templates

### 16-A6

> There are two comparison methods in pattern recognition, Euclidean distances and Hamming distances, for decision making. What difference between these two distances? If given two words: "WHILE" and "WHORL", what is their Hamming distance?

Lec9-35

Hamming distances are positive integers that represent the number of pieces of data you would have to change to convert one data point into another.

Euclidean distance is the length of the line segment that connects two coordinates.

❓Euclidean distance is used for numeric measures, but Hamming distance is used for discrete measures.

Hamming distance: 3/5.

### 16-A7

> There are three main approaches in biometrics authentication: Statistical, Syntactic and NN. For each approach, please give a its dfn and explore a simple application.

Lec5-4

**Statistical PR**: there is an _underlying and quantifiable statistical basis_ for the generation of patterns.

Most of PR systems are based on this approach.

**Syntactic PR**: the _underlying structure of the pattern_ provides the information fundamental for PR

**NN**: neither of the above cases hold true, but we are able to develop and train an architecture to correctly associate input patterns with desired response.

Example: Lec5-10

### 14-A4

> There are two main functions in pattern recognition: Feature Extraction and Matching. Please explain which stage is important after all possible features are extracted. How to implement matching function? 

Lec4-27

Not all features are useful for a special problem. Feature selection is the important stage after all possible features are extracted. It is the process of choosing input to PR system and involves judgement. It is important that the extracted features be relevant to the PR task at hand.

How to implement matching function?

1. Hypothesize a plausible solution and adjust it to fit the problem
2. Create a mathematical model of the problem and derive an optimal classifier.

Pattern classification, template matching.

### 14-A5

> Please find their differences in the following three pairs of basic concepts:
> 
> Template and sample;
> Speech recognition and voice biometrics
> Text-dependent speaker ID and text-independent speaker ID

**Template and Sample**(Lec2-33): system will take several samples and extract unique features from samples to create a template

**Speech recognition and Voice biometrics**(Lec12-3,9): A clear graph shows at Lec12-9. Speech Processing -> Output/Input. Input can be voice biometrics or speech recognition. Voice biometrics is confirm people's identities using their voice. Speech recognition is extract information from the stream of speech and figure out what the person is saying.


**Text-dependent speaker ID**: provide utterance of key words or sentences that are the same for training and recognition.
**Text-independent speaker ID**: verifies the identity of the individual who is speaking. The performance of verification can vary according to: the quality of the audio signal, ambient noise, the variation between enrollment and verification devices. So same device for acquisition and verification.

### 12-A6

> Please define the following basic concepts used in image processing:
> 
> Pixel
> Image
> Image histogram
> Point operation

Pixel: the point at which an image is sampled as known as picture elements.

Image: a spatial presentation of an object: matrix representing quantized intensity values

Image histograms: Plots of $N_j$ v.s. $j$: shows the distribution of image pixels in terms of their gray levels.

Point operations: a function is applied to every pixel in an image, which operates only on the pixel's current value.

### 13-A4

> Generally, there exist four main stages in a given biometric system. Please indicate each function.

Lec2-33

1. Capture: a physical or behavioral sample is captured during enrollment, identification or verification process
2. Extraction: unique data is extracted from the sample and a template is created
3. Comparison: the template is compared to new sample
4. Match/non-match: system then decides if the features extracted from the new sample are a match/non-match.

## Section B

### 16-B1

> It is necessary to perform a statistical analysis from a relative large DB... **Variance of Inter-class, Variance of Intra-class and F-ratio**

Lec12-22 + Lec13-20
Intra-class variability remember the difference between different classes, while inter-class similarity shows the similar features of two samples. Intra-class variability can show the key characteristics of the person, and inter-class similarity can help the system to remove the similar feature and leave unique characteristics.

_F-ratio is inter-class variability/intra-class variability._

F-ratio is the balanced ratio considering these two variables. _The higher is the ratio, the more discriminant the feature is._

### 16-B2

> Signature features

**Upper and lower envelop**: the curve connecting the most up or low pixel of the signature trajectory

**Vertical and horizontal projection**: the count of black pixels per horizontal or vertical lines

### 16-B3

> PCA Method: list the main steps to implement this method? Point out the main advantages using this method.

**Steps(Lec5-19)**

1. Divide image data into training and testing set. E.g. the training set X is composed by the first 5 samples for each class and the rest construct the test set Y.
2. Express every image sample in X by a feature vector with dimension of its resolution. Calculate mean value for each group($m$).
3. Calculate total scatter matrix.
4. Compute the eigenvalue and eigenvectors of $S_t$, we have $\lambda_i\phi_i = S_t\phi_i, i=1,...,644$, where $\lambda_i$ and $\phi_i$ are the $i^{th}$ eigenvalue and eigenvector. Re-express 9 eigenvectors with nonzero eigenvalues in the form of image -> eigenfaces.
5. Select the most principal components or eigenvectors. (ratio: selected components/total sum)
6. Then the PCA projection transform $W$ is composed by $W = (\phi_1, ..., \phi_n)$ (if n most principal components). Obtain transformed features sets from X and Y: $X' = (X-m)*W$; $Y' = (Y-m)*W$

**Advantages**

1. Reduce data dimensionality
2. Satisfy the minimal MSE rule
3. Eliminate the correlation of original data

**Disadvantages**

1. Eigenfaces do not distinguish between shape and appearance
2. PCA does not use class information

### 14-B2

> Eigenface is PCA-based method with five steps. After finishing the first four stages, we obtain 9 eigenvectors with nonzero eigenvalues in the form of image. At the fifth step, the $k$ most principal components are selected abased on the ratio $\gamma$ of the eigenvalue sum of selected components to the total sum. Please decide the value of $k$ when the threshold of $\gamma$ is 85%.

See: Lec5-24

### 13-A3

> What is PCA? Why can it be used for biometrics authentication?

Principal Component Analysis can reduce the number of dimensions of a data set, so the image can be further processed or visualization. It is used to calculate the vectors which best represent this small region of image space.

In biometrics, different types images should occupy different areas of the smaller region, so that we can identify a person by finding the nearest known vector in image space.

## Section C

### 16-C1

> Power Law Function for contrast enhancement

$\gamma < 1$ enhance contrast in dark regions
$\gamma > 1$ enhance contrast in bright regions

For first picture, $\gamma$ can be 0.5. 弧线应该是圆左上角样子

For second picture, $\gamma$ can be 3. 弧线应该是圆右下角的样子

### 14-B1-2

> Why Median Filter is better than Low-Pass Filter for noise reduction?

Low-pass filter: blurs the edge, fine detail smoothed by averaging

Median filter: fine detail passed by filter, place all pixels by neighborhood median by convolving

### 14-C1

> Contrast enhancement is an important method in the image preprocessing. How to design a transfer function(T) from input to output?

P3-15

### 16-C2

> Fingerprint representations can be broadly categorized into two types: global and local. Global feature characteristics includes singular points and basic ridge patterns(six classes). Local representation is based on minute details(minutiae) of finger ridges. Given the following fingerprint image, please indicate which class it is and account all each global and local feature you can find.

What class it is?

**Fingerprint Classification**

* Loop
* Arch
* Whorl

**Global Features**

* Pattern Area
* Core Point
* Type Lines
* Delta
* Ridge Count
* Basic Ridge Patterns: loop, arch, whorl

**Local Features**

* Ridge ending
* Ridge bifurcation
* Ridge divergence
* Dot or Island
* Enclosure
* Short ridge

**More**:
Global representation is an overall attribute of the finger and a single representation is valid for the entire fingerprint and is typically determined by an examination of the entire finger.

A local representation consists of several components, each component typically derived from a spatially restricted region of the fingerprint.

Typically, generic representations are used for fingerprint indexing and local representations are used for fingerprint matching.

### 14-B3

> What kind of points could be shown as singular points? Could you draw three basic fingerprint classes according to singular points?
> How many different points could be usually indicated as fingerprint minutia? Please list each definition.

Lec7-38

### 16-C3

> Convolution in image processing. Compute the convolved image.

Answer for this particular question:
on my notebook.

### 14-C2

> Assume that there is an IrisCode with 256 bytes by using texture feature. If 4 bits represent a feature, please compute the total number of features represented by the IrisCode

256*8/4

## Section D

### 16-D1

> A 3-D example for pattern extraction is defined in the following. There are four kinds of features are extracted. Please select a minimum feature vector to classify the given six objects. If each feature is a binary value (0/1), please list these objects' representation.

Use features: edges, cross-section-size, axis.

### 16-D2

> Fourier Function. How to explain the meaning of the Spectrum in Fig. (b) transformed by Fourier Function from Fig. (a)? For a given English letter "K", what is the main spectrums?

Lec6-24

Fourier theory expresses any signal as sum of $sin$ and $cos$ function. 

* The center dot is the DC(Direct Current) component, represents the average value of the image.
* The other two represent the frequency of the sine function. The one dot is just a mirrored version of the other one.
* No dots in the x-direction because the image is the same everywhere in that direction.

Draw K: Lec6-38

### 16-D3

> There are two typical examples of filter operations for edge extraction, which are High-Pass Filter and Laplacian Edge Enhancement Filter. Both are only different in the centre weight values and their weight sums are the "1"-Sum for High-Pass Filter and "0"-Sum mask for Edge Enhancement Filter, respectively. Could you explain what difference about their filtering results?

High-pass Filter

* The high-pass filter will _sharpen the whole image even for smooth parts_, because the sums of weight are 1.

Laplacian Edge Enhancement Filter

* While the Laplacian Edge Enhancement Filter will _only sharpen the edge and the segmentation between different smooth parts_. 
* It works better for _edge extraction_. 
* The _smooth parts will become darker_ due to the sums of its weight is 0.

### 14-D1
> 100 inidividuals try to use a biometric system. There are 38 genuine individuals are accepted, 8 genuine individuals rejected, 44 imposter rejected and 10 imposter accepted. Please evaluate the biometrics system by giving the FAR and FRR. If FTE=0.5, how about ATV?

FRR = True reject/Total true
FAR = False reject / Total false
ATV = (1-FTE)(1-FRR)
EER is where FAR=FRR
Crossover = 1:x <- x=round(1/EER)

FRR = 8/46
FAR = 10/54
ATV = 0.5*38/46 = 0.41

### 12-D2

> As an example of image de-noise, could you roughly explain how to do by using function of frequency domain?

Frequency domain relates to the Fourier transform by decomposing a function into an infinite or finite number of frequencies.



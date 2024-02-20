# Rice Grain Quality Analysis using Deep-Learning

## Introduction 
A Deep Convolutional Neural Network Approach to Rice Grain Purity Analysis is available in this repository. The percentage of foreign grains mixed in with rice is one important indicator of rice purity. Traditionally, most rice sellers employed laborers with years of experience to manually annotate rice grains to confirm their purity. However, this is an expensive method that typically yields inaccurate results. This is extremely time-consuming as well. Consequently, this approach will determine rice purity from a scanned image of the sample in a matter of seconds and with perfect accuracy. All grains will be identified and categorized according to their respective grain types in the result.

## Aims or Objectives:
* Obtaining the measurements of individual rice grains
* Resolving the issue of touching rice grains
* Examining fractured grains of rice

## The technology used:
* Computer Vision
* OpenCV
* Watershed-Algorithm
* Image Pre-processing
* Image Segmentation
* Deep Learning Methods
The aims' approach is clearly explained, with vivid visualizations providing further insights into how each notebook cell functions

# Ideal Image Information
* There will always be a black background
* A combination of broken and unbroken rice grains will be present
* Although they won't overlap, the grains may come into contact

<a href="https://ibb.co/ngwhYQq"><img src="https://i.ibb.co/JBcXGrW/test-black-full1.jpg" alt="test-black-full1" border="0"></a>

# Initial Approach or Solution
---

## The following are the steps needed to solve the objectives:
1. **Importing all the Required Libraries**
2. **Specifying the Necessary Function**
    *  Custom "show" function definition for image visualization Pre-processing Images
2. **Image Pre-Processing**
    * GrayScale Conversion
    * Image Thresholding
    * Morphological Transformations (Noise Removal)
3. **Counting rice grains using the Contours method**
    * Working over Clear images to get insight into grain touching problem
3. **Applying Watershed Algorithm** (Solving grains touching problem)
    * Applying the Watershed Algorithm for Solving Touching Rice grains problem
  
4. **Counting total Rice grains and Broken Rice grains using the contour area**
    * For total rice grain counting: the Watershed method
    * For broken rice grains counting: A filter of an average area of broken rice grain.

# Explanation
<a href="https://www.youtube.com/watch?v=5BAdC-UXpEQ"><img src="https://i.ibb.co/kqg4Jpb/Counting-RIce-Grains.png" alt="Counting-RIce-Grains" border="0"></a>

Making the given image into the best format possible is the basic idea behind solving the objective (counting rice grains). \
It would be simple to count the rice grains if the image was clear and the grains were separated from the background.

Then, Solve the actual Corner cases and hence build the proper solution.


**There are a total 3 major and challenging parts in building solutions:**
1. Image Preprocessing
2. Solving Grains touching problem
3. Counting broken rice

## Image Preprocessing
One of the most important components of the approach is image preprocessing, as the Whole Ideology depends on it.

It is simple to proceed with the techniques if the image is precisely adjusted to meet the requirements.

The most important step in image preprocessing is image tuning, which requires a lot of trial and error to get the parameter value just right.

As part of the Solution, I have used:
* Conversion of BGR Image to Grayscale Image
* Image Thresholding
* And removing noise from the thresholded image using morphologyEx (Opening)

After all the processes, the clear Image was ready for further use. 


## Solving Grains Touching Problem
Once the image has been successfully pre-processed, the problem statement's challenging portion begins.

"**Counting the rice grains that are touching each other**" 

Even counting the rice grains by hand during a manual inspection procedure is difficult. The illusion is created by the white color and small size.

neatly, if the rice grains are neatly separated, counting them is fairly simple for machines. The reason for this is the abundance of available algorithms and helpful strategies.

However, classifying grains becomes quite difficult when there is an issue with objects touching or overlapping.

Given the small size of the rice grains in our situation, it gets more challenging.


Its small size prevents us from using techniques like erosion to separate the touching corner portion.

Thus, I have used the WaterSheld Algorithm to solve this problem:

The basis of the WaterSheld Algorithm is the extraction of specific background and foreground information. Markers are then used to trigger the watershed algorithm, which determines the precise borders.

It's similar to filling in the valleys and then dividing them into hills.



## Counting broken rice
Counting broken rice grains is a common task, however, we will obtain the total number of rice grains in the image after applying the Watershed algorithm.


Using an area-based technique, I classified the rice grains into two categories by applying a threshold after several trial and error attempts.
"**Either Broken rice grain or Full rice grain**"

The image is classified as broken rice if its area is smaller than the given threshold.

We have thereby completed the solutions for both of the objectives.
In any case, I've added other strategies that occurred to me in this notebook's later portion. That can also be used, but I thought my method was more thorough, therefore it's a part of the answer.










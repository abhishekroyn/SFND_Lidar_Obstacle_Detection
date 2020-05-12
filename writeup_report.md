# **Kidnapped Vehicle** 
---

**Lidar-Obstacle-Detection-Project**

The goals / steps of this project are the following:
* Use lidar point clouds and process them in C++ in order to detect obstacles around the moving vehicle.
* Process point clouds, and use it to detect car and trucks on a narrow street using lidar. 
* Follow the methods like filtering, segmentation, clustering, and bounding boxes for the detection pipeline. 
* Create the segmentation, and clustering methods from scratch using the previous lesson’s guidelines for reference. 
* Make sure the he finished result will have bounding boxes placed around all obstacles on the road.

## Rubric Points
### Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/2529/view) individually and describe how I addressed each point in my implementation.  

---
### Compiling and Testing

#### 1. The submission must compile.

The project code compiled without errors using cmake and make.

### Obstacle Detection

#### 1. Bounding boxes enclose appropriate objects.

Bounding boxes enclosed vehicles, and the pole on the right side of the vehicle. There was one box per detected object.

#### 2. Objects are consistently detected across frames in the video.

Most bounding boxes was followed through the lidar stream, and major objects didn't lose or gain bounding boxes in the middle of the lidar stream.

#### 3. Segmentation is implemented in the project.

The code used for segmentation used the 3D RANSAC algorithm developed in the course lesson.

#### 4. Clustering is implemented in the project.

The code used for clustering used the Euclidean clustering algorithm along with the KD-Tree developed in the course lesson.

### Code Efficiency

#### 1. The methods in the code should avoid unnecessary calculations.

The code submitted here did not sacrifice comprehension, stability, or robustness for speed. However, good and efficient coding practices were maintained when writing functions.

There were a few examples showing that inefficiencies were avoided,
* did not run the exact same calculation repeatedly; ran it once, stored the value and then reused the value later, for example, found point clouds for plane, and excluded them from total point clouds to obtain point clouds for obstacles, instead of calculating them again.
* made sure that loops didn't run too many times, by adding maximum iteration counts to them.
* did not create unnecessarily complex data structures when simpler structures work equivalently, for example, divided the steps into subroutines and added recursive function with a checkpoint to come out of loop, wherever needed.
* Only necessary control flow checks were included, for example, at various instances only those values were kept for further processing which met specific criteria.

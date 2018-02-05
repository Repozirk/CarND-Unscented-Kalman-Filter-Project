[//]: # (Image References)
[image1]: ./result/laser_and_radar_Dataset1.PNG
[image2]: ./result/laser_and_radar_Dataset2.PNG
[image3]: ./result/only_laser.PNG
[image4]: ./result/only_radar.PNG


# Unscented Kalman Filter
This is Project 2 of Udacity Self-Driving Car Nanodegree program. 
The goal of the project is to apply the Unscented Kalman Filter to fuse data from LIDAR and Radar sensors using C++.

The project was created with the Udacity [Starter Code](https://github.com/udacity/CarND-Unscented-Kalman-Filter-Project).

## [Rubric](https://review.udacity.com/#!/rubrics/783/view) Points

## Content of this repo
- `scr` a directory with the project code:
  - `main.cpp` - reads in data, calls a function to run the Kalman filter, calls a function to calculate RMSE
  - `ukf.cpp` - initializes the filter, calls the predict function, calls the update function, defines the predict function, the update function for lidar, and the update function for radar
  - `tools.cpp` - a function to calculate RMSE
- `data`  a directory with two input files, provided by Udacity
- `results`  a directory with output and log files
- `Docs` a directory with files formats description
- `ide_profiles`
- `CMakeLists.txt`
- `README.md` Description of the Project by Udacity
- `writeup_template.md` for submission of this Project

## Result
The RMSE values for Dataset_1 are below the RMSE values given [x: 0.9; y: 0.10; vx: 0.40; vy: 0.30] by the rubic poinst. 
Compared to the achieved RMSE values of the Extended Kalman Filter Project, especially the RMSE of the vx and vy values ar 
e lowered. 


Dataset_1: `RMSE: [x: 0.0798; y: 0.0861; vx: 0.3670; vy: 0.2746]`
![alt text][image1] 


Dataset_2: `RMSE: [x: 0.0806; y: 0.0854; vx: 0.6225; vy: 0.3054]`
![alt text][image2] 


To show the benefit of sensor fusion and the implemintation of the CTRV Model, the Dataset_1 is computed once with Radar and once with Laser Date exclusively.

Dataset_1: Only Laser Data
![alt text][image3] 

Dataset_1: Only Radar Data
![alt text][image4] 


Space for Improvement:
As suggested in the lessons for the Unscented Kalman Filter, I tried to compute the percentage of NIS-value higher then 7.815 for Radar and 5.991 for Lidar. Sadly I always got a error I could not fix by the "Eigen"-Function-Block. My suggestion to get the percentage was, counting all the measurements higher then the specific NIS value und put these values in relation to the number of measurements. 
The NIS values of ever measurement are calculated in the Update-Function.
`NIS_laser_ = z_diff.transpose() * S.inverse() * z_diff;`

`NIS_radar_ = z_diff.transpose() * S.inverse() * z_diff;`







`





---
title: "CodeBook.md"
author: "Scott Jacobs"
date: "April 24, 2015"
output: 
  html_document:
    keep_md: yes
---
##Project Description
A Coursera class project for the course "Getting and Cleaning Data". See WHAT THE SCRIPT DOES below.

##Study design and data processing

HOW THE DATA WAS COLLECTED

You can find information about the data here

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

Here are the data for the project: 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 



###Guide to create the tidy data file
Download the data from the link above and place run_analysis.R in the working directory UCI HAR Dataset. Run the script.
 
###Cleaning of the data
WHAT THE SCRIPT DOES
The script takes the data from the UCI HAR Dataset contained in the train and test folders and tidys it up based on the requirements in the course project. The requirements were for the script to do the following;

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
 
##Description of the variables in the TidyTable.txt file
General description of the file including:
 - TidyTable is 180 rows and 88 columns
 - It contains the required "tidy" output of means for the columns that contain 'mean' & 'std' in their names
 - These are the variables in the data
 > names(TidyTable)
 [1] "activity"                                            
 [2] "subject"                                             
 [3] "TimeBodyAccelerator.mean...X"                        
 [4] "TimeBodyAccelerator.mean...Y"                        
 [5] "TimeBodyAccelerator.mean...Z"                        
 [6] "TimeGravityAccelerator.mean...X"                     
 [7] "TimeGravityAccelerator.mean...Y"                     
 [8] "TimeGravityAccelerator.mean...Z"                     
 [9] "TimeBodyAcceleratorJerk.mean...X"                    
[10] "TimeBodyAcceleratorJerk.mean...Y"                    
[11] "TimeBodyAcceleratorJerk.mean...Z"                    
[12] "TimeBodyGyroscope.mean...X"                          
[13] "TimeBodyGyroscope.mean...Y"                          
[14] "TimeBodyGyroscope.mean...Z"                          
[15] "TimeBodyGyroscopeJerk.mean...X"                      
[16] "TimeBodyGyroscopeJerk.mean...Y"                      
[17] "TimeBodyGyroscopeJerk.mean...Z"                      
[18] "TimeBodyAcceleratorMagnitude.mean.."                 
[19] "TimeGravityAcceleratorMagnitude.mean.."              
[20] "TimeBodyAcceleratorJerkMagnitude.mean.."             
[21] "TimeBodyGyroscopeMagnitude.mean.."                   
[22] "TimeBodyGyroscopeJerkMagnitude.mean.."               
[23] "FrequencyBodyAccelerator.mean...X"                   
[24] "FrequencyBodyAccelerator.mean...Y"                   
[25] "FrequencyBodyAccelerator.mean...Z"                   
[26] "FrequencyBodyAccelerator.meanFreq...X"               
[27] "FrequencyBodyAccelerator.meanFreq...Y"               
[28] "FrequencyBodyAccelerator.meanFreq...Z"               
[29] "FrequencyBodyAcceleratorJerk.mean...X"               
[30] "FrequencyBodyAcceleratorJerk.mean...Y"               
[31] "FrequencyBodyAcceleratorJerk.mean...Z"               
[32] "FrequencyBodyAcceleratorJerk.meanFreq...X"           
[33] "FrequencyBodyAcceleratorJerk.meanFreq...Y"           
[34] "FrequencyBodyAcceleratorJerk.meanFreq...Z"           
[35] "FrequencyBodyGyroscope.mean...X"                     
[36] "FrequencyBodyGyroscope.mean...Y"                     
[37] "FrequencyBodyGyroscope.mean...Z"                     
[38] "FrequencyBodyGyroscope.meanFreq...X"                 
[39] "FrequencyBodyGyroscope.meanFreq...Y"                 
[40] "FrequencyBodyGyroscope.meanFreq...Z"                 
[41] "FrequencyBodyAcceleratorMagnitude.mean.."            
[42] "FrequencyBodyAcceleratorMagnitude.meanFreq.."        
[43] "FrequencyBodyBodyAcceleratorJerkMagnitude.mean.."    
[44] "FrequencyBodyBodyAcceleratorJerkMagnitude.meanFreq.."
[45] "FrequencyBodyBodyGyroscopeMagnitude.mean.."          
[46] "FrequencyBodyBodyGyroscopeMagnitude.meanFreq.."      
[47] "FrequencyBodyBodyGyroscopeJerkMagnitude.mean.."      
[48] "FrequencyBodyBodyGyroscopeJerkMagnitude.meanFreq.."  
[49] "angle.tBodyAcceleratorMean.gravity."                 
[50] "angle.tBodyAcceleratorJerkMean..gravityMean."        
[51] "angle.tBodyGyroscopeMean.gravityMean."               
[52] "angle.tBodyGyroscopeJerkMean.gravityMean."           
[53] "angle.X.gravityMean."                                
[54] "angle.Y.gravityMean."                                
[55] "angle.Z.gravityMean."                                
[56] "TimeBodyAccelerator.StdDev...X"                      
[57] "TimeBodyAccelerator.StdDev...Y"                      
[58] "TimeBodyAccelerator.StdDev...Z"                      
[59] "TimeGravityAccelerator.StdDev...X"                   
[60] "TimeGravityAccelerator.StdDev...Y"                   
[61] "TimeGravityAccelerator.StdDev...Z"                   
[62] "TimeBodyAcceleratorJerk.StdDev...X"                  
[63] "TimeBodyAcceleratorJerk.StdDev...Y"                  
[64] "TimeBodyAcceleratorJerk.StdDev...Z"                  
[65] "TimeBodyGyroscope.StdDev...X"                        
[66] "TimeBodyGyroscope.StdDev...Y"                        
[67] "TimeBodyGyroscope.StdDev...Z"                        
[68] "TimeBodyGyroscopeJerk.StdDev...X"                    
[69] "TimeBodyGyroscopeJerk.StdDev...Y"                    
[70] "TimeBodyGyroscopeJerk.StdDev...Z"                    
[71] "TimeBodyAcceleratorMagnitude.StdDev.."               
[72] "TimeGravityAcceleratorMagnitude.StdDev.."            
[73] "TimeBodyAcceleratorJerkMagnitude.StdDev.."           
[74] "TimeBodyGyroscopeMagnitude.StdDev.."                 
[75] "TimeBodyGyroscopeJerkMagnitude.StdDev.."             
[76] "FrequencyBodyAccelerator.StdDev...X"                 
[77] "FrequencyBodyAccelerator.StdDev...Y"                 
[78] "FrequencyBodyAccelerator.StdDev...Z"                 
[79] "FrequencyBodyAcceleratorJerk.StdDev...X"             
[80] "FrequencyBodyAcceleratorJerk.StdDev...Y"             
[81] "FrequencyBodyAcceleratorJerk.StdDev...Z"             
[82] "FrequencyBodyGyroscope.StdDev...X"                   
[83] "FrequencyBodyGyroscope.StdDev...Y"                   
[84] "FrequencyBodyGyroscope.StdDev...Z"                   
[85] "FrequencyBodyAcceleratorMagnitude.StdDev.."          
[86] "FrequencyBodyBodyAcceleratorJerkMagnitude.StdDev.."  
[87] "FrequencyBodyBodyGyroscopeMagnitude.StdDev.."        
[88] "FrequencyBodyBodyGyroscopeJerkMagnitude.StdDev.." 
 

 
NOTES ON VARIABLES

The authors of the study describe the variables thisly in the file features_info.txt

Feature Selection 
=================

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag

The set of variables that were estimated from these signals are: 

mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.

Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:

gravityMean
tBodyAccMean
tBodyAccJerkMean
tBodyGyroMean
tBodyGyroJerkMean

The complete list of variables of each feature vector is available in 'features.txt' ((These were listed above))

ACTIVITY NAMES 
 
The activities were named based on the file activity_labels.tx which contained the following information

1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING
 

 

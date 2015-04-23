---
title: "README"
author: "Scott Jacobs"
date: "April 23, 2015"
output: html_document
---

This is the README file for the Getting and Cleaning Data course project performed by me, Scott Jacobs. What follows is my code and # explaining my coding.

##run_analysis.R
##Author:Scott Jacobs
#1. Merge the training and test sets to create one data set
#2. Extract only the measurements on the mean and standard deviation for each measurement
#3. uses descriptive activity names to name the activities in the data set
#4. Appropriately label the data set with descriptive variable names
#5. From that data set, create a second independent tidy data set avg of each variable for ea activity and subject


##This is my code to read in the files from the train folder
training_x<-read.table("train/X_train.txt")
training_y<-read.table("train/Y_train.txt")
sub_train<-read.table("train/subject_train.txt")
#This is my code to read in the files from the test folder
testing_x<-read.table("test/X_test.txt")
testing_y<-read.table("test/Y_test.txt")
sub_test<-read.table("test/subject_test.txt")
#The files have now been read into variables so that we can combine the training with the testing data
x_combined<-rbind(training_x,testing_x)
y_combined<-rbind(training_y,testing_y)
sub_combined<-rbind(sub_train,sub_test)
#Now lets clean up some naming issues
#First let's rename the column in sub_combined to be "subject"
names(sub_combined)<-c("subject")
#Then let's rename the column in y_combined to be "activity"
names(y_combined)<-c("activity")
#create variable for activity labels
activity_labels<-read.table("activity_labels.txt",header=FALSE)
#replace the integers in the activity column with the corresponding activity labels
#This satisfies requirement #3!
vect<-activity_labels[,2]
vect2<-data.frame("activities"=vect)
vect2$activities[y_combined$activity]
#Now we have to deal with the 561 columns in x_combined that do not yet have descriptive column names
#We can fetch these names from the file "features.txt"
names_featuresfile<-read.table("features.txt", head=FALSE)
#Now let's apply the names in the variable names_featurefile to our x_combined data by subsetting column 2
names(x_combined)<-names_featuresfile$V2
#Now we have three components of the data set with clean names
#Now we can merge the columns of the three to get the merged data set
#Start by merging the activity and the subject data
activity_subject<-cbind(y_combined,sub_combined)
#Now lets bind that to that big honker x_combined
full_data<-cbind(x_combined,activity_subject)

#We have a merged data set! This is what we are asked to do in #1 of the requirements.

#Now we need to extract ONLY the measurements on the mean and std dev for ea measurement
#CreateS2 (Set2)
S2<-tbl_df(full_data)
#Create valid column names so we can use the selct and contains functions
valid_column_names<-make.names(names=names(S2), unique=TRUE, allow_=TRUE)
names(S2)<-valid_column_names
#Create a data frame of only columns that include mean or std
means_and_stds<-select(S2,contains("mean", ignore.case=TRUE), contains("std",ignore.case=TRUE),subject:activity)
#Woohoo this meets requirement #2. 

#Now to rename the columns with descriptive variable names
names(means_and_stds)<-gsub("Acc","Accelerator",names(means_and_stds))
names(means_and_stds)<-gsub("std","StdDev",names(means_and_stds))
names(means_and_stds)<-gsub("^t","Time",names(means_and_stds))
names(means_and_stds)<-gsub("^f","Frequency",names(means_and_stds))
names(means_and_stds)<-gsub("Mag","Magnitude",names(means_and_stds))
names(means_and_stds)<-gsub("Gyro","Gyroscope",names(means_and_stds))

#We did it! That checks off requirement #4.

#create Tidy Table
library(plyr)
TidyTable<-ddply(means_and_stds, .(activity,subject), function(x) colMeans(x[1:86]))

#And lastly, we satisfy requirement #5 by creating a txt output of the Tidy Table
write.table(TidyTable,"TidyTable.txt",row.name=FALSE)
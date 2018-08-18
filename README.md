# Getting and Cleaning Data Course Project 
This is for Data Science Class 3 Week 4 Project
## R Script: How the Scripts Work and How they are Connected


### Prepare the data for cleanning
1. Download and unzip the file.
2. Put the train and test data into two tables "train" and "test". They are tables containing the columns "Activity", "Subject"" and the variables in the Feature file. 
3. Combine the two tables, called "all" and create the data set called "Merged".
4. Use greg() function to identify all columns containing keyword "mean" or "std" in the variables.
5. Select the values in the "all" and store them into the table "subset".
6. Detailed the names on the variables using the fucntion gsub(). 
7. Calculate the mean on the "subset" by the "activty" and "subject", and store the data into a table called "tidy" and create the data set called "Tidy".

```

library(data.table)
## Download the zip file and unzip the file for use
url <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
download.file(url,"./UCI HAR Dataset.zip", mode = "wb")
## The unzip file will be in the same directory as the zipfile
unzip("UCI HAR Dataset.zip", exdir = getwd()) 

## Load the data into the enviroment
setwd("C:/Users/Ms. Kui/Desktop/Coursera/DataCleaning/UCI HAR Dataset")
## Load the variables 
features <- read.csv("features.txt", header = FALSE, sep = " ")
## Only take the 2nd column from the csv as character
features <- as.character(features[,2])

## Load the 3 values of train samples
setwd("C:/Users/Ms. Kui/Desktop/Coursera/DataCleaning/UCI HAR Dataset/train")
## X-train.txt is a table (2 dimensions), so use read.table
trainX<-read.table("X_train.txt")
## Activity and Subject file is a list
trainA<-read.csv("y_train.txt", header = FALSE, sep = " ")
trainS<-read.csv("subject_train.txt", header = FALSE, sep = " ")
## Put the train table together
train<-data.frame(trainS,trainA, trainX)
## features is a list of variables (names)
names(train)<-c(c("Subject", "Activity"), features)

## Load the 3 values of test samples
setwd("C:/Users/Ms. Kui/Desktop/Coursera/DataCleaning/UCI HAR Dataset/test")
testX<-read.table("X_test.txt")
testA<-read.csv("y_test.txt", header = F, sep = " ")
testS<-read.csv("subject_test.txt", header = F, sep = " ")
## put the test table together
test<-data.frame(testS, testA, testX)
names(test)<-c(c("Subject", "Activity"), features)
```
### 1. Merges the train and test sets into 1 data set called all
```
all<-rbind(train,test)
##create the dataset and put into the desire directory
setwd("C:/Users/Ms. Kui/Desktop/Coursera/DataCleaning")
write.table (x = all, file = "Merged.txt", row.names = F )
```
### 2. Extract only the measurements on the mean and standard deviation for 
```
each measurement
##The keyword is mean or std in the variables (features), grep()return the column number
select<-grep("mean|std",features)
## Extra the dataset, select + 2 because the index of "select" starts from 1
subset<-all[,c(1,2,select + 2)]
```
### 3. Uses descriptive activiy names to name the activities in the data
```
## To matching the activity_label to the activity list number, note that this is a 2 dimension table, so use read.table not read.csv
Labela<-read.table("./UCI HAR Dataset/activity_labels.txt", header = F)
## Get only the 2nd column of the data
Labela<-as.character(Labela[,2])
subset$Activity <- Labela[subset$Activity]
```
### 4. Appropriately labels the data set with descriptive variable names.
```
## Use string function to detail the description
nme<-names(subset)
nme <-gsub("[(][)]","",nme)
nme <-gsub("^t","Time_Domain_",nme)
nme <-gsub("^f","Frequency_Domain_",nme)
nme <-gsub("Acc","Accelerometer",nme)
nme <-gsub("Gyro","Gyroscope",nme)
nme <-gsub("Mag","Magnitudge",nme)
nme <-gsub("-mean-","_Mean_",nme)
nme <-gsub("std","_StandardDeviation_",nme)
nme <-gsub("-","_",nme)
names(subset)<-nme
```
### 5. Create a second data set from the step 4 with the average of each variable for each activity and each subject
```
## Calculate the mean from column 3 to 81 group by the activity (Name as Activity) and  subject (name as Subject)
tidy<-aggregate(subset[,3:81], by = list(Activity = subset$Activity, Subject = subset$Subject), FUN = mean)
write.table(x=tidy, file = "Tidy.txt", row.names = F)
```

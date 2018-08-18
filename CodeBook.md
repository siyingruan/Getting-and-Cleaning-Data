# Code Book
## Human Activity Recognition Using Smartphones Dataset
### Version 1.0

***
#### Experiment Owners

* Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
* Smartlab - Non Linear Complex Systems Laboratory
* DITEN - Universit?degli Studi di Genova.
* Via Opera Pia 11A, I-16145, Genoa, Italy.
* [Email Contact](activityrecognition@smartlab.ws)
* [SmartLab](www.smartlab.ws)
* [Link to the Dataset](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

***
#### Data Collection Process

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six **activities:**

* WALKING
* WALKING_UPSTAIRS
* WALKING_DOWNSTAIRS
* SITTING
* STANDING
* LAYING

wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals **(accelerometer and gyroscope)** were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the **time and frequency domain**. See 'features_info.txt' for more details. 

##### For each record it is provided:

***
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

***
#### The Dataset includes files:

- 'README.txt'
- 'features_info.txt': Shows information about the variables used on the feature vector.
- 'features.txt': List of all features.
- 'activity_labels.txt': Links the class labels with their activity name.
- 'train/X_train.txt': Training set.
- 'train/y_train.txt': Training labels.
- 'test/X_test.txt': Test set.
- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 
- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 
- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 
- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

Notes: 

- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

For more information about this dataset contact: activityrecognition@smartlab.ws

***

#### Data Transformation Work:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

***
#### The Output Data Variables and the Description
| Position | Variables                       | Description                                                  |
|----------|---------------------------------|--------------------------------------------------------------|
| 1        | Subject                         | Subject                                                      |
| 2        | Activity                        | Activity                                                     |
| 3        | tBodyAcc-mean()-X               | TimeDomain_BodyAccelerometer_Mean__X                         |
| 4        | tBodyAcc-mean()-Y               | TimeDomain_BodyAccelerometer_Mean__Y                         |
| 5        | tBodyAcc-mean()-Z               | TimeDomain_BodyAccelerometer_Mean__Z                         |
| 6        | tBodyAcc-std()-X                | TimeDomain_BodyAccelerometer_StandardDiviaionX               |
| 7        | tBodyAcc-std()-Y                | TimeDomain_BodyAccelerometer_StandardDiviaionY               |
| 8        | tBodyAcc-std()-Z                | TimeDomain_BodyAccelerometer_StandardDiviaionZ               |
| 9        | tGravityAcc-mean()-X            | TimeDomain_GravityAccelerometer_Mean__X                      |
| 10       | tGravityAcc-mean()-Y            | TimeDomain_GravityAccelerometer_Mean__Y                      |
| 11       | tGravityAcc-mean()-Z            | TimeDomain_GravityAccelerometer_Mean__Z                      |
| 12       | tGravityAcc-std()-X             | TimeDomain_GravityAccelerometer_StandardDiviaionX            |
| 13       | tGravityAcc-std()-Y             | TimeDomain_GravityAccelerometer_StandardDiviaionY            |
| 14       | tGravityAcc-std()-Z             | TimeDomain_GravityAccelerometer_StandardDiviaionZ            |
| 15       | tBodyAccJerk-mean()-X           | TimeDomain_BodyAccelerometerJerk_Mean__X                     |
| 16       | tBodyAccJerk-mean()-Y           | TimeDomain_BodyAccelerometerJerk_Mean__Y                     |
| 17       | tBodyAccJerk-mean()-Z           | TimeDomain_BodyAccelerometerJerk_Mean__Z                     |
| 18       | tBodyAccJerk-std()-X            | TimeDomain_BodyAccelerometerJerk_StandardDiviaionX           |
| 19       | tBodyAccJerk-std()-Y            | TimeDomain_BodyAccelerometerJerk_StandardDiviaionY           |
| 20       | tBodyAccJerk-std()-Z            | TimeDomain_BodyAccelerometerJerk_StandardDiviaionZ           |
| 21       | tBodyGyro-mean()-X              | TimeDomain_BodyGyroscope_Mean__X                             |
| 22       | tBodyGyro-mean()-Y              | TimeDomain_BodyGyroscope_Mean__Y                             |
| 23       | tBodyGyro-mean()-Z              | TimeDomain_BodyGyroscope_Mean__Z                             |
| 24       | tBodyGyro-std()-X               | TimeDomain_BodyGyroscope_StandardDiviaionX                   |
| 25       | tBodyGyro-std()-Y               | TimeDomain_BodyGyroscope_StandardDiviaionY                   |
| 26       | tBodyGyro-std()-Z               | TimeDomain_BodyGyroscope_StandardDiviaionZ                   |
| 27       | tBodyGyroJerk-mean()-X          | TimeDomain_BodyGyroscopeJerk_Mean__X                         |
| 28       | tBodyGyroJerk-mean()-Y          | TimeDomain_BodyGyroscopeJerk_Mean__Y                         |
| 29       | tBodyGyroJerk-mean()-Z          | TimeDomain_BodyGyroscopeJerk_Mean__Z                         |
| 30       | tBodyGyroJerk-std()-X           | TimeDomain_BodyGyroscopeJerk_StandardDiviaionX               |
| 31       | tBodyGyroJerk-std()-Y           | TimeDomain_BodyGyroscopeJerk_StandardDiviaionY               |
| 32       | tBodyGyroJerk-std()-Z           | TimeDomain_BodyGyroscopeJerk_StandardDiviaionZ               |
| 33       | tBodyAccMag-mean()              | TimeDomain_BodyAccelerometerMagnitude_Mean_                  |
| 34       | tBodyAccMag-std()               | TimeDomain_BodyAccelerometerMagnitude_std                    |
| 35       | tGravityAccMag-mean()           | TimeDomain_GravityAccelerometerMagnitude_Mean_               |
| 36       | tGravityAccMag-std()            | TimeDomain_GravityAccelerometerMagnitude_std                 |
| 37       | tBodyAccJerkMag-mean()          | TimeDomain_BodyAccelerometerJerkMagnitude_Mean_              |
| 38       | tBodyAccJerkMag-std()           | TimeDomain_BodyAccelerometerJerkMagnitude_std                |
| 39       | tBodyGyroMag-mean()             | TimeDomain_BodyGyroscopeMagnitude_Mean_                      |
| 40       | tBodyGyroMag-std()              | TimeDomain_BodyGyroscopeMagnitude_std                        |
| 41       | tBodyGyroJerkMag-mean()         | TimeDomain_BodyGyroscopeJerkMagnitude_Mean_                  |
| 42       | tBodyGyroJerkMag-std()          | TimeDomain_BodyGyroscopeJerkMagnitude_std                    |
| 43       | fBodyAcc-mean()-X               | FrequencyDomain_BodyAccelerometer_Mean__X                    |
| 44       | fBodyAcc-mean()-Y               | FrequencyDomain_BodyAccelerometer_Mean__Y                    |
| 45       | fBodyAcc-mean()-Z               | FrequencyDomain_BodyAccelerometer_Mean__Z                    |
| 46       | fBodyAcc-std()-X                | FrequencyDomain_BodyAccelerometer_StandardDiviaionX          |
| 47       | fBodyAcc-std()-Y                | FrequencyDomain_BodyAccelerometer_StandardDiviaionY          |
| 48       | fBodyAcc-std()-Z                | FrequencyDomain_BodyAccelerometer_StandardDiviaionZ          |
| 49       | fBodyAcc-meanFreq()-X           | FrequencyDomain_BodyAccelerometer_Mean_Freq_X                |
| 50       | fBodyAcc-meanFreq()-Y           | FrequencyDomain_BodyAccelerometer_Mean_Freq_Y                |
| 51       | fBodyAcc-meanFreq()-Z           | FrequencyDomain_BodyAccelerometer_Mean_Freq_Z                |
| 52       | fBodyAccJerk-mean()-X           | FrequencyDomain_BodyAccelerometerJerk_Mean__X                |
| 53       | fBodyAccJerk-mean()-Y           | FrequencyDomain_BodyAccelerometerJerk_Mean__Y                |
| 54       | fBodyAccJerk-mean()-Z           | FrequencyDomain_BodyAccelerometerJerk_Mean__Z                |
| 55       | fBodyAccJerk-std()-X            | FrequencyDomain_BodyAccelerometerJerk_StandardDiviaionX      |
| 56       | fBodyAccJerk-std()-Y            | FrequencyDomain_BodyAccelerometerJerk_StandardDiviaionY      |
| 57       | fBodyAccJerk-std()-Z            | FrequencyDomain_BodyAccelerometerJerk_StandardDiviaionZ      |
| 58       | fBodyAccJerk-meanFreq()-X       | FrequencyDomain_BodyAccelerometerJerk_Mean_Freq_X            |
| 59       | fBodyAccJerk-meanFreq()-Y       | FrequencyDomain_BodyAccelerometerJerk_Mean_Freq_Y            |
| 60       | fBodyAccJerk-meanFreq()-Z       | FrequencyDomain_BodyAccelerometerJerk_Mean_Freq_Z            |
| 61       | fBodyGyro-mean()-X              | FrequencyDomain_BodyGyroscope_Mean__X                        |
| 62       | fBodyGyro-mean()-Y              | FrequencyDomain_BodyGyroscope_Mean__Y                        |
| 63       | fBodyGyro-mean()-Z              | FrequencyDomain_BodyGyroscope_Mean__Z                        |
| 64       | fBodyGyro-std()-X               | FrequencyDomain_BodyGyroscope_StandardDiviaionX              |
| 65       | fBodyGyro-std()-Y               | FrequencyDomain_BodyGyroscope_StandardDiviaionY              |
| 66       | fBodyGyro-std()-Z               | FrequencyDomain_BodyGyroscope_StandardDiviaionZ              |
| 67       | fBodyGyro-meanFreq()-X          | FrequencyDomain_BodyGyroscope_Mean_Freq_X                    |
| 68       | fBodyGyro-meanFreq()-Y          | FrequencyDomain_BodyGyroscope_Mean_Freq_Y                    |
| 69       | fBodyGyro-meanFreq()-Z          | FrequencyDomain_BodyGyroscope_Mean_Freq_Z                    |
| 70       | fBodyAccMag-mean()              | FrequencyDomain_BodyAccelerometerMagnitude_Mean_             |
| 71       | fBodyAccMag-std()               | FrequencyDomain_BodyAccelerometerMagnitude_std               |
| 72       | fBodyAccMag-meanFreq()          | FrequencyDomain_BodyAccelerometerMagnitude_Mean_Freq         |
| 73       | fBodyBodyAccJerkMag-mean()      | FrequencyDomain_BodyBodyAccelerometerJerkMagnitude_Mean_     |
| 74       | fBodyBodyAccJerkMag-std()       | FrequencyDomain_BodyBodyAccelerometerJerkMagnitude_std       |
| 75       | fBodyBodyAccJerkMag-meanFreq()  | FrequencyDomain_BodyBodyAccelerometerJerkMagnitude_Mean_Freq |
| 76       | fBodyBodyGyroMag-mean()         | FrequencyDomain_BodyBodyGyroscopeMagnitude_Mean_             |
| 77       | fBodyBodyGyroMag-std()          | FrequencyDomain_BodyBodyGyroscopeMagnitude_std               |
| 78       | fBodyBodyGyroMag-meanFreq()     | FrequencyDomain_BodyBodyGyroscopeMagnitude_Mean_Freq         |
| 79       | fBodyBodyGyroJerkMag-mean()     | FrequencyDomain_BodyBodyGyroscopeJerkMagnitude_Mean_         |
| 80       | fBodyBodyGyroJerkMag-std()      | FrequencyDomain_BodyBodyGyroscopeJerkMagnitude_std           |
| 81       | fBodyBodyGyroJerkMag-meanFreq() | FrequencyDomain_BodyBodyGyroscopeJerkMagnitude_Mean_Freq     |
***

#### License:

Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

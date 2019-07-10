## Getting and Cleaning Data Project

### Description
Additional information about the variables, data and transformations used in the course project for the Johns Hopkins Getting and Cleaning Data course.

### Source Data
Data + Description can be found here [UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)



## Transformations of the source data

The following steps are performed by `run_analysis.R` in order to fulfill the project task and produce the desired output file:

#### Obtaining the source data
The program checks, whether the source data file has already been downloaded and unzipped. If not, it will do both.

#### Merging the training and the test sets to create one data set
The program reads the feature names from the feature list. Then, for both the training and the test sets, the program will first read the subject identifiers, the activity levels and the measurements from their respective files, as outlined in the previous section. Then it combines those three lists into one, by binding the columns together, and renames them according to the feature list. Finally, it merges both the training and the test lists by row-binding them.

#### Extracting only the mean and standard deviation measurements
The program identifies all columns that are the calculated mean and standard deviation quantities of their respective measurement. These can be identified by the `mean()` and `std()` substrings. The data set is reduced to only these columns, as well as the subject identifier and the activity level. Other columns that contain the word "mean" are not taken into account.

#### Replacing the activity identifiers with descriptive activity names
The activity names are read from the activity lable file that was described in the previous section. The numeric activity identifier column is replaced with a factor column that uses these names.

#### Appropriately labeling the data set with descriptive variable names
For this step, the column names of the data set are modified according to the following rules: 

- The prefixes `t` and `f` are replaced by the more descriptive `TimeDomain-` and `FrequencyDomain-`.
- The abbreviated terms `Acc`, `Gyro`, `Mag` and `std` are replaced by the more descriptive `Acceleration`, `Gyroscope`, `Magnitude` and `StandardDeviation`.
- The lowercase `mean` is replaced with an uppercase `Mean`, in order to have consistently spelled variable names.
- All parentheses are removed for better readability.
- In variable names that mistakenly included the term `BodyBody`, only a single `Body` is used.

#### Creating a second, independent tidy data set with the average of each variable for each activity and each subject
For this step, the R package `dplyr` is required, and will be installed if it does not exist. The program then uses the `group_by` method to group the data by its two identifiers, i.e. the subject ID and the activity level. Using the `summarise_all` method, the mean value across each of the measurement columns is calculated for each combination of subject and activity. The output file `tidy_data_output.txt` is created from the resulting data with the `write.table()` method and the `row.names=FALSE` flag. To read the output data back into R, the following command can be used: `tidy_data <- read.table("tidy_data_output.txt", header=TRUE)`.


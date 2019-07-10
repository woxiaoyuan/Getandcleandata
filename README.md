# Getandcleandat
Data Zip File Location: [UC Irvine Repo](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip "Clicking will download the data")

## Goal of the Project
1. A tidy data set 
2. A link to a Github repository with your script for performing the analysis 
3. A code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.
4. Analysis R Script


## Project tasks

The student should create one R script called `run_analysis.R` that does the following:

- Merges the training and the test sets to create one data set.
- Extracts only the measurements on the mean and standard deviation for each measurement.
- Uses descriptive activity names to name the activities in the data set
- Appropriately labels the data set with descriptive variable names.
- From the data set in the previous step, creates a second, independent tidy data set with the average of each variable for each activity and each subject.










## In this repository

- `README.md` is this document. It serves as an introduction to the project, and the source data and explains the other contents of the repository.
- `CodeBook.md` is the code book, which explains which steps, summaries and transformations were taken to produce the resulting tidy data set from the original source data. It also contains a list of all variables in the output data, along with their units and other relevant information.
- `run_analysis.R` is the actual analysis code, written in R, which downloads the source data, applies all the necessary transformations as outlined in the code book, and produces the output file.
- `tidy_data_output.txt` is the output file, generated according to the project tasks and tidy data principles by the `run_analysis.R` code.

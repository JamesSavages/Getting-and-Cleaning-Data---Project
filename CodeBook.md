## Code Book

Actions performed in analysis

1 - Creating a data dir on local repository
2 - install the package "data.table"
3 - download the dataset at the URL (given in the assignment)
4 - Extracting the zip file
4 - merging all *_test.txt and *_train.txt files into one dataset: mergedData
5 - Extract all measurements on the mean and standard deviation for each measurement

mean_std.select
data.sub

6 - Reading the labels from the activity_labels text file. Refer to variables:

activity.labels
data.sub$activity

7 - Replace the names in the dataset with the names from the activity labels

name.new <- names(data.sub)
name.new <- gsub("[(][)]", "", name.new)
name.new <- gsub("^t", "TimeDomain_", name.new)
name.new <- gsub("^f", "FrequencyDomain_", name.new)
name.new <- gsub("Acc", "Accelerometer", name.new)
name.new <- gsub("Gyro", "Gyroscope", name.new)
name.new <- gsub("Mag", "Magnitude", name.new)
name.new <- gsub("-mean-", "_Mean_", name.new)
name.new <- gsub("-std-", "_StandardDeviation_", name.new)
name.new <- gsub("-", "_", name.new)
names(data.sub) <- name.new

8 - Using the this dataset I created an independent tidy data set with the average of each variable activity
and each subject. Created under variable name data.tidy



# week4_gettingandcleaningdata
description of how the script works

1. Download the files and unzip them
2. We read the files as data.table using the fread function and create 2 data sets train_ds and test_ds,which
correspond to the 2 separate data sets present in the folder.
3. As each column is numbered and not annotated properly we need to label them. The file features.txt contained 
the annotation for the columns of both data sets. This one was assigned to the variable "feats" as data.table. The
names of the column were replaced by the names contained in the "feats" data set.
4. Each row of test_ds and train_ds had to be given an activity value(1-6) , this info was present in y_train and y_test for the
train data and the test data set respectively. Each type of activity was assigned to a integer which had to replaced by
the real name of the activity using the activity_labels file. The number of each participant for each data set are add using the "subject_train" and "subject_test" file to train_ds and test_ds respectively.
5. At this point the data sets can be merged together into a new data set called traintest
6. We then keep only the col with a mean or std and activity, this new data set is called traintest_meanstd.
7. We polish the names by removing the parenthesis and replace the dashes by underscores. The col names are
then set to lower case.
8. We can finally summarize our data set by actvity type and subject, this new data set is called traintest_meanstd_sum

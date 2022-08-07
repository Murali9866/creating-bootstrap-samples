# creating-bootstrap-samples
Randomly create 30 samples from the whole boston data points

# Task 1
# Step - 1

Creating samples
Randomly create 30 samples from the whole boston data points

Creating each sample: Consider any random 303(60% of 506) data points from whole data set and then replicate any 203 points from the sampled points

For better understanding of this procedure lets check this examples, assume we have 10 data points [1,2,3,4,5,6,7,8,9,10], first we take 6 data points randomly , consider we have selected [4, 5, 7, 8, 9, 3] now we will replicate 4 points from [4, 5, 7, 8, 9, 3], consder they are [5, 8, 3,7] so our final sample will be [4, 5, 7, 8, 9, 3, 5, 8, 3,7]

Create 30 samples

Note that as a part of the Bagging when you are taking the random samples make sure each of the sample will have different set of columns
Ex: Assume we have 10 columns[1 ,2 ,3 ,4 ,5 ,6 ,7 ,8 ,9 ,10] for the first sample we will select [3, 4, 5, 9, 1, 2] and for the second sample [7, 9, 1, 4, 5, 6, 2] and so on... Make sure each sample will have atleast 3 feautres/columns/attributes
Note - While selecting the random 60% datapoints from the whole data, make sure that the selected datapoints are all exclusive, repetition is not allowed.

 # Build a regression trees on each of 30 samples.
*  Computed the predicted values of each data point(506 data points) in your corpus.
*  Predicted house price of $i^{th}$ data point $y^{i}_{pred} =  \frac{1}{30}\sum_{k=1}^{30}(\text{predicted value of } x^{i} \text{ with } k^{th} \text{ model})$
*  Now calculate the $MSE =  \frac{1}{506}\sum_{i=1}^{506}(y^{i} - y^{i}_{pred})^{2}$

# Step - 3

Calculating the OOB score
Predicted house price of ith data point yipred=1k∑k= model which was buit on samples not included xi(predicted value of xi with kth model).
Now calculate the OOBScore=1506∑506i=1(yi−yipred)2.

# Task 2
Computing CI of OOB Score and Train MSE
Repeat Task 1 for 35 times, and for each iteration store the Train MSE and OOB score
After this we will have 35 Train MSE values and 35 OOB scores
using these 35 values (assume like a sample) find the confidence intravels of MSE and OOB Score
you need to report CI of MSE and CI of OOB Score
Note: Refer the Central_Limit_theorem.ipynb to check how to find the confidence intravel


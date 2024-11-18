There are 5 shape metrics used: elastic scaled metric, elastic unscaled metric with elastic representation of shapes, 
Full Procrustes metric, Kendall scaled metric, Kendall unscaled metric with Kendall's representation of shapes. 

Data in nested sturcture: factor-cell,animal,type of mitochondria (SS/IMF), exercise(Running/Sedentary)

ReSampleCurve.m
Resample the original data to get N points on the boundary

plot_color_map.m
to display the distance matrix between two samples/groups

AllShape.mat contains all the reampled boundary, to make the code run faster we resample 50 points on the boundary.
%%%Data: 12 animal in total.X1,X2,...,X12 
%%%Each animal contain several cells: 4, 5 or 6.
%%%n1,n2,...,n12 = number of mitochondria shapes in each cell of each animal

Ex: folder--ElasticShapeScaled


ElasticDistance.m
used to calculate the elastic scaled metric between two shapes/boundaries. 

ElasticDisMat.m
used to get the distance matrix between two groups/samples of shapes. 
To improve effciency, I use parallel computing with "parfor", it's just "for" looping.

EnergyStat2sample.m
used the calculate the energy statistic of two groups/samples

EnergyStatksample.m
used the calculate the energy statistic of k groups/samples

PermutationTest.m
use permutation test to get the p-value of energy test with energy statistic

TestStatistic.m
to test the significance of one factor when it contains another significant factor. 
For example, to test the the significance of animal when it contains another significant factor--cell.
I designed two test statistic: delta and epsilon but we think epsilon is better. 

TwoAnimalPermutation.m
use permutation test to get the p-value of of TestStatistic.m. Here, it's only for two-sample test 
because of the mitochondria data. If you have k-sample, you can design k-sample test statistic like 
energy statistic.


GetDistanceMat.m
to get the distance matrix. It takes a long time with elastic metrics and also large memory of the computer.
You may want to get it step by step.





linear regression with julia
================

Using Julia to predict Online News Popularity
---------------------------------------------

We will try to predict Online News Popularity fitting Linear Regression with **Knet** library in **Julia**
###### N.B. we'll be using Julia version 0.6.4
First we download the zip data file, unzip it and then move the csv file to the project directory which contains the script...

``` r
wget https://archive.ics.uci.edu/ml/machine-learning-databases/00332/OnlineNewsPopularity.zip 

## or with 
curl -s 'https://archive.ics.uci.edu/ml/machine-learning-databases/00332/OnlineNewsPopularity.zip' -o OnlineNewsPopularity.zip

## then 
tar -xvjf OnlineNewsPopularity.zip 
# x OnlineNewsPopularity/
# x OnlineNewsPopularity/OnlineNewsPopularity.names
# x OnlineNewsPopularity/OnlineNewsPopularity.csv

mv OnlineNewsPopularity/OnlineNewsPopularity.csv project/path
cd project/path
```
Then we run the script from the command line ...

``` r
$ julia popularity_linear_regression.jl

### READING DATA ###
(:data_shape, (39644, 59))

# Preparing Data:
* scaling X, log Y, and split data into train and test
# Check that both data are of the same distribution
7.4740787 , 7.4818397

# size of train and test data
(58, 35680)(58, 3964)

# Define the Model:
* predict, loss, and train functions and initial coeffs and the intercept

### FITTING THE MODEL ###
(:epoch, 1, :train_loss, 14.83188387160643, :test_loss, 14.88458312988758)
(:epoch, 2, :train_loss, 4.357709047995799, :test_loss, 4.381402929182324)
# ......
(:epoch, 10, :train_loss, 0.8663710537913094, :test_loss, 0.8611728589672556)

# plotting the loss of train and data
# a loss plot has been saved into your directory
```

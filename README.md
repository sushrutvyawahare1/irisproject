# irisproject #

###### Working with iris DataSet ######

## Loading DataSet ##

data("iris")
iris

## Look at first 5 rows of data for each class ##

subset(iris, Species == "setosa")[1:5,] # For setosa class

subset(iris, Species == "versicolor")[1:5,] # For versicolor class

subset(iris, Species == "virginica")[1:5,] # For virginica class

## Summarizing the DataSet ##

summary(iris)

## Analysing DataSet through Boxplot ##

par(mar=c(7,5,1,1)) # more space to labels
boxplot(iris,las=2)

## Create Box Plot for each Soecies ##

irisVer <- subset(iris, Species == "versicolor")
irisSet <- subset(iris, Species == "setosa")
irisVir <- subset(iris, Species == "virginica")
par(mfrow=c(1,3),mar=c(6,3,2,1))
boxplot(irisVer[,1:4], main="Versicolor",ylim = c(0,8),las=2)
boxplot(irisSet[,1:4], main="Setosa",ylim = c(0,8),las=2)
boxplot(irisVir[,1:4], main="Virginica",ylim = c(0,8),las=2)

## Predict the class of the flower based on available attributes ##
# Creating the scatterplot # 

pairs(iris[,1:4], colour = iris$Species)
pairs(iris[,1:4],col=iris[,5],oma=c(4,4,6,12))
par(xpd=TRUE)
legend(0.85,0.6, as.vector(unique(iris$Species)),fill=c(1,2,3))

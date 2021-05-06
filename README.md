# Prediction-using-Supervised-ML
Predicting the percentage of an student based on the no. of study hours. 

# to import the data for the task from the given link.
Data1=read.csv("http://bit.ly/w-data")
head(Data1)

# plotting the distribution of scores.
plot(Data1$Hours,Data1$Scores,main="Scatter Plot",xlab = "Hours Studied",ylab = "Percentage Scored")
cor(Data1$Hours,Data1$Scores)

# to build the regression model.
model = lm(Scores~Hours,data=Data1)
model

# detailed output using summary function
summary(model)

# plotting the regression line.
abline(model)

# to compare actual vs predicted values
Data1$predicted = fitted(model)
Data1$Residual = residuals(model)
Data1

# to predict output for a given value.
p = data.frame(Hours=9.25)
predict(model,p)




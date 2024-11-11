# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary python packages using import statements.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Split the dataset using train_test_split.
4. Calculate Y_Pred and accuracy.
5. Print all the outputs.
6. End the Program.
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: BHAVATHARANI S
RegisterNumber:  212223230032
*/
```

## Output:
```
import pandas as pd
data=pd.read_csv("/content/spam.csv",encoding='Windows-1252')
data.head()
```
![alt text](image.png)
```
data.tail()
```
![alt text](image-1.png)
```
data.info()
```
![alt text](image-2.png)
```
data.isnull().sum()
```
![alt text](image-3.png)
```
x=data['v2'].values
y=data['v1'].values
```
```
y.shape
```
![alt text](image-4.png)
```
x.shape
```
![alt text](image-5.png)
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
x_train.shape
```
![alt text](image-6.png)
```
y_train.shape
```
![alt text](image-7.png)
```
x_test.shape
```
![alt text](image-8.png)
```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
x_train = cv.fit_transform(x_train)  
x_test = cv.transform(x_test)
```
```
x_train.shape
```
![alt text](image-9.png)
```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred 
```
![alt text](image-10.png)
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![alt text](image-11.png)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.

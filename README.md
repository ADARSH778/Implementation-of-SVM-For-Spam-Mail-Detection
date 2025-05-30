# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start the Program.
2. Import the necessary packages. 
3. Read the given csv file and display the few contents of the data.
4. Assign the features for x and y respectively.
5. Split the x and y sets into train and test sets.
6. Convert the Alphabetical data to numeric using CountVectorizer.
7. Predict the number of spam in the data using SVC (C-Support Vector Classification) method of SVM (Support vector machine) in sklearn library.
8. Find the accuracy of the model.
9. End the Program.
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: ADARSH CHOWDARY R
RegisterNumber:  212223040166
*/
import chardet
file='spam.csv'
with open(file,'rb') as rawdata:
    result=chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding='Windows-1252')
data.head()
data.info()
data.isnull().sum()
x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
### data.head()
![image](https://github.com/user-attachments/assets/c4720918-77b0-47a2-8d05-e8e9cfeefc6e)

### data.info()
![image](https://github.com/user-attachments/assets/d17f4642-74f5-4f3a-9b90-a2ef8a1d6215)

### data.isnull().sum()
![image](https://github.com/user-attachments/assets/4879afbb-5a53-44b1-8bc5-474506366e4f)

### Y Prediction
![image](https://github.com/user-attachments/assets/110ad0b3-b958-4061-b370-43545370026b)

### Accuracy
![image](https://github.com/user-attachments/assets/1a0653df-8d93-4eef-9a10-b295528f6ca3)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.

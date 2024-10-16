# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the data and use label encoder to change all the values to numeric.
2. Drop the unwanted values,Check for NULL values, Duplicate values.
3. Classify the training data and the test data.
4. Calculate the accuracy score, confusion matrix and classification report.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: SARANYA S
RegisterNumber:  212223110044
*/
```
```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
data=pd.read_csv('/content/Placement_Data_Full_Class (1).csv')
data
```
![image](https://github.com/user-attachments/assets/10340e55-c103-4e7e-982e-3123ad2ff57e)

```
data.head()
```
![image](https://github.com/user-attachments/assets/88902f8c-9258-435d-a08d-8fb10631147b)

```
data.tail()
```
![image](https://github.com/user-attachments/assets/d490db12-64a8-48d0-8b2d-4013daa8f948)

```
data.info()
```
![image](https://github.com/user-attachments/assets/63859368-e6f7-45a0-b675-89e609449170)

```
data.drop('sl_no',axis=1)
```
![image](https://github.com/user-attachments/assets/9c09222c-45e1-4fd6-815a-693e1224f13c)

```
data["gender"]=data["gender"].astype('category')
data["ssc_b"]=data["ssc_b"].astype('category')
data["hsc_b"]=data["hsc_b"].astype('category')
data["hsc_s"]=data["hsc_s"].astype('category')
data["degree_t"]=data["degree_t"].astype('category')
data["workex"]=data["workex"].astype('category')
data["specialisation"]=data["specialisation"].astype('category')
data["status"]=data["status"].astype('category')
data.info()
```
![image](https://github.com/user-attachments/assets/45f427fc-9cc4-4783-86ff-aa269c3975aa)

```
data["gender"]=data["gender"].cat.codes
data["ssc_b"]=data["ssc_b"].cat.codes
data["hsc_b"]=data["hsc_b"].cat.codes
data["hsc_s"]=data["hsc_s"].cat.codes
data["degree_t"]=data["degree_t"].cat.codes
data["workex"]=data["workex"].cat.codes
data["specialisation"]=data["specialisation"].cat.codes
data["status"]=data["status"].cat.codes
data
```
![image](https://github.com/user-attachments/assets/02a8ca2a-efd9-449a-9ae8-ed76dbd16447)

```
data.info()
```
![image](https://github.com/user-attachments/assets/de3163f6-c59f-41b5-913e-4da420291c2d)

```
x=data.iloc[:,:-1].values
y=data.iloc[:,-1].values
```
```
x
y
```
![image](https://github.com/user-attachments/assets/eb95a00e-4991-482c-bbe9-f0ca315095cb)

```
x.shape
y.shape
```
![image](https://github.com/user-attachments/assets/9098c72a-2d78-4fb2-a201-ccad1eefe07e)
![image](https://github.com/user-attachments/assets/a3407ce0-16b4-4977-9d84-8c4795c46e78)

```
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=1)
```
```
x_train.shape
x_test.shape
y_train.shape
y_test.shape
```
![image](https://github.com/user-attachments/assets/9e2c0f32-df85-4e48-b19b-df5603cd0bea)

```
clf=LogisticRegression()
clf.fit(x_train,y_train)
```
![image](https://github.com/user-attachments/assets/376c6876-82b3-427e-a564-06d9bc7df978)

```
y_pred=clf.predict(x_test)
```
```
y_pred
```
![image](https://github.com/user-attachments/assets/9aecd86e-85eb-40e2-9c09-dd4cd80bcd93)

```
from sklearn.metrics import confusion_matrix,accuracy_score
```
```
cf=confusion_matrix(y_test,y_pred)
print(cf)
```
![image](https://github.com/user-attachments/assets/17ea13d2-d58a-4cab-b352-f4c927c17c47)

```
accuracy=accuracy_score(y_test,y_pred)
print(accuracy)
```
![image](https://github.com/user-attachments/assets/8b981328-7908-400c-b388-264b23142f27)






## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.

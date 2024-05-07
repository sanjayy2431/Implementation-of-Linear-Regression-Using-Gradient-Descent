# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.
## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook
## Algorithm
1.Initialize weights randomly.
2.Compute predicted values.
3.Compute gradient of loss function.
4.Update weights using gradient descent.   
## Program:
Program to implement the linear regression using gradient descent.    
Developed by: sanjay.v     
RegisterNumber:  212223230188    

import numpy as np     
import pandas as pd      
from sklearn.preprocessing import StandardScaler    
def linear_regression(X1,y,learning_rate=0.1,num_iters=100):    
    X=np.c_[np.ones(len(X1)),X1]     
    theta=np.zeros(X.shape[1]).reshape(-1,1)    
    for _ in range(num_iters):     
      #calculate predictions      
      predictions=(X).dot(theta).reshape(-1,1)     
        #calculate errors        
      errors=(predictions-y).reshape(-1,1)    
      #update theta using gradiant descent      
    theta-=learning_rate*(1/len(X1))*X.T.dot(errors)     
    return theta     
data=pd.read_csv("C:/Users/admin/Desktop/50_Startups.csv")     
data.head()     
X=(data.iloc[1:,:-2].values)     
X1=X.astype(float)     
scaler=StandardScaler()    
y=(data.iloc[1:,-1].values).reshape(-1,1)     
X1_Scaled=scaler.fit_transform(X1)     
Y1_Scaled=scaler.fit_transform(y)     
print(X)     
print(X1_Scaled)     
## Output:

![image](https://github.com/sanjayy2431/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/149365143/0dabb6a6-25ad-484d-80cc-2de5549e9496)
```

[[162597.7  151377.59 443898.53]       
 [153441.51 101145.55 407934.54]      
 [144372.41 118671.85 383199.62]      
 [142107.34  91391.77 366168.42]      
 [131876.9   99814.71 362861.36]      
 [134615.46 147198.87 127716.82]      
 [130298.13 145530.06 323876.68]      
 [120542.52 148718.95 311613.29]     
 [123334.88 108679.17 304981.62]     
 [101913.08 110594.11 229160.95]     
 [100671.96  91790.61 249744.55]     
 [ 93863.75 127320.38 249839.44]     
 [ 91992.39 135495.07 252664.93]     
 [119943.24 156547.42 256512.92]     
 [114523.61 122616.84 261776.23]     
 [ 78013.11 121597.55 264346.06]    
 [ 94657.16 145077.58 282574.31]    
 [ 91749.16 114175.79 294919.57]     
 [ 86419.7  153514.11      0.  ]     
 [ 76253.86 113867.3  298664.47]     
 [ 78389.47 153773.43 299737.29]    
 [ 73994.56 122782.75 303319.26]     
 [ 67532.53 105751.03 304768.73]      
 [ 77044.01  99281.34 140574.81]     
 [ 64664.71 139553.16 137962.62]     
 [ 75328.87 144135.98 134050.07]     
 [ 72107.6  127864.55 353183.81]     
 [ 66051.52 182645.56 118148.2 ]    
 [ 65605.48 153032.06 107138.38]     
 [ 61994.48 115641.28  91131.24]     
 [ 61136.38 152701.92  88218.23]     
 [ 63408.86 129219.61  46085.25]      
 [ 55493.95 103057.49 214634.81]      
 [ 46426.07 157693.92 210797.67]    
 [ 46014.02  85047.44 205517.64]    
 [ 28663.76 127056.21 201126.82]     
 [ 44069.95  51283.14 197029.42]     
 [ 20229.59  65947.93 185265.1 ]     
 [ 38558.51  82982.09 174999.3 ]     
 [ 28754.33 118546.05 172795.67]     
 [ 27892.92  84710.77 164470.71]     
 [ 23640.93  96189.63 148001.11]     
 [ 15505.73 127382.3   35534.17]     
 [ 22177.74 154806.14  28334.72]     
 [  1000.23 124153.04   1903.93]     
 [  1315.46 115816.21 297114.46]     
 [     0.   135426.92      0.  ]    
 [   542.05  51743.15      0.  ]    
 [     0.   116983.8   45173.06]]    
[[ 2.06444689e+00  1.08674530e+00  2.04710611e+00]    
 [ 1.85614613e+00 -7.11896632e-01  1.73802284e+00]    
 [ 1.64982664e+00 -8.43382418e-02  1.52544492e+00]     
 [ 1.59829693e+00 -1.06114699e+00  1.37907465e+00]     
 [ 1.36555729e+00 -7.59549576e-01  1.35065297e+00]     
 [ 1.42785876e+00  9.37119267e-01 -6.70236359e-01]     
 [ 1.32964071e+00  8.77364743e-01  1.01560916e+00]      
 [ 1.10770332e+00  9.91548265e-01  9.10214603e-01]     
 [ 1.17122873e+00 -4.42142808e-01  8.53220419e-01]     
 [ 6.83888775e-01 -3.73575189e-01  2.01599152e-01]    
 [ 6.55653643e-01 -1.04686585e+00  3.78499613e-01]     
 [ 5.00768772e-01  2.25336793e-01  3.79315121e-01]     
 [ 4.58195856e-01  5.18045196e-01  4.03598069e-01]     
 [ 1.09406987e+00  1.27185968e+00  4.36668630e-01]     
 [ 9.70774801e-01  5.69187019e-02  4.81902796e-01]     
 [ 1.40171151e-01  2.04213242e-02  5.03988539e-01]     
 [ 5.18818627e-01  8.61162942e-01  6.60646550e-01]     
 [ 4.52662441e-01 -2.45327166e-01  7.66744716e-01]     
 [ 3.31418719e-01  1.16324696e+00 -1.76786575e+00]     
 [ 1.00148706e-01 -2.56373164e-01  7.98929296e-01]     
 [ 1.48733235e-01  1.17253235e+00  8.08149372e-01]    
 [ 4.87502635e-02  6.28593860e-02  8.38933693e-01]      
 [-9.82591094e-02 -5.46989742e-01  8.51390791e-01]    
 [ 1.18124397e-01 -7.78647778e-01 -5.59731668e-01]    
 [-1.63501211e-01  6.63351874e-01 -5.82181464e-01]          
 [ 7.91054423e-02  8.27447384e-01 -6.15806869e-01]     
 [ 5.82245190e-03  2.44821707e-01  1.26748176e+00]    
 [-1.31951672e-01  2.20634710e+00 -7.52471405e-01]     
 [-1.42098957e-01  1.14598636e+00 -8.47092475e-01]     
 [-2.24248196e-01 -1.92852853e-01 -9.84661727e-01]      
 [-2.43769731e-01  1.13416515e+00 -1.00969684e+00]      
 [-1.92071447e-01  2.93341889e-01 -1.37179791e+00]      
 [-3.72133433e-01 -6.43436432e-01  7.67579736e-02]     
 [-5.78425164e-01  1.31291203e+00  4.37806597e-02]        
 [-5.87799186e-01 -1.28831630e+00 -1.59720149e-03]       
 [-9.82512742e-01  2.15877746e-01 -3.93329758e-02]         
 [-6.32026234e-01 -2.49730335e+00 -7.45470274e-02]      
 [-1.17438775e+00 -1.97220609e+00 -1.75652453e-01]      
 [-7.57409950e-01 -1.36226960e+00 -2.63879233e-01]        
 [-9.80452300e-01 -8.88427205e-02 -2.82817765e-01]           
 [-1.00004914e+00 -1.30037133e+00 -3.54364495e-01]       
 [-1.09678072e+00 -8.89351609e-01 -4.95908241e-01]         
 [-1.28185424e+00  2.27553942e-01 -1.46247646e+00]          
 [-1.13006788e+00  1.20951025e+00 -1.52435028e+00]      
 [-1.61185030e+00  1.11924904e-01 -1.75150292e+00]       
 [-1.60467891e+00 -1.86589193e-01  7.85608134e-01]          
 [-1.63460525e+00  5.15604972e-01 -1.76786575e+00]           
 [-1.62227377e+00 -2.48083192e+00 -1.76786575e+00]         
 [-1.63460525e+00 -1.44781686e-01 -1.37963750e+00]]     
#learn model Parameters    
theta=linear_regression(X1_Scaled,Y1_Scaled)      
#Predict target value for a data point        
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)     
new_Scaled=scaler.fit_transform(new_data)        
prediction=np.dot(np.append(1,new_Scaled),theta)     
prediction=prediction.reshape(-1,1)         
pre=scaler.inverse_transform(prediction)           
print(prediction)     
print(f"Predicted value: {pre}")    
```
## PREDICTED VALUE:      
![image](https://github.com/sanjayy2431/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/149365143/895b9a4c-cbee-4669-a1b6-245fb960abe5)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.

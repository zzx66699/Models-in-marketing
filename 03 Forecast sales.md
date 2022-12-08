# Chapter3 Forecast sales

## 1. Simple Forecast in excel
<img width="444" alt="image" src="https://user-images.githubusercontent.com/105503216/206354985-599054a2-2991-4026-af53-0c981251714c.png">

## 2. Seasonality and Trend Forecasting with linear regression
<img width="204" alt="image" src="https://user-images.githubusercontent.com/105503216/206356794-2a2ae1ee-cebd-48b4-b5d8-30a56c6ec20f.png">  
1. add a column called 'periods' because it only recognize numbers  
<img width="291" alt="image" src="https://user-images.githubusercontent.com/105503216/206356896-fba671e0-d4de-4947-aebd-ce53260e8aa4.png">   

2. calculate the Intercept and slope  
<img width="245" alt="image" src="https://user-images.githubusercontent.com/105503216/206357016-6ee7afa9-a495-4d2c-961d-d3fa2666da5b.png"><img width="207" alt="image" src="https://user-images.githubusercontent.com/105503216/206357072-354da45d-7ddc-415e-91ce-07c11009b954.png">  

3. calculate the linear trend forecast  
<img width="550" alt="image" src="https://user-images.githubusercontent.com/105503216/206357260-6ab9dc0b-eaec-48e2-9f24-358d2b7da1fc.png"><img width="339" alt="image" src="https://user-images.githubusercontent.com/105503216/206357300-eed087a3-22ef-4499-94bf-3bc8a250a220.png">  

linear trend forecast can capture the trend but it can not capture seasonal up and downs  
<img width="429" alt="image" src="https://user-images.githubusercontent.com/105503216/206357459-adc3e6c2-c8e9-420e-a8ca-155584acfdde.png">  
so we need to add seasonal trend into it  

4. adjust monthly values according to seasonality
```
seasonal index = average January demand / average demand throughout all three years  
```

<img width="612" alt="image" src="https://user-images.githubusercontent.com/105503216/206358075-0c4f0fd6-01ae-4ca5-97aa-80178ca3dbe4.png"><img width="209" alt="image" src="https://user-images.githubusercontent.com/105503216/206358107-5acfca36-47ec-4964-90cb-ba12bb4f0fe8.png">

5. Seasonal forecast with trend  
<img width="643" alt="image" src="https://user-images.githubusercontent.com/105503216/206358379-83c5ac0e-16e9-4011-a7b6-1795361e12a2.png"><img width="182" alt="image" src="https://user-images.githubusercontent.com/105503216/206358426-9f2e8472-a884-41c5-862b-f61701b6cc86.png">

6. predict the future  
<img width="526" alt="image" src="https://user-images.githubusercontent.com/105503216/206358668-db188a72-18d8-46ca-a3a8-44e867d9644e.png">
<img width="487" alt="image" src="https://user-images.githubusercontent.com/105503216/206358712-2ef38349-0c21-44b7-9916-a2679bf2ff91.png">








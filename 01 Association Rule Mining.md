# Chapter1 association rule mining

## 1. Definition  
### 1.1 Association rules
Association rules, which are typically written in the form {A} → {B}, where the two items A and B exhibit some sort of relationship to happen together.  
In other word, the presence of A many imply the the presence of B with some probability.  

### 1.2 market basket
A market basket is a group of one or more items that a customer purchases in one transaction.

### 1.3 Antecedent and Consequent
The IF component of an association rule is known as the antecedent.   
The THEN component is known as the consequent.

### 1.4 Support
Support of product is the fraction of transactions that contain that product. For example, there are totally 10 orders, and 5 orders contain applicator, so the support of applicator is 50%.
We can also calculate the support of itemsets. 

### 1.5 Frequent item sets 
individual item sets that meet or exceed a given minimum support threshold.  

### 1.6 Confidence
Confidence({A} → {B}): If A happens, what the probability will B happens    
I: frequent max-item set
S: subset of I, 
If Confidence (S -> (I-S)) > min_confidence, the S -> I-S is strong association rule  

### 1.7 High confidence rules 
Confidence or meet or exceed a predefined confidence threshold.  

### 1.8 Lift
<img width="298" alt="image" src="https://user-images.githubusercontent.com/105503216/206885385-aa615156-8684-4baf-ab16-a38a2e907da1.png">  
the denominator of formula representS the randomless occurance of A & B (as the multiply of occurance A and occurance B)  
If lift < 0 : the occurance of randomness is more than occurance because of any association, so we don't need to spend any time on the particular rule we got  

## 2. Example1: 
### 2.1 Step1: Find the frequent item sets (support of the item sets > min_support)   
<img width="446" alt="image" src="https://user-images.githubusercontent.com/105503216/206842691-19c5ac6f-9cee-4cd3-8ef7-966eea32a0a6.png">

#### 2.1.1 count the frequency of 1-item set and filter only the frequent 1-item set
<img width="361" alt="image" src="https://user-images.githubusercontent.com/105503216/206842712-ac6724ee-c25b-462b-a35c-4696a160b403.png"><img width="425" alt="image" src="https://user-images.githubusercontent.com/105503216/206842752-0105bd3b-fcd2-4109-8ecd-bffe851c38b6.png">

#### 2.1.2 count the frequency of 2-item set and filter only the frequent 2-item set
The Apriori principle states that if an item set is frequent then all of its subsets will also be frequent, and vice versa.   
Therefore, if item i does not frequent, then no item sets that include item i will appear be frequent.   
That's why when we try to indentify the 2-items sets, we only need to analyse the possible sets made up by frequent 1-item set, not all the 1-item set.   
<img width="362" alt="image" src="https://user-images.githubusercontent.com/105503216/206842952-a302e209-5433-49a4-8002-f58bc82c54e5.png"><img width="434" alt="image" src="https://user-images.githubusercontent.com/105503216/206842958-fdb0b20a-a650-4ef7-98da-28bdbc8eb1f4.png">

#### 2.1.3 count the frequency of 3-item set and filter only the frequent 3-item set
Also, only analyse the 3-item set made up by the unique item in frequent 2-item set   
<img width="482" alt="image" src="https://user-images.githubusercontent.com/105503216/206843121-067f85b8-5fed-4b8f-a975-74e4c7fe65f4.png"><img width="443" alt="image" src="https://user-images.githubusercontent.com/105503216/206843137-17799d37-8187-400b-ae30-d5824491ea3a.png">  
 We only have 3 unique item in frequent 3-item set, so we can not have 4-item sets  

### 2.2 Step2: Explore association rules (confidence of > min_confidence)  
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206857350-af0ccd5c-ad5b-490f-9b26-02d30bc98508.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206857329-5f3a94ce-f3f6-4333-b0c4-574e73092c92.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206857423-7ff67734-9e45-4bef-8649-65e7085fc518.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206857449-5a6ef7ee-995b-4785-9987-e3cd85b7585c.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206857473-cd214b51-2de0-43a3-ae93-16cd9f5b9f0a.png">  
Because P(A) * P(B/A) = P(A, B)    

confidence (A implies B) = P (B/A) = P(A, B) / P(A)  

## 3. Example2:
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858229-5ba8a920-6b76-4ec3-a32d-849e81e55f02.png"><img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858756-9ea74f0d-6d54-4ddd-9543-211538f3ea20.png">
There are 3 frequent 3-item set, so we need to calculate the confidence respectively    

### 3.1 First frequent 3-item set
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858387-55485344-b2d0-4e4b-a562-5439bf7708fe.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858413-755a16db-e3bc-471a-af75-cd9890004374.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858425-89e424de-eec7-4dc5-9b19-710031103cea.png">

### 3.2 Second frequent 3-item set
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858440-771db5ad-4391-4c5b-bbc1-0840d88caccd.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858462-08766f64-f473-4033-9a7e-50adb0592ae0.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/206858475-202b0dd3-66b1-4c78-ae33-dc1789b2d627.png">

## 4. Example3:

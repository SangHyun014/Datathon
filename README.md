# Datathon


## Contents
    1. 분석 목표
    2. 어떤 Data 인가?
    3. EDA(Exploration Dataa Analysis)
    4. 결론
    5. 회고
---    
### 분석 목표
 - 세일 기간 및 판매 행사를 위해 소비자가 주로 방문하는 요일과 시간대를 파악하고, 구매한 품목 별 관계를 통해 행사 품목을 지정하고자 한다.

---
### 어떤 Data 인가?
|**Folder**|Column|
|-----|---|
|orders|order_id : 주문 ID<br>user_id : 구매자 ID<br>eval_set :  prior/tain/test로 나뉘며, 마지막 주문은 train/test로 나뉜다.<br>order_number : 주문 수<br>order_dow : 주문 요일<br>order_hour_of_day : 주문 시간<br>days_since_prior_order : 재주문 시간<br>(하나의 행은 하나의 주문)|
|order_products_train<br>order_products_prior|order_id : 주문 ID<br>product_id : 상품 ID<br>add_to_cart_order : 해당 상품이 몇 번쨰 순서에 주문이 되었는가?<br>reordered : 재주문 여부|
|products|product_id : 상품 ID<br>product_name : 상품명<br>aisle_id : 진열대 ID<br>department_id : 상품군 ID|
|aisles|aisle_id : 진열대 ID<br>aisle : 진열대명|
|departments|department_id : 상품군 ID<br>department : 상품군명|

---
### EDA
우선 orders data를 먼저 살펴보자

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c0d399c7-0344-4a7c-a0e5-5d0b4621618f/Untitled.png)

해당 graph는 eval_set column을 종류 별로 분류한 것이다.

총 data 중 prior이 압도적으로 많음을 보여주고 있다.

train 데이터를 추가해도 결과에 미치는 영향이 미미할 것 같아서 prior만 가지고 EDA를 진행하였다.

order_product_prior와 다른 csv 파일들을 merge하여 하나의 데이터셋으로 만들어준 후 다음을 분석하였다.

1. 어느 제품군에서 많이 팔렸는가?
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/84b75214-f7a6-444f-88d7-3ce4db36ed66/Untitled.png)
    
    농수산물을 의미하는 produce가 제일 많이 팔렸고, 다음으로 달걀/유제품이 많이 팔렸다.
    
2. 어느 진열대에서 많이 팔렸는가?
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a518277-ecfb-4bbe-9a14-b8f2145842da/Untitled.png)
    
    신선 과일, 신선 채소와 같은 농산물이 가장 많이 팔렸고, 요거트, 치즈, 우유와 같은 유제품류도 다음으로 많이 팔린 것을 확인할 수 있다.
    
3. 어떤 제품이 많이 팔렸는가?
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/80eef256-e747-4f28-a826-a037dd26b844/Untitled.png)
    
    바나나가 압도적으로 많이 팔린 것을 확인할 수 있다. 유기농 제품들도 눈에 보인다.
    
4. 제품군 별 진열대 정보 시각화
    
    ![newplot.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2c1262a5-894d-4a42-9505-697c8a5ffd73/newplot.png)

---
### 결론

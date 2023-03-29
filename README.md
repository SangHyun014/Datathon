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

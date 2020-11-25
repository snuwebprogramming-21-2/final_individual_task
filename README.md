# final_individual_task

## 개요

가상의 코인 거래소를 제쟉한다. 유저는 회원가입, 자산 조회, 시세 조회, 구매 및 판매의 행위를 할 수 있다.  

## 가격조회

가격은 https://www.coingecko.com/en/api 의 api를 이용해서 가져온다. (https://www.coingecko.com/api/documentations/v3#/simple/get_simple_price)  
거래가능한 코인의 종류는 btc, xrp, eth, bch 4가지로 제한한다.  


## api 명세

성공 시 status 2xx, 클라이언트 에러로 실패 시 4x코드로 반환. 
모든 response data는 json 형태.  
authentication 필요한 코드의 경우, header의 Authorization에 Bearer: {Key} 를 포함해서 호출함.  
에러가 날 경우, {error: '{reason}'}를 보내도록.


### /register
회원가입 시 유저에게 10,000$를 제공한다.  
[:POST]

request


- name: string. 4-12글자. alphanumeric
- email: string. 100자 미만. email형식
- password: 8-16글자.


response
 - {}

### /login
[:POST]

request
- email
- password


response
- {key: {key}}

### /coins
[:GET]

request


response
- ["btc", "xrp", "bch", "eth"]

### /assets
본인의 자산을 조회한다. 없는 자산의 경우 노출시키지 않는다.
[:GET]
:auth_required  


request

response
- ["usd: 3000, "btc": 1, "xrp": 2, "bch": 3, "eth": 4]


### /coins/:coin_name/buy
코인을 구매한다.
[:POST]
:auth_required  


request
- quantity: number. 소수점 4번째 자리까지.


response
- 

## 기본 스펙



## models

## 심화 스펙

* jwt 를 이용한 로그인 구현 (https://jwt.io/)

## 제출일


## 제출방법

etl 기말과제 

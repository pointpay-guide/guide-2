# πμ»¨νμΈ κ°λ§Ήμ  μ°λ κ°μ΄λ

- [μ€λ¬Όκ°λ§Ήμ ](../../../guide-1/#μ€λ¬Όκ°λ§Ήμ -μ°λ-κ°μ΄λ)   
- [μ»¨νμΈ κ°λ§Ήμ ](#μ»¨νμΈ κ°λ§Ήμ -μ°λ-κ°μ΄λ)   
- [λ΄λΉμ μ λ³΄](../../../Responsibility/#λ΄λΉμ-μ λ³΄)   

---

## λͺ©μ°¨
- [μλ°μ΄νΈ](#μλ°μ΄νΈ)   
- [λλ©νμ΄μ§](#λλ©νμ΄μ§)   
- [κ²°μ νμ](#κ²°μ νμ)   
- [ν¬μΈνΈ μ ν ν](#ν¬μΈνΈ-μ ν-ν)   

<br/>

## μλ°μ΄νΈ
- 21.12.20 μ°λκ°μ΄λ μ μ

<br/>

## λλ©νμ΄μ§

|μλ²|URL|μ μ‘ λ°©λ²|
|----|------|:---:|
|κ°λ°|http://dev.pointpay.im/landing/main|GET|
|μμ©|https://ssl.pointpay.im/landing/main|GET|

|μ λ¬ νλΌλ―Έν°|λ΄μ©|νμμ¬λΆ|
|------|---|:---:|
|`a_code`|λ§€μ²΄μ½λ(ν¬μΈνΈνμ΄ λ°κΈμμ΄λ)|O|
|`user_id`|λ§€μ²΄ νμμμ΄λ (λ‘κ·ΈμΈμ μλ£ν νμ λμ)|O|
|`ui_type`|UI νμ(ν¬μΈνΈνμ΄ μ λ¬ κ°)|O|
|`add_param`|μμ²΄ μμ²­ νλΌλ―Έν° (νμμ μΆκ°)||


 _*λͺ¨λ  νλΌλ―Έν°λͺμ μλ¬Έμλ₯Ό μ¬μ©ν©λλ€._


 **μμ)**
 ```
https://ssl.pointpay.im/landing/main?a_code=λ§€μ²΄μ½λ&user_id=λ§€μ²΄νμμμ΄λ&ui_type=UIνμ
 ```
<br/>

## κ²°μ νμ

#### νμ νΈμΆ λ°©μ

JSλ₯Ό ν΅ν νμμ°½ μ€ν λ°©μμλλ€.

|μλ²|URL|μ μ‘ λ°©λ²|
|-----|------|:---:|
|κ°λ°|http://dev.pointpay.im/popup/main|GET|
|μμ©|https://ssl.pointpay.im/popup/main|GET|

|μ λ¬ νλΌλ―Έν°|λ΄μ©|νμμ¬λΆ|
|------|---|:---:|
|`a_code`|λ§€μ²΄μ½λ(ν¬μΈνΈνμ΄ λ°κΈμμ΄λ)|O|
|`user_id`|λ§€μ²΄ νμμμ΄λ (λ‘κ·ΈμΈμ μλ£ν νμ λμ)|O|
|`pu_type`|νμ νμ(ν¬μΈνΈνμ΄ μ λ¬ κ°)|O|
|`add_param`|μμ²΄ μμ²­ νλΌλ―Έν° (νμμ μΆκ°)||

 _*λͺ¨λ  νλΌλ―Έν°λͺμ μλ¬Έμλ₯Ό μ¬μ©ν©λλ€._


 **μμ)**
```js
window.open(
'https://ssl.pointpay.im/popup/main?a_code=λ§€μ²΄μ½λ&user_id=λ§€μ²΄νμμμ΄λ&pu_type=νμνμ', 
'width=510, height=800, resizable=0, scrollbars=no, status=0, titlebar=0, toolbar=0, left=435, top=100' 
);
```
<br/>

## ν¬μΈνΈ μ ν ν

μ ν ν λ§€μ²΄ ν¬μΈνΈμ λ¦½ μ²λ¦¬(ν¬μΈνΈ, μΊμ λ±)λ₯Ό μν RETURN URLμ
[κ°λ°ν]() μ μ λ¬ν΄μ£Όμλ©΄ λ©λλ€.

 **μμ)**
```
http://λ§€μ²΄λλ©μΈ/event/result.php
```

|μ λ¬ νλΌλ―Έν°|μ€λͺ|νμ|μμ|
|------|--------|------|------|
|`rw_pay_type`|κ²°μ κ΅¬λΆ|Varchar|KT|
|`rw_user_id`|λ§€μ²΄ νμμμ΄λ|Varchar|pointpay
|`rw_price`|μ νν¬μΈνΈ|Int|10000
|`rw_reg_datetime`|κ±°λμκ°|Date|2021-12-17 11:25:36
|`rw_a_code`|κ±°λλ§€μ²΄μ½λ|Varchar|ν¬μΈνΈνμ΄ λ°κΈμμ΄λ
|`rw_orderno`|κ±°λλ²νΈ|Varchar|ME2021121733235510625855
|`utc_code`|λ§€μ²΄ μμ²­νλΌλ―Έν°|Varchar|ETC

 _*λͺ¨λ  νλΌλ―Έν°λͺμ μλ¬Έμλ₯Ό μ¬μ©ν©λλ€._

### μν λ¦¬ν΄

κ²°κ³Ό μλ΅μ½λλ₯Ό Textκ°μΌλ‘ λ°νν΄μ£ΌμΈμ.   
> μλ΅μΌλ‘ JSμ alert μ¬μ©μ ERRORκ° λ°μνλ, μ°Έκ³ ν΄μ£ΌμΈμ.    
   
</br>

#### μ λ¦½ μ±κ³΅μΈ κ²½μ° μλ΅μ½λ
```
201
```

#### μ λ¦½ μ€ν¨μΈ κ²½μ° μλ΅μ½λ 

μ λ¦½ μ€ν¨μΈ κ²½μ° μ€ν¨μ¬μ λ₯Ό κ΅¬λΆμ "|-|" (νμ΄νλΌμΈ νμ΄ν νμ΄νλΌμΈ)κ³Ό ν¨κ» μμ±ν΄μ£ΌμΈμ.   
```
202|-|κ±°λλ²νΈ μ€λ³΅
202|-|κ±°λλ²νΈ μ€λ³΅   
202|-|μμ΄λ μμ
```



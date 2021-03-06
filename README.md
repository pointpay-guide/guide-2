# 📝컨텐츠가맹점 연동 가이드

- [실물가맹점](../../../guide-1/#실물가맹점-연동-가이드)   
- [컨텐츠가맹점](#컨텐츠가맹점-연동-가이드)   
- [담당자 정보](../../../Responsibility/#담당자-정보)   

---

## 목차
- [업데이트](#업데이트)   
- [랜딩페이지](#랜딩페이지)   
- [결제팝업](#결제팝업)   
- [포인트 전환 후](#포인트-전환-후)   

<br/>

## 업데이트
- 21.12.20 연동가이드 제작

<br/>

## 랜딩페이지

|서버|URL|전송 방법|
|----|------|:---:|
|개발|http://dev.pointpay.im/landing/main|GET|
|상용|https://ssl.pointpay.im/landing/main|GET|

|전달 파라미터|내용|필수여부|
|------|---|:---:|
|`a_code`|매체코드(포인트페이 발급아이디)|O|
|`user_id`|매체 회원아이디 (로그인을 완료한 회원 대상)|O|
|`ui_type`|UI 타입(포인트페이 전달 값)|O|
|`add_param`|업체 요청 파라미터 (필요시 추가)||


 _*모든 파라미터명은 소문자를 사용합니다._


 **예시)**
 ```
https://ssl.pointpay.im/landing/main?a_code=매체코드&user_id=매체회원아이디&ui_type=UI타입
 ```
<br/>

## 결제팝업

#### 팝업 호출 방식

JS를 통한 팝업창 오픈 방식입니다.

|서버|URL|전송 방법|
|-----|------|:---:|
|개발|http://dev.pointpay.im/popup/main|GET|
|상용|https://ssl.pointpay.im/popup/main|GET|

|전달 파라미터|내용|필수여부|
|------|---|:---:|
|`a_code`|매체코드(포인트페이 발급아이디)|O|
|`user_id`|매체 회원아이디 (로그인을 완료한 회원 대상)|O|
|`pu_type`|팝업 타입(포인트페이 전달 값)|O|
|`add_param`|업체 요청 파라미터 (필요시 추가)||

 _*모든 파라미터명은 소문자를 사용합니다._


 **예시)**
```js
window.open(
'https://ssl.pointpay.im/popup/main?a_code=매체코드&user_id=매체회원아이디&pu_type=팝업타입', 
'width=510, height=800, resizable=0, scrollbars=no, status=0, titlebar=0, toolbar=0, left=435, top=100' 
);
```
<br/>

## 포인트 전환 후

전환 후 매체 포인트적립 처리(포인트, 캐시 등)를 위한 RETURN URL을
[개발팀]() 에 전달해주시면 됩니다.

 **예시)**
```
http://매체도메인/event/result.php
```

|전달 파라미터|설명|타입|예시|
|------|--------|------|------|
|`rw_pay_type`|결제구분|Varchar|KT|
|`rw_user_id`|매체 회원아이디|Varchar|pointpay
|`rw_price`|전환포인트|Int|10000
|`rw_reg_datetime`|거래시간|Date|2021-12-17 11:25:36
|`rw_a_code`|거래매체코드|Varchar|포인트페이 발급아이디
|`rw_orderno`|거래번호|Varchar|ME2021121733235510625855
|`utc_code`|매체 요청파라미터|Varchar|ETC

 _*모든 파라미터명은 소문자를 사용합니다._

### 상태 리턴

결과 응답코드를 Text값으로 반환해주세요.   
> 응답으로 JS의 alert 사용시 ERROR가 발생하니, 참고해주세요.    
   
</br>

#### 적립 성공인 경우 응답코드
```
201
```

#### 적립 실패인 경우 응답코드 

적립 실패인 경우 실패사유를 구분자 "|-|" (파이프라인 하이픈 파이프라인)과 함께 작성해주세요.   
```
202|-|거래번호 중복
202|-|거래번호 중복   
202|-|아이디 없음
```



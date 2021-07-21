# 테스트 캠페인 세팅 후 <br> vegas_adkey={adkey} 가 보이지 않을 때
<br>

이런 경우에는 **리다이렉트**를 하고 있어서 발생합니다.

### 1. 리다이렉트 문제
<br>
그러나 광고주의 사이트에서 여러 이유에 의해서 redirect를 해서 다른 페이지로 landing URL을 보내게 되면 <br>
**vegas_adkey={adkey} 값이 url에 보이지 않습니다.**

 vegas_adkey={adkey}은 광고주의 개발자분이 최종 landing 페이지까지(애드맥스의 a 스크립트가 심어있는) url로<br>
 **vegas_adkey={adkey} 파라미터와 값을 전달해주셔야 합니다.**
<br><br>


## A 스크립트에는 1), 2) 조건이 필수적으로 필요합니다.
<br>

#### 1) url에  vegas_adkey={adkey}존재 
#### 2) 쿠키에 vegas_param 존재 
<br><br>


### 2. 애드맥스의 파트너 URL 클릭 시 vegas_adkey={adkey} 파라미터가 존재해야 함.
<br>
애드맥스 캠페인 세팅시 <br>
광고주가 전달 해준 landing URL => edsdf.pe.kr/page_07/index02.asp?sender=ad02&**vegas_adkey={adkey}** 으로 <br>
애드맥스는 캠페인   landing URL로 설정 해놓습니다.
<br><br>
 

애드맥스 파트너 pick URL을 누르면<br>

bs1n.io/v.79AM7 (애드맥스 파트너 pick URL) 애드맥스의 클릭서버를 통해 클릭할 때마다<br>
**vegas_adkey** 파라미터에 대한 고유한 값을 생성합니다.

**vegas_adkey=**y0ONEqr0n-7774-8435-5859-AqOmYSkZfOHeZrBJdeMsbYc1eFM1tM8fAlp-921d9cbe2ed65c3b18dd43c4dda2ebe6

 

결국 도착한  landing URL에는 **vegas_adkey** 와 **값**이 존재합니다.

예시) edsdf.pe.kr/page_07/index02.asp?sender=ad02&**vegas_adkey=y0ONEqr0n-7774-8435-5859-AqOmYSkZfOHeZrBJdeMsbYc1eFM1tM8fAlp-921d9cbe2ed65c3b18dd43c4dda2ebe6**

![image](https://user-images.githubusercontent.com/87693595/126424590-e02e7506-2d7f-4f8b-b83a-4c392490d3bd.png)


 

[위 이미지의 최상단 빨간 박스] 
최초에 landing 한 페이지에는 vegas_adkey={adkey}가 전달됩니다.<br><br>


<br><br><br><br>
 
 
 
 
 
### 3. Cookie에 vegas_param 존재
![image](https://user-images.githubusercontent.com/87693595/126424676-27ca0af0-f54f-41ac-9d72-5b2893754d91.png)

A 스크립트의 **tracker.firstLanding()이 실행되면** <br>
url에 있는 vegas_adkey={adkey}을 값을 쿠키에 **vegas_param**에 값을 저장하고 있습니다.

이 **vegas_param** 쿠키 값이 B 스크립트가 있는 페이지에 같이 공유를 하면서 어떤 사람이 전환(회원가입)을 했는지 구분하는 값입니다. 

따라서 A 스크립트에는 <br>
1) url에 있는 **vegas_adkey={adkey} 의 존재** <br>
2) **쿠키에 vegas_param 존재가** 필수적으로 필요합니다.

 

이 두가지가 생성되야 A 스크립트가 제대로 작동하는 것으로 애드맥스는 판단하고 있습니다.

이 조건이 선행되어야 B 스크립트에서 쿠키에 vegas_param 의 값을 가지고 전환을 실행시킵니다.
<br><br><br><br>

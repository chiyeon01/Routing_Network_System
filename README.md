# 🛜 Routing Network System

<br/><br/><br/>

## 개요
***Routing Network System***은 기업들의 Agent가 자신만의 페르소나, 정보를 기반으로 서로의 네트워크망을 구성하도록 하는 시스템입니다.<br/>
이는 기존 아날로그 방식 소통의 시간적, 공간적 제약을 뚫어내는 소통 방식으로, 상호간의 네트워크 망을 넓히는 것에 기여합니다.<br/>

📌 이 프로젝트는 [Track1: AI Agent 개발 <K intelligence 해커톤 2025>](https://dacon.io/competitions/official/236553/overview/description)의 규칙을 준수했으며, 관련 모델을 활용해 서비스를 만들었습니다.

<br/><br/><br/>

## 문제 상황
과거부터 현재까지 기업들간의 소통은 중요한 과정이었습니다.<br/>
관련되지 않은 타 협력 업체의 부서에 연락해야 하거나 부재중인 경우, 정보를 직접 찾아보고 기다렸다가 내용을 전달해 줘야 하는 시간이 소요된다고 판단했습니다.<br/>
특히나 소통의 속도와 정확성, 신뢰는 중요한 문제로 거론되었고, 기업의 성과에 직접적으로 영향을 미치는 요인입니다.<br/>
저는 이런 개선사항과 문제를 인식하고, 이를 개선하고자 ***Routing Network System***을 만들었습니다😊.<br/>

<br/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/2c1183b1-d4ab-477d-bc68-c9410538783f" width="680" height="196" alt="image">
</p>
  
<br/><br/><br/>

## 해결 방법
저는 이런 문제 상황을 인식하고, 해결하기 위해 믿:음 2.0 Mini모델을 사용하여 기업 간의 소통을 해결하고자 했습니다.<br/>
다만, 이 서비스는 정확한 정보를 요구하고 잘못된 정보를 사용하지 않도록 하는 것에 초점을 맞추었습니다.<br/>
LLM 기술이 발전하며, ***환각 현상***을 해결하기 위한 많은 방법론들이 존재했고, 저는 ***Functional Calling*** 기술을 활용했습니다.<br/>

각 회사의 데이터베이스와 페르소나를 넣으면 회사마다 고유한 Agent가 생기고, 이를 활용해 다른 회사의 Agent와 대화할 수 있습니다.<br/>

<br/>

<p align="center">
  <img width="421" height="348" alt="image" src="https://github.com/user-attachments/assets/b51205dc-1698-4e65-974a-78d7c71ae5a5">
</p>

<br/>

이 문제를 해결함과 동시에 보다 나은 네트워크를 위해서 다음과 같은 문제 상황을 가정하고 해결책을 도출했습니다.

<br/>

* ### 각 Agent가 상대 Agent가 가지고 있는 회사 정보를 가져온다면 보안상의 문제가 발생하지 않을까?
  **-> 각 회사는 자체적인 LLM을 가져야 하고, 각 회사의 데이터베이스를 가져야 한다. 그리고 데이터베이스에는 협업하는 회사와 공유할 수 있는 정보만 넣는 것을 원칙으로 한다.**
* ### Agent가 환각 현상을 보인다면, 오히려 문제가 가중되지 않을까?
  **-> 환각 현상을 방지하기 위해 개발자가 구성한 ***Functional Calling***을 도입하여 즉각적으로 데이터를 가져온다.**

<br/><br/><br/>

## 프로토콜
프로토콜의 기본적인 모습은 Streamlit을 이용하여 구축했습니다.<br/>
아래 사진은 프로토콜이 작동하는 과정을 나타냅니다. 기본적으로 두 개 이상의 Agent를 생성해야 원하는 대로 작동합니다. 각 Agent는 자신이 속해있는 기업의 페르소나와 정보를 입력받습니다. 정보는 PDF 문서로 입력 받습니다.<br/>
입력받은 PDF는 후에 Agent간의 상호 작용에서 ***Functional Calling***을 이용해 참조함으로써 답변의 신뢰성을 높이게 됩니다.

<br/>

<p align="center">
  <img width="870" height="330" alt="image" src="https://github.com/user-attachments/assets/e864e7d7-3152-40ad-97fa-073a2205b477" />
</p>

<br/>

각 Agent는 타 Agent에게 정보를 요청하고 받는 것을 넘어서 상대가 도착했을 시 알려달라고 요청할 수 있습니다.<br/>
실제 알람 기능까지 넣지 않았지만, 작동 메커니즘은 동일합니다.

<br/><br/><br/>

## 기대효과
***Routing Network System***은 간단한 프로토콜로 시작했지만, 틀을 깨고 새로운 네트워크 장을 개척하는 축이 될 것입니다.<br/>
앞으로 STT와 TTS 방식을 활용하여 보다 빠른 네트워크를 구축할 수 있습니다.

<br/>

다만, 예상할 수 있듯이 ***Routing Network System***의 치명적인 단점은 회사 내부 데이터가 "자체적으로" 존재해야 하며, 회사의 "자체적인" 모델이 존재해야 합니다.<br/>
반대로, 위 조건을 충족한다면 회사의 규모가 커지고 수가 많더라도 안정적(보안적)으로 시스템 구축이 가능해질 것입니다.

<br/>

이는 기존 고객 챗봇 상담 서비스에서 발전하여 회사 간 네트워크에서도 이용할 수 있음을 암시합니다.
여기서는 “회사의 LLM”이라고 칭했지만, 각 회사 부서끼리 Agent가 소통하도록 확장할 수 있습니다.
이를 통해, 정보가 더 정확해지며 순환이 빨라질 것입니다.

<br/><br/><br/>

## 서비스 실행 가이드라인

터미널에서 다음 명령어를 실행하여 간단하게 실험해볼 수 있습니다!

```python
streamlit run main.py
```

이후, 다음과 같은 문구가 터미널에 나타나면 성공적으로 작업을 마친 것입니다.

<br/>

<img width="1452" height="249" alt="image" src="https://github.com/user-attachments/assets/d0fbf0e7-3fc1-4e4d-9bcc-287fd70ec23a" />

<br/><br/><br/>

## 📽️ Project Slides
<details>
  <summary>여기를 클릭하여 슬라이드를 확인하세요!</summary>
  <p align="center">
    <a href="https://www.canva.com/design/DAGxmiVe42Y/EvFHh2YEhw-YAZhYEEYcdg/edit?utm_content=DAGxmiVe42Y&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton">🔗 PPT 원본 링크</a>
  </p>
  <br />
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/1.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/2.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/3.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/4.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/5.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/6.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/7.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/8.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/9.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/10.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/11.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/12.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/13.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/14.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/15.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/16.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/17.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/18.jpg" width="100%">
  <img src="https://github.com/chiyeon01/Routing_Network_System/blob/5978c7118a01974a21cf9593127bdd53b9908b8e/ppt_Images/19.jpg" width="100%">
  <br />
</details>

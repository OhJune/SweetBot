# SweetBot

### 🤟 애인에게 해줄 답장이 생각 안 날때 , 위로의 말을 듣고 싶을 때 Sweetbot이 도와드립니다.
---

>  팀구성 : 3명

Open AI의 gptAPI를 이용하여 이용자의 MBTI에 맞는 애인 챗봇 서비스를 웹으로 구현 및 배포 




### 역할

* MBTI별로 대답을 해줘야 하기 때문에 프롬프트를 최대한 사용자가 원하는 대답을 할 수 있게 유도
* AWS에서 git과 docker-compose를 사용해 배포
* 사용자들의 피드내용를 DB에서 집계하여 불용어 처리 후 워드클라우드 시각화

### ✏️사용 stack

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">  <img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/postgresql-4169E1?style=for-the-badge&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white">

---

📝 input으로 들어온 request를 OpenAI API로 호출하여 챗봇의 응답을 생성

![image](https://github.com/OhJune/SweetBot/assets/124857930/c2e92eb9-c6b4-4e84-a36b-bb65ff625842)

📝 session_messages는 각 발화(role)와 내용(content), 그리고 발화의 고유 id를 담은 리스트이고

이후의 내용을 추출하여 이를 이용해 새로운 발화 정보를 생성한 뒤 request.session에 추가하여 대화가 이어지도록 만듬

![image](https://github.com/OhJune/SweetBot/assets/124857930/c25e8e93-e4a7-41bb-a4fc-121df146d94b)

📝 사용자에게 효과적인 대답을 해주기 위해 프롬프트 설정

![image](https://github.com/OhJune/SweetBot/assets/124857930/dc7c889f-9fc1-430d-b611-d193b273dc81)


---

📝WordCloud활용

DB에서 사용자들이 게시한 text내용을 집계하여 워드클라우드로 보여주는 기능을 구현

실시간으로 웹에서 워드클라우드.png를 저장하고 바로 보여줄 수 있게 사용하려 하였지만 자연어 처리기의 속도가 느려서 페이지 로드에 문제가 생김

문제를 해결 하기 위해 DB의 text내용을 가져와서 전처리 과정 후에 워드클라우드로 만들고 사진으로 저장하는 파이썬 파일을 만들어 해당 페이지에서 저장된 사진만 crontab으로 주기적으로 로드

😮‍💨원래 과정

DB와 연결 -> 파이썬함수(해당 사용자들의 text 조회하는 쿼리문 실행) -> 전처리 실행 -> 워드클라우드 -> 페이지 로드

😄수정 후 과정

DB와 연결 -> 파이썬함수(해당 사용자들의 text 조회하는 쿼리문 실행) -> 전처리 실행 -> Crontab으로 워드클라우드.jpg 저장 -> 페이지에서 사진 로드 

https://oh-um.tistory.com/26









# SweetBot

Open AI의 gptAPI를 이용하여 이용자의 MBTI에 맞는 애인 챗봇 서비스를 웹으로 구현 및 배포 

* MBTI별로 대답을 해줘야 하기 때문에 프롬프트를 최대한 사용자가 원하는 대답을 할 수 있게 유도
* DB 서버는 RDS 혹은 별도의 인스턴스로 따로 분리하지 않고, 1개 인스턴스에서 docker-compose를 통해 배포
* 사용자들의 피드내용를 집계하여 불용어 처리 후 워드클라우드 시각화

✏️사용 stack

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">  <img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/postgresql-4169E1?style=for-the-badge&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white">




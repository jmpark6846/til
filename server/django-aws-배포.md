# django 프로젝트 AWS 배포 할일 리스트
django 프로젝트를 AWS에 배포할때 하는 일들을 쭉 적어봤다. 아주 훌륭한 튜토리얼이 있어서 비교적 수월하게 따라할 수 있었다. 배포 성공 후 전체적인 큰 흐름을 한번 짚어보고 싶어서 리스트로 간단하게 적어보았다. 

### 기본 
1. AWS 계정 생성 및 로그인
2. 리젼 '서울'로 변경
3. IAM 에서 새 유저 추가
    1. 권한 정책 설정
4. EC2 키페어 생성
5. EC2 인스턴스 생성
6. ssh를 사용하여 EC2 접속 확인
7. AWS -> 보안그룹 인바운드 규칙 추가(포트 추가)

### 서버 환경 설정
1. locale 설정
2. 패키지 정보 업데이트
3. python3-pip 설치
4. pyenv를 활용한 python 설치
    1. pyenv가 사용하는 패키지들 설치.

### django, db
1. settings.py -> allowed_host에 ec2 인스턴스 퍼블릭 dns 추가
2. django project를 scp를 사용해서 서버에 업로드
3. 서버에 가상환경 설정, 디펜던시 설치
4. mysql-server 설치
5. mysqlclient 설치, mysql-config 등 필요한 패키지 설치
6. mysql shell에서 project 용 user 추가
7. 새 user에 권한 설정
8. db table 생성
9. django mysql cnf 파일에 새 user 정보 입력
10. db migrate
11. python manage.py runserver로 실행
12. 브라우저에서 퍼블릭DNS:8080으로 실행 확인


참고  
https://nachwon.github.io/django-deploy-1-aws/
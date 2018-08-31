# charset utf-8과 MySQL, django 
charset은 자료형(자료구조)으로 utf-8은 텍스트를 저장하기 위한 자료형이다.  
utf-8은 1~4 바이트를 저장할 수 있는 구조이다. (가변 바이트)

MySQL도 utf-8을 지원한다. 하지만 mysql은 utf-8을 3바이트로 설계했다.  
그 이유는, 모든 언어를 살펴본 결과 3바이트가 조금 안됬기 때문에 용량, 속도 등을 이유로 3바이트 가변 자료형(1~3바이트)으로 설계한 것이다.  

그런데 이모지 같은 비교적 최신 문자들은 4바이트이다. MySQL을 사용하는 환경에서 이모지를 저장하면 오류를 발생시키는 것이다.  
따라서 MySQL에서 2010년에 utf8mb4라는 charset을 만들어 4바이트까지 저장할 수 있도록 설계를 변경하였다.

django에서는 MySQL 연동할때 utf-8을 쓸 것은 권하고 있다.  2.1버전 공식 문서의 DATABASES에 보면 utf8mb4 대신 utf8을 명시해놓았다.    
스택오버플로우에 관련 키워드로 검색해보면 해외의 개발자들도 DB 전체를 utf8mb4로 설정하는 경우 문제가 발생할 수 있다는 견해가 많은 것 같다. (단순히 업그레이드를 부담스러워하는 걸지도)

따라서 전체를 utf8mb4로 설정하는 것 보다는, 필요한 필드만 부분적으로 설정하는 것이 가장 추천되는 방법인 것 같다.

---

여담으로 django database를 utf-8로 설정하는 경우 꼭 테스트 db도 utf-8로 설정하자.  
test db의 charset은 latin 이라 문제가 발생할 수 도 있다.

### 참고
http://sshkim.tistory.com/128  
https://stackoverflow.com/questions/12894658/django-test-database-is-not-created-with-utf8

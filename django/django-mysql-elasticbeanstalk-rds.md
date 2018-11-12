# django-mysql-elasticbeanstalk-rds

django에서 mysql을 사용할때 database의 기본 charset으로 utf8mb4를 사용하는 것이 더 좋다.
utf8mb4는 4byte utf8을 의미한다. 원래 utf8은 4byte 를 지원하나 실용성이라는 이유로 3byte를 사용해왔다. (3byte만 되도 모든 문자를 다 표현할 수 있었음)
하지만 이모지 처럼 4byte 를 필요로하는 필드 들이 생기면서 4byte utf8을 지원하는 문자셋인 utf8mb4를 만들었다.

특히 elastic beanstalk과 rds를 사용할 경우 utf8, utf8mb4로 데이터베이스(혹은 특정 테이블)의 기본 문자셋을 지정하지 않는다면 문자셋이 달라 `Incorrect string value` 에러가 날 가능성이 높다.
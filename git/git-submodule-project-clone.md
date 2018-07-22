# git submodule 을 사용하는 프로젝트 clone하기

git submodule을 사용하는 프로젝트를 clone하면 submodule 폴더가 비어있다.  
이럴땐 init과 update를 차례로 실행해준다.

    git submodule init
    git submodule update 

해당 서브모듈의 코드를 다운받는 것을 확인하고 정상 실행한다.

참고 
https://git-scm.com/book/ko/v1/Git-%EB%8F%84%EA%B5%AC-%EC%84%9C%EB%B8%8C%EB%AA%A8%EB%93%88#%EC%84%9C%EB%B8%8C%EB%AA%A8%EB%93%88%EC%9D%B4-%EC%9E%88%EB%8A%94-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-Clone%ED%95%98%EA%B8%B0
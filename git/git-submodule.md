# git submodule

자주 사용할 것 같은 ui 컴포넌트를 저장소로 따로 만들었다.
https://github.com/jmpark6846/ui-components

다른 프로젝트 내에서 이 저장소를 받아 사용하려면 git submodule을 사용할 수 있다.

git submodule은 한 프로젝트 안에서 다른 프로젝트들을 사용할 수 있게 해준다.

    git submodule add <url> <path>

서브모듈에서 수정사항이 생기면 서브모듈 경로로 이동해서 부모 프로젝트와는 별개로 커밋, 푸시, 풀 한다. 

참고
http://ohgyun.com/711
https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-%EC%84%9C%EB%B8%8C%EB%AA%A8%EB%93%88
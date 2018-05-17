## React PropTypes & isRequired

**컴포넌트의 props의 경우 부모 혹은 외부에서 받는 데이터들이기 때문에 컴포넌트에서 자체적으로 type checking이 필요하다.**
calendar-note 프로젝트 내에서 컴포넌트들의 props에 대한 type checking 을 위해 관련 내용을 찾아보았다.


처음에는 Flow를 도입하기 위해 관련 코드를 작성했으나 여러가지 문제점이 있었다.

- node_modules의 라이브러리들을 type check하는 경우 발생
- 컴포넌트 contructor 내에서 메소드를 bind하는 코드를 flow가 지적(complain)

등을 포함해 여러 자잘한 에러들이 보였다.


찾아보니 문제에 대해 해결 방법이 없는 것은 아니었다.

하지만 문제라고 납득하기 어려운 부분을 문제라고 지적한 부분이 여럿 있었고 더욱이 공식 문서에서 여기에 대해 설명해놓지 않았다.

여러 고민 끝에 좀 더 사용하기 간단한 PropTypes를 사용하였다.



PropTypes를 사용하다보면 isRequired를 언제 사용해야하는 지 애매했다.
사실상 사용하지 않는 데이터는 굳이 prop으로 넣지 않기 때문에 모두 필요하다고 생각되기 때문이다. 
그러다 한 Reac 공부자료에서 관련 내용을 발견했다.

**만약 해당 프로퍼티에 의존하는 코드가 있다면 isRequired, 출력만하거나 변경될지도 모르는 프로퍼티들은 isRequired를 적지 않는다.**



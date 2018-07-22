# jest react-redux connect
react-redux의 connect를 이용해 컴포넌트를 HOC로 만들어 사용하면 export default connect()() 이렇게 보통 사용한다.  
하지만 이렇게 되면 export 되는 대상이 컴포넌트 자체가 아닌 connect()의 리턴값이다.  
따라서 jest로 테스트를 하기 위해선 컴포넌트와 connect(컴포넌트) 두 개를 모두 export 하면 된다. 그럼 순수한 컴포넌트를 import하여 테스트 할 수 있다.

    import { connect } from 'react-redux'
​
    // Use named export for unconnected component (for tests)
    export class App extends Component { /* ... */ }
​
    // Use default export for the connected component (for app)
    export default connect(mapStateToProps)(App)

참고  
https://redux.js.org/recipes/writing-tests#connected-components
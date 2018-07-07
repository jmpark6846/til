# jsx autofocus react focus
jsx에서 element에 포커스를 주고 싶을때 autoFocus attribute를 추가하면 된다.  

    <input autoFocus />

이건 jsx만의 문법은 아니다. html 태그에서 사용되던 autofocus를 jsx로 구현한 것이다.  
관련 스펙에 따라 html5에서 autofocus를 지원하는 태그들은 autoFocus도 사용 가능하다.  
하지만 div는 autofocus를 지원하는 태그가 아니므로 contenteditable이 적용된다고 해도 autofocus 또는 autoFocus를 사용할 수 없다.  
react에서 contenteditable에 포커스를 주려면 ref를 이용해 dom node에 접근한뒤 focus() 하는 방법을 사용해야한다.

    // contructor
    this.ref = React.createRef()
    
    // render
    <input ref={this.ref} />

    // focus like this..
    this.ref.current.focus()


참고  
https://reactjs.org/docs/accessibility.html#programmatically-managing-focus
https://github.com/facebook/react/issues/6868#issuecomment-221762910
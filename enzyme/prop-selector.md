# Enzyme Prop Selector
Enzyme으로 테스팅할때, 렌더링된 컴포넌트 안에서 특정 element를 찾을때 enzyme selector를 사용한다.  
HTML 태그 셀렉터, CSS 셀렉터 뿐만아니라 Prop selector라는 걸 지원하는데, attribute selector처럼 react의 prop을 이용한 selector이다.

    // <ContentEditable />
    <div contentEditable={true}></div>

    // test
    const component = shallow(<ContentEditable />)
    expect(component.find('[contentEditable=true]').length).toBe(1)

참고  
https://github.com/airbnb/enzyme/blob/master/docs/api/selector.md#2-prop-selector
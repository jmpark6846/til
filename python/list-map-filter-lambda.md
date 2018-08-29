# python list(), map(), filter(), lambda

자바스크립트에서 편했던 기능 중 하나가 map, reduce, filter였다.  
파이썬에서도 비슷한 기능을 사용할 일이 있어서 찾아보니 동명의 함수가 있었다.  
  
list(이터러블)는 iterable을 받아서 리스트로 변환  
map(함수, 이터러블)은 function과 iterable을 받아서 python2에서는 리스트, python3에서는 map 객체로 변환  
filter(함수, 리스트)는 리스트의 값중 함수가 참을 반환하는 값을 리턴. 역시나 python2에서는 리스트, python3에서는 filter객체(아마도?)  

여기서 요긴하게 쓰이는 것이 lambda이다.  
람다는 간단하게 인라인 함수를 표현할 수 있는 문법이다. 자바스크립트에서는 애로우 펑션과 비슷하게 사용할 수 있을 것 같다.  
    
    lambda 인자: 표현식

    // 각 category 쿼리셋의 element 중에서 name과 id를 dictionary 형태로 반환
    category = list(map((lambda c: { "name": c.name, "id": c.id }), Category.objects.all()))

### 참고 
- https://wikidocs.net/64  
- https://docs.python.org/3/library/functions.html
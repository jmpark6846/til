# django escape
django는 템플릿에서 변수를 렌더링 할 경우 기본적으로 escape 해서 렌더링 한다. (autoescape)  
escape란 html 태그 같은 안전하지 않은 문자들을 안전한 문자로 변환하는 것을 말한다. \<script>태그 같은 내용은 사용자 입력 부분에 삽입되어 악용될 수 있기 때문이다.
변환 규칙은 아래와 같다.

- < 은 \&lt;로 변환 
- \> 은 \&gt;로 변환
- ' (작은 따옴표)는 \&#39;로 변환
- " (큰 따옴표)는 \&quot;로 변환
- &는 \&amp;로 변환.


참고
- https://stackoverflow.com/questions/11306669/django-template-escaping
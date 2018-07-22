# white-space : pre-line
react에서  jsx textarea를 통해 폼의 입력값을 화면에 렌더링할때, 값에는 enter값 (new line)이 있지만 화면에 출력한다면 new line 없이 한 줄로 나타난다.

이때 css white-space 속성을 pre-line으로 변경한다.

pre-line은 연속된 빈칸은 붙고, 각 문장이 new line으로 분리되어 줄이 나뉜다.

참고
https://stackoverflow.com/questions/36260013/react-display-line-breaks-from-saved-textarea
# em, rem, px 차이

em과 rem은 적용된 font-size에 따라 px값으로 변환된다.  
`
font-size:16px;  
padding: 1.5em; // 16 * 1.5 = 24px  
`

em과 rem은 기준이 되는 DOM element에 따라 다르다.  
em은 해당 element에, rem은 html 태그에 적용된 font-size에 따라 px값으로 변환된다.  
디바이스에 따라 폰트 크기가 변경되어야할 경우 거기에 맞게 모든 값들이 조정될 수 있도록 rem을 쓰는 것이 좋다.

### 참고: 
- https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984 
	
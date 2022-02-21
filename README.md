# Nomadcoders Kokoatalk Clone

html,css수업_kokoaTalk 클론코딩2주 챌린지

https://nomadcoders.co <br>
https://nomadcoders.slack.com/archives/CCHLQEXP1

# < display >
2D 레이아웃 범위내에서 HTML elements의 위치를 제어한다.
- inline   
- block   
- inline-block   
- flex   
inline-block은 반응형디자인을 지원하지 않기 때문에 브라우저 창크기의 변화에 대응하지 못하는   문제점을 해결하기 위한 해결책으로 등장했다.   
부모태그를 flexbox로 만들어 해당 box범위 안의 자식태그들의 위치를 제어할 수 있다.   
  - flex-direction : row(기본값), column , column-reverse, row-reverse
  - flex-wrap : wrap, nowrap, wrap-reverse
  - justify-content(flexbox 주축선정렬) : space-evenly,  space-between
  - align-itemps(flexbox 교차축정렬) : flex-statr,  center,  flex-end,  stretch
        
# < position >
2D 레이아웃 위(over)의 다른층의 레이어에 위치하게 할 HTML elements의 위치를 제어한다.   
ex.스크롤을 이동해도 화면상에 항상 같은위치에 존재하는 맨위로가기 버튼  

- fixed   
화면기준 어느 위치에 존재하게 할것인지는 top,bottom,right,left 속성으로 위치값 추가.   
보통 아래 레이어에 위치한 contents를 가리지 않기 위해 opacity 값을 넣어준다.   
- static (기본값)   
elements가 처음 위치한 자리
- relative   
elements가 처음위치한 자리(static)기준으로 위치를 조정한다.   
top,top,bottom,right,left 속성으로 위치값 변경  
- absolute   
가장 가까운 elements중 position을 relatve로 설정한 태그를 부모태그로 두고 그 기준으로 위치를   조정한다. relative로 설정된 태그가 없는 경우 최상위 태그인 body를 기준으로 한다.  

# < CSS selector >
>reference : [MDN_pseudo selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

- **tag name**
- **#id name**
- **.class name**
- **pseudo selectors**

좀더 세부적으로 html elements를 선택하는 기능 
무분별한 class, id추가 없이 html elements를 선택할 수 있다.

```css
selector : first-child{
}
selector : nth-child(2){
}
selector : nth-child(3){
}
selector : last-child{
}
-----------------------------------------------
selector : nth-child(even){
}
selector : nth-child(odd){
}
------------------------------------------------
selector : nth-child(2n){
}
selector : nth-child(2n+1){
}
selector : nth-child(3n){
}
selector : nth-child(수열){
}
--------------------------------------------------
body h1{     body안의 h1을 찾음
}
div p h1{    div안의 p안의 h1을 찾음
}
div > h1{    div안에 있는 h1을 찾음
}
div + h1{    div와 형제관계인 바로 다음에 위치한 h1을 찾음
}
div ~ h1{    div의 형제관계이고 바로 다음에 있지않은 h1을 찾음
}
```

## attribute selector

>reference : [MDN_attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
좀더 세부적으로 html elements를 선택하는 기능 
무분별한 class, id추가 없이 html elements를 선택할 수 있다. 

```css
html attribute 사용 
input: required{     input태그 중 required속성이 추가된 태그를 찾음
}
input[placehorder="username"]{   input태그 중 placehorder가 username인 태그찾음
}
input[placehorder~="name"]{  input태그 중 placehorder에 name이 포함된 모든태그찾음
}
a[href$=".org"]{    a태그 중 연결된 url이 .org로 끝나는 모든태그를 찾음
}

```

## Pseudo-classes : state

html elements의 각각 state(상태)마다 다르게 스타일을 적용 할 수 있다.

- active
버튼을 예시로 하면 클릭되었을때의 상태
- hover
버튼을 예시로 하면 마우스르르 올려놓은 상태
- focused
버튼을 예시로 하면 “키보드”로 해당 버튼을 선택한 상태
보통 input태그들 중 현재 커서가 위치한 곳을 보여줄때 사용됨
- visited
링크태그만의 상태로서 방문한링크여부를 구분해준다.
- focusedwithin
focused된 상태인 elements가 들어있는 부모태그의 스타일을 변경가능하다.

```css
<-- 특정태그의 state를 다른 태그와 연계하여 사용할 수도 있다.-->

form:hover input{      form이 hover상태일때 form안의 input태그의 스타일 변경
}

form:hover input:foucused{    태그 두개의 상태를 동시 사용 가능하다
}
```

## 추가 특수한 pseudo-element
>reference : [MDN_::placehoder](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder)
>reference : [MDN_::selection](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)

```css
input::placehorder{     placehorder의 스타일 변경
}
taxtarea::placehorder{
}

p::selection{    드래그했을때 형광펜으로 칠한 효과
}
```

# transition
transition의 사전적 의미 : 다른상태로의 이행, 과도   
변경되는 값들의 변화과정에 스타일을 줄 수 있다.   
스타일의 종류   
- linear 
- ease
- ease-in
- ease-out
- ease-in-out
- 내 임의로 스타일적용 cubic-bezier(0.6,  0,  0.735,  0.045);
```css
버튼을 클릭했을때 배경색이 흰색에서 빨강으로 변화하는 과정을 
10초 동안에 걸쳐서 

button{
	background-color : white;
	transition : background-color 10s ease-in-out;   
}
buttom:hover{
	background-color : red;
}

button{
	background-color : white;
	border-radius : 1px;
	color : yellow;
	transition : background-color 10s ease-in-out,  //변화 중 2개만 선택적으로 적용
							 border-radius 5s ease-out;  
}
buttom:hover{
	background-color : red;
	border-radius : 10px;
	color : blue;
}

a{
	background-color : white;
	color : green;
	transition : all 10s ease-in-out;      //변화가 있는 모든것에 transition적용  
}
a:hover{
	background-color : red;
	color : blue;
	border-radius : 20px;
}
```

# transformation
- translateX()   
- scale()   
- rotate()   
- matrix()   
transform은 다른 box elements,이미지에 영향을 주지 않는다.   
3D차원의 변형이기때문에 2D 레이아웃상의 요소들에 영향을 주지않는다.   
transition과 연계하여 주로 사용된다.   

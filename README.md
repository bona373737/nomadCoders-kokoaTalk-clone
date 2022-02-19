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
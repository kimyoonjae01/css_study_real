# css (cascading style sheet)
## css 작성 전 준비사항
* html 문서준비 (태그작성 완료상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css파일 배치
* ex) index.html , index,css
## css 외부스타일시트와 내부스타일 시트
* name.css 외부 파일로 분리해서 html에 link로 연결하는 외부 스타일 시트
* html 파일 내에서 head태그 안에 style 태그로 구분해서 작성하는 **내부 스타일 시트**
* 외부스타일시트 장단점 :
- 장점 : 1개의 css파일로 여러개의 html을 관리할 수 있다
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다.
* 내부스타일시트 장단점 : 
- 장점 : html 파일 내에 작성하여 태그와 한꺼번에 보기 편하다
- 단점 2개 이상의 html 파일을 동시에 디자인관리하는것이 불가능하다.
## css 선택자
1. 태그선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스 선택자 : `<h1 class="a"><h1>` -> `.a{속성:값;}`
3. 아이디 선택자 : `<h1 id="b"></h1>` -> `#b{속성:값;}`
4. 자손 선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식 선택자 `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## css디자인하기
* css 작성 전 html이 미리 디자인 되어있으면 안된다.
* **html을 디자인초기화하는 작업이 css 디자인 전 반드시 선행되어야한다.!!**
* 초기화 css `reset.css` 공통파일 **(날짜나 프로젝트명 표기 금지)**
# css 글자 표현 속성
## font-family
* 로컬 글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야한다.
* 글꼴이름에 한글이나 공백이 있으면 "" 필수로 붙여야한다.
## 폰트 사이즈
* 웹 글꼴 평균 16px 
* 사용단위 px, %, em,rem
* 절대값 : px, 상대값 : %, em, rem(권장)
# 선택자 우선 순위
* #아이디(3점) > .클래스(2점) > 태그(1점) 점수가 높은 쪽이 우선순위를 
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {8}` 3+2+2+1
* `#box #a .b p {9}` 3+3+2+1
* `#wrap #box .a {8}` 3+3+2
* `#wrap .a .b p {8}` 3+2+2+1
2. 다음 중 우선 순위가 가장 높고 낮은 선택지는?
* `#box #wrap .p a {}`
* `.p .box p a {}`
* `#box #wrap p a {}`
* `#a .p pox wrap {}`
## color
* 영문명 직접 입력 ex) 테스트용 주로 밝은 색을 사용한다.
* aqua, lime, yellow, coral, ***
* 헥사코드 입력
* 최소값 0 ~ 최대값 F RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을수록 밝아진다.
* #Hex #000000 -> #000, #ff00cc -> #F0c
* RGBA(RED,GREEN,BLUE, ALPHA) *최대색상255
## 글꼴태그
* `padding` 태그와 태그간의 거리 / 속성 top or bottom
## box Css
### display
* `block, inilnem inilne-block`
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식 (그 외 크기인식 불가능)
* `inline-block` : 내용만큼 크기 인식 (크기 추가설정가능)
### box-sizing
* `box-sizing:border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성 
* 속성 미적용 시 : w100+h100+padding`top20 = 100x120
* 속성 적용 시 : w100+h100+padding`top20 = 100x100
### wudth, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
## form 요소와 속성
### `<form action="#" method=""></form>`
* action : 폼 내부에 데이터를 보내는 목적지 url을 지정한다.
* method : 폼을 서버로 전송하는 http 방식을 지정. POST와 GET이 있다.
* fieldset, legend : ex) fieldset : form 내부에서 관계된 요소들끼리 묶어주며 그룹화 하는데 그룹화 된 주위에 얇은 테두리를 이용하여 박스를 그린다. ex)fieldset에 제목을 달아주는 역할을 한다. 이러한 폼 요소들의 그룹화는 스크립트에서 접근 시 보다 용이하게 만들어주며 사용자의 접근성 또한 높여준다.
### `<input type="">`
* type : 속성 값을 입력할 수 있음 ex) `input type="name , text , time , search, url"` 등
* name : 어떤 것에 쓰이는지  알 수 있음 ex) `input type="text" name="user_name"` 등
* readinly : 읽기 전용, 웹사이트 방문자가 바꿀 수 없다
* autofocus, autocomplete : ex) 구글 메인이미지 접속시 마우스커서를 안눌러도 자동으로 검색폼 누를 수 있는 기능, ex) 그동안 썻던 검색기록을 볼 수 있는 기능
* value : 초기값 지정. ex) 번호 입력시 010자동으로 입력 되있는 값
* placeholder : 아이디나 비밀번호 적는 창에 "id를 입력해주세요" 라는 문구가 나와있지만 클릭하면 사라지는 기능
* value와 placeholder의 차이점 : value는 초기값을 지정해주는 것, placeholder 는 누르면 사라짐
* maxlength : 쓸 수 있는 글자의 수를 지정해두는 것 ex) 비밀번호는 10자 이상 쓰면 안된다. > maxlength="10"
### `<textarea></textarea>`
* rows, cols : ex) rows="3" > 한번에 3줄이 보이게 함 , ex) cols="50" 한 줄에 50개의 글자가 보이게 함
* 사용용도 및 주의사항 : 약관내용으로 자주 사용하지 않음, 고객 리뷰같은 페이지에 쓰는 듯?
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접 입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터구분용) , 선택양식(데이터구분 (개별데이터X,그룹데이터구분용)) / value="userMailAgreeY" , "userMailAgreeN" 으로 벨류값 따로 지정하면 됌
* `value` : 입력양식(초기값), 선택양식 (개별데이터구분용)
## float 
* float 속성을 넣으면 부모의 밖으로 자식이 나가버림
### float 해결법
* 자식에 float 적용함으로써 생기는 부모인식 오류 해결 
* 해결법 1. 크기를 직접 적용한다 
* `.box {height: 100px;} `
* 해결법 2. 자식 포함 크기 재인식 속성 
* `overflow:hidden;`
* 해결법 3.가상요소 생성 
* `.box::after {clear: both; content:"a"; display: block;}`
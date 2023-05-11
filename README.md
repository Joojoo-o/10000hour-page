# 10000hour-page html code

10000hours page project에서 사용된 code들 설명 모음

## script

script란?
HTML문서에 자바스크립트 코드를 삽입할 수 있는 코드
script의 위치는 body의 가장 마지막에 작성하여야 문서 처리 속도가 빨라진다.

**defer**
다만, 자바스크립트의 파일 크기가 크거나 네트워크 속도가 느린경우에는
defer속성을 활용하면 HTML과 자바스크립트가 동시에 처리가 되어 더욱 빠르게 처리가 가능하며,
script를 body마지막에 넣지 않아도 마지막에 들어간 효과가 있다.

_defer 활용법 예시)_

```
<script defer src=""></script>

```

**async**
async속성은 HTML과 자바스크립트를 동시에 내려받으며,
다운이 끝나자마자 자바를 실행한다.
따라서 자바스크립트가 어느 시점에 내려받아져 실행될지 알수없어 HTML보다 빠르거나 느리게 끝날 수도 있다.

_async 활용법 예시)_

```
<script async src=""></script>
```

**defer과 async의 구별 사용법**
defer은 자바스크립트 코드를 HTML문서에 나타나는 순서대로 실행을 해준다.
따라서 서로 연관이 있는 여러 개의 스크립트 파일을 순차적으로 실행해야하는 경우 안전하다.

async는 독립된 여러개의 자바스크립트 파일을 삽입하는 경우 유리하다.
하나의 자바스크립트 파일이 다른 파일에 의존하는 경우(defer을 사용할 경우) 오류가 발생할 위험이있다.

_defer과 async의 차이점 예시)_

```
연관있는 여러개 파일은 defer
<script defer src="./script-1.js"></script>
<script defer src="./script-2.js"></script>
<script defer src="./script-3.js"></script>

독립된 여러개의 파일은 async
<script async src="./google-ad.js"></script>
<script async src="./facebook-ad.js"></script>
<script async src="./naver-ad.js"></script>
```

**type**
script와 script type="text/javascript"는 동일한 문장이다.
text를 통해서 스크립트를 구현하겠다는 뜻이며,
웹표준은 type을 적어주는 것이 맞지만,
HTML5에서는 디폴트로 javascript를 지정해주기 때문에 안적어도 괜찮다.
하지만, 하위 호환성을 위해서는 적어주는 것이 좋다.

_src=파일의 경로, url_

참고 사이트 : https://www.daleseo.com/js-script-defer-async/

## section

section은 div처럼 문단을 나눌 때 사용한다.
보통 section은 제목을 포함하고는 한다. (제목= h1,h2...을 자식요소로 포함)
섹션은 주제별로 그룹화 된 콘텐프이다.
(콘텐츠가 독립적인 성향이 크다면 section대신 article요소를 사용하는 것이 좋다.)

- 단순 스타일링 : div 사용
- 문서 요약에 해당 구획이 논리적으로 나타날 때 : section 사용
  일반적으로 섹션(부문, 구역, 영역)을 나타내는 기능을 하며
  글등을 그룹으로 다루어주는 역할을 한다.

_section 활용법 예시)
_

```
<section>
    <h1>HTML의 역사</h1>
    <p>최초의 HTML은 1991년 말에 버너스리가
    처음으로 인터넷에서 문서를 "HTML 태그"(HTML tag)로 부르면서 시작되었다.</p>
</section>
```

**id와 class에 대해**

- id는 스타일을 지정할 때 한가지만 지정해서 쓰는 이름(표기방식:#이름)
  하나의 문서에 고유한 id하나만 사용가능

- class는 그룹으로 묶어서 스타일을 지정할 때 쓰는 이름 (표기방식:.이름)
  id와 class의 이름은 자유롭게 지으면 되지만 숫자로 시작해서는 안된다.

**id와 class의 네이밍**

- index : 첫페이지 / 홈페이지의 첫 페이지를 명칭
- wrap : 전체 영역 / 페이지를 감싸는 전체영역
- header : 머리글 영역
- contant : 본문 영역
- footer : 바닥글 영역
  ![](https://velog.velcdn.com/images/joojoo0/post/10273c68-8f6b-4a7b-84be-7739015dd922/image.png)
  _참고 사이트 / 이미지사용 : https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=pungwun&logNo=220213568142_

## input

input은 입력창이 생성되는 것이다.
input에는 여러 type이 있는데 text는 텍스트를 입력하는 창이 생성된다.
placeholder를 입력하면 입력창 안에 흐린 글씨로 안내 문구를 작성할 수 있다.

그 외의 타입으로는

- button : 버튼 생성
- color : 컬러 선택
- date : 날짜 선택
- range : 바 이동하여 선택
  등이 있다.

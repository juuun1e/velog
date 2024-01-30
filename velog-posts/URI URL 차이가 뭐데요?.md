<p>형씨, URI랑 URL의 차이가 뭐데요? ??
요즘 들어 기초적인 것에 대해 호기심이 마구마구 생기는 중인 듯.</p>
<p>한 눈에 보기 쉬운 벤다이어그램을 그려봤다.
전까지는 정확한 차이를 몰랐기에 혼용해왔던 것이 사실이고, 
URL보다 URI의 개념이 더 방대하다는 것도 새롭게 알게 되었다</p>
<p>구체적으로 어떠한 차이가 있는지 알아보자!<img alt="" src="https://velog.velcdn.com/images/juuunie/post/72d55e47-9e13-4ae1-8569-6770f47bb6d9/image.png" /></p>
<br />

<hr />
<br />

<h2 id="🤔uri-란">🤔URI 란?</h2>
<p>풀네임은 <code>Uniform Resource Identifier</code>, 해석하면 <code>통일 자원 식별자</code> 를 의미한다. <br />
단어 하나 하나 의미를 살펴보자요-</p>
<ul>
<li><p>Uniform 
: 축구팀을 유니폼으로 구분하는 것처럼 <strong>resource를 식별</strong>하기 위해 사용하는 방식이다.</p>
</li>
<li><p>Resource 
: 어우 리소스가 뭐야? 아주 대~단한 자료들이지,
왜인지 머리 속에 잘 안들어왔던 개념인데 단순하게 하자면</p>
</li>
<li><p><em>인터넷 상의 문서, 사진, 동영상 등의 자료*</em>들을 통틀어 말한다.</p>
</li>
<li><p>Identifier 
: 인터넷 상의 자료들을 <strong>구분하기 위해 부여하는 이름</strong>을 의미한다.<br />URI가 가장 큰 개념이고, 하위 개념으로 URL과 URN을 포함하고 있다</p>
<br />

</li>
</ul>
<blockquote>
<p>즉, URI는 인터넷 상의 문서/사진/동영상 등(<code>resource</code>)에 <br />접근할 수 있는 유일한(<code>Uniform</code>) 식별자(<code>Identifier</code>) 인 것이다.</p>
</blockquote>
<blockquote>
<p>주요 목적이 리소스를 찾고 이름이나 위치를 이용하여 다른 리소스와 구별하는 것!! </p>
</blockquote>
<br />
URI는 '김아무개' 라는 이름을 활용하여 식별할 수 있다.<br />
하지만 위치나 연락처와 같은 정보는 알 수 없는 상황이다.

<p>이러한 상세 정보를 제공해주는 것이 URL이 되겠다!</p>
<br />
<br />


<h2 id="🤔url-이란">🤔URL 이란?</h2>
<p>우리가 가장 흔히 알고 있는 URL의 풀네임은 <code>Uniform Resource Locator</code> ,
해석하면 <code>통합 자원 지시자</code> 를 의미한다.</p>
<p>_'우리 인터넷 상의 문서/사진/영상(=자원)의 위치를 어떻게 표시하는게 좋을까?' _
고민고민해서 표시 방법을 약속해둔 것이다. 
<br /></p>
<blockquote>
</blockquote>
<p>😎 : 벨로그 어디있어!!?<br />??? : 여기 &gt;&gt;&gt; <code>https://velog.io/</code> </p>
<p>하고 정확한 위치정보를 알려줄 수 있는 것이 URL이다.
우리가 어떤 경로로 접근하는지 알 수 있는 것도 URL 덕분이라고 할 수 있겠다.</p>
<br />

<h3 id="💨-url의-구조를-살펴보자">💨 url의 구조를 살펴보자</h3>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/6802bbfd-321a-43e9-bfc7-8c7e630523b0/image.png" /></p>
<ul>
<li><p>프로토콜(protocol), 스킴(Scheme) | 필수항목</p>
</li>
<li><p>Host name(domain name) | 필수항목</p>
</li>
<li><p>포트번호(:port) | 필수지만 보통 숨어있다. 
그 이유는 HTTP인 경우는 80, HTTPS인 경우는 443이 기본으로 설정되어 있기 때문이다. URL 상으로 보여지지 않는다면 프로토콜을 기준으로 통신하고 있다는 거다! </p>
</li>
<li><p>/path | 선택항목</p>
</li>
<li><p>?query | 선택항목</p>
<br />
➡ url에는 `프로토콜(스킴)`, `도메인`, `포트` 이 3가지가 꼭 있어야 한다. 
<br />
ex) ![](https://velog.velcdn.com/images/juuunie/post/bb25cf1f-b538-41f3-a9c2-7c7d0f98bdab/image.png)

</li>
</ul>
<p>보통 브라우저들이 프로토콜을 숨기고 보여준다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/257d9d09-029e-4ea4-ba3f-8d68465740ee/image.png" /></p>
<p>클릭하거나 복사해서 다른 곳에 붙여넣기를 하면 숨어있던 <code>https://</code>를 볼 수 있다.</p>
<br />
<br /><br />

<hr />
<br />

<h2 id="🧐-그래서ㅡ-무어가-다르냐고">🧐 그래서ㅡ 무어가 다르냐고?</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/97a7d63d-5cf0-49b6-bee1-99f5d08b2b98/image.png" /></p>
<p>A와 B 모두 index.html이라는 리소스를 향하고 있다.</p>
<p>➡ A는 <code>/index.html</code> 실제 위치를 정확하게 나타내는 주소이기에 URI이면서 URL이 된다.</p>
<p>➡ B의 주소 <code>/index</code>는 파일이 존재하지 않기에 URL은 될 수 없다.
정확한 위치를 모르기 때문이다. 하지만 서버측에서의 처리로 index.html까지 식별하여 도달하기에 URI는 맞다고 할 수 있다.</p>
<br />

<h3 id="💨만약-indexhtml-파일-위치가-if폴더-아래로-변경됐다면">💨만약 index.html 파일 위치가 &gt;if폴더&lt; 아래로 변경됐다면?</h3>
<p>➡ A는 <code>/if/index.html</code> 과 같이 변경되어야만 한다. (정확한 위치이기에) 
기존의 주소로는 접근이 불가하다는 말이다. <strong>이 점이 URL의 최대 단점이라고 볼 수 있다.</strong>
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/9f7419f6-cb6e-4d62-92af-6b05de478286/image.png" /></p>
<p>➡ B는 주소를 따로 변경하지 않아도 서버측에서 index.html이 보여지도록 처리해준다.
<br />
<br /></p>
<hr />
<br />
<br />
머리 속에 박아두기 좋은 벤다이어그램 한 번 더 보고 마치자.

<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/fb444c55-c0ac-4423-ac77-96e8d471c63f/image.png" /> </p>
<br />

<p>⭐참고하면 좋은 글</p>
<ul>
<li><a href="https://www.charlezz.com/?p=44767">https://www.charlezz.com/?p=44767</a></li>
<li><a href="https://velog.io/@torang/URL%EA%B3%BC-URI%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90">https://velog.io/@torang/URL%EA%B3%BC-URI%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90</a></li>
<li><a href="https://hstory0208.tistory.com/entry/URI%EC%99%80-URL-%EB%B9%84%EC%8A%B7%ED%95%B4%EB%B3%B4%EC%9D%B4%EB%8A%94%EB%8D%B0-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%B4-%EB%AD%98%EA%B9%8C-%EC%99%84%EB%B2%BD-%EC%A0%95%EB%A6%AC">https://hstory0208.tistory.com/entry/URI%EC%99%80-URL-%EB%B9%84%EC%8A%B7%ED%95%B4%EB%B3%B4%EC%9D%B4%EB%8A%94%EB%8D%B0-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%B4-%EB%AD%98%EA%B9%8C-%EC%99%84%EB%B2%BD-%EC%A0%95%EB%A6%AC</a></li>
</ul>
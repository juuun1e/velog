<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/bc28b2db-1398-42d7-bf90-79c0e417465a/image.png" /></p>
<h2 id="🚨왜애애애애애애애앵ㅇ">🚨왜애애애애애애애앵ㅇ</h2>
<p>평소와 같이 커밋을 위해 <code>git add .</code>을 하는 순간 에러가 발생했다.
에러 전문은 아래와 같다.</p>
<blockquote>
<p>warning: LF will be replaced by CRLF in 파일경로.
The file will have its original line endings in your working directory</p>
</blockquote>
<p>파일경로에서 LF가 CRLF로 대체됩니다... <img alt="" src="https://velog.velcdn.com/images/juuunie/post/44e5d791-fdc2-4e09-91f5-2804e40e5a9d/image.png" />례..? 머선소리죠?
저희 사이 좋았자나여.. 제발 .. plz.. 
<br /><br /></p>
<hr />
<br />

<h2 id="💨-아니-글쎄-lf랑-crlf가-개행문자래">💨 아니 글쎄 LF랑 CRLF가 개행문자래..!!</h2>
<p>알아보니 <code>LF(Line Feed)</code>와 <code>CRLF(Carriage Return Line Feed)</code>는 줄을 바꾸는 방식을 의미했다.
이 용어는 아래 사진에 보이는 타자기에서 유래한 용어라고 한다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/668b2e47-6190-4bd1-8445-7299dcfaa316/image.png" />LF(Line Feed)는 타자기 시절 페이퍼 롤을 한 줄씩 아래로 이동시키는 명령어였고
 CR(Carriage Return)은페이퍼 롤을 우측으로(=커서는 맨 앞으로)이동시키기 위한 명령어였다. 현재 키보드의 Home키 정도로 생각하면 쉬울 것 같다.</p>
<p> 정리하자면,
 LF(\n)는 커서는 그대로 있는 상태에서 줄만 바꾸는 동작,
 CR(\r)은 현재 키보드로 Home키 : 현재 커서를 맨 앞으로,
 CRLF(\r\n)는 두 가지를 모두 수행하여 현재 키보드의 엔터키 정도가 되겠다.
<br /><br /></p>
<hr />
<br />

<h2 id="🚨-에러-발생한-이유">🚨 에러 발생한 이유</h2>
<p>타자기 시절부터 사용되어온 방식들을 컴퓨터 체제에도 그대로 적용되었는데,
기술이 발전되면서 효율과 성능을 최우선시 하다보니 
줄바꿈을 할 때도 적은 자원을 활용하고 싶어 했다.</p>
<p>풀어서 말하자면, <code>\n</code>만 써도 줄바꿈이 되는데 
굳이 4byte<code>\r\n</code>을 사용하면서 할 필요가 없어진 것이다.</p>
<p>하지만 운영체제별로 줄바꿈을 하는 방식이 달랐다.
윈도우는 기본 포맷인 CRLF를, 유닉스 계열은 LF를 채택하여 사용하고 있다.</p>
<p>이 둘은 바이트코드가 다르기에 다른 코드로 인식한다.
그래서 커밋할 때 줄바꿈 타입이 다르면 변경하지 않은 파일에 대해서도 
변경된 거라고 잘못 인식하기에 한 가지로 통일해줘야만 하는 것이다.
(통상적으로 <code>LF</code>통일을 권장하고 있다고 한다.)
<br /><br /></p>
<hr />
<br />

<h2 id="🚨-우찌-해결하셨습네까">🚨 우찌 해결하셨습네까</h2>
<p><code>core.autocrlf</code> 설정을 통해 개행문자를 통일해주면 된다.
default값이 false인데 true로 바꿔주면 CRLF를---&gt; LF로 변경해준다.</p>
<p>따라서 윈도우즈에서는 true로ㅡ 
리눅스 계열은 input으로 설정하는 게 가장 적합하다고 한다.</p>
<pre><code>// 해당 프로젝트에만 적용할 경우
윈도우 $git config core.autocrlf ture
Mac $git config core.autocrlf input</code></pre><p>시스템 전체에 적용할 것이라면 <code>--global</code> 옵션을 추가해줘야 한다.</p>
<pre><code>// 시스템 전체에 적용할 경우
윈도우 $git congig --global core.autocrlf ture
Mac $git congig --global core.autocrlf input</code></pre><br />

<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/c968a6ef-1551-4c75-b78e-91a2774461e3/image.png" />바뀐 설정을 적용시키고 나니까<br />문제가 되었던 <code>git add .</code> 부터 
<code>git commit -m &quot;커밋메시지&quot;</code>, 
<code>git origin main</code>과정까지 무사히 마칠 수 있었다!!</p>
<p>야호!</p>
<hr />
<h2 id="⭐️-참고하면-짱-좋은-글">⭐️ 참고하면 짱 좋은 글</h2>
<ul>
<li><a href="https://sasca37.tistory.com/301">https://sasca37.tistory.com/301</a></li>
<li><a href="https://velog.io/@jakeseo_me/LF%EC%99%80-CRLF%EC%9D%98-%EC%B0%A8%EC%9D%B4-Feat.-Prettier">https://velog.io/@jakeseo_me/LF%EC%99%80-CRLF%EC%9D%98-%EC%B0%A8%EC%9D%B4-Feat.-Prettier</a></li>
</ul>
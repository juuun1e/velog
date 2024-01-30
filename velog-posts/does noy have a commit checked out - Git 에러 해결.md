<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/7ea2c0f9-965b-4ee9-a931-a7fd423c90be/image.png" /></p>
<h2 id="🚨-오류와의-만남">🚨 오류와의 만남</h2>
<p>23년 8월 끝자락에 처음 만났던 자바
<del>당시에 이클립스를 사용하기도 했고 가장 기본적인 개념들이 흐리멍텅해져서</del>
기본 개념을 다시 복습하면서 intellJ툴에 익숙해지기 위해
다시 공부하기 시작했다.</p>
<p>겸사겸사 손놓고 있던 github 잔디도 열심히 심어봐야겠다!
다짐했는데 does not have a commit checked out 이라는 에러를 만났다.
<br />
<br /></p>
<h2 id="🚨-오류-내용">🚨 오류 내용</h2>
<blockquote>
<p> does not have a commit checked out</p>
</blockquote>
<p>이게 무슨 오류인가 했더니 
로컬저장소에 .git이 중복 저장되었을 때
정확한 저장소가 어딘지 못찾아서 나타나는 현상이었다.
<br />
<br /></p>
<h2 id="🚨-오류-해결해보자">🚨 오류 해결해보자</h2>
<p> Mac에서 숨김처리된 파일을 보고싶으면 
<code>command</code> +<code>shift</code> +<code>.</code> 단축키를 사용하면 된다
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/3128d436-f07e-4ac6-8a5a-1f2e02ef19ad/image.png" /> 살펴보니까 상위폴더 Study와</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/6168c7b9-a814-4c22-a83e-882baff39d90/image.png" /> 그의 하위폴더에 있는 Study &gt; IntelliJJava &gt; HelloWorld 파일에도
  <code>.git</code>이 설치되어있음을 확인할 수 있었다.</p>
<br />

<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/adf404fc-d49a-46c4-8792-9fb0c918d647/image.png" />왜 이런 현상이 나타났나 했더니 intellJ에서 새로운 프로젝트를 생성할 때
Create Git repository에 체크해서 초래된 일이었다.</p>
<p>Study &gt; IntelliJJava &gt; HelloWorld 파일에 있던 <code>.git</code> 파일을 삭제해주니 해결됐다!~
<br />
<br /></p>
<hr />
<h2 id="💨-커밋해보자">💨 커밋해보자</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/148ddf56-54ec-4460-8494-d2000013609c/image.png" /><code>git status</code> 명령어로 변경 사항을 확인,
<code>git commit</code> 으로 커밋한 뒤
<code>git push origin main</code> 푸쉬하고 나면</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/c9ec20f8-58bf-4a87-bede-0dad29c9645b/image.png" />자잔-! 리모트에도 정상적으로 커밋된 모습이다!!
잔디 열심히 심자!</p>
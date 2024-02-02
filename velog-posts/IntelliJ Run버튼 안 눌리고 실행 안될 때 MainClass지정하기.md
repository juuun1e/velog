<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/f1b67ec4-5d4d-4f06-a905-06e0de1c0ec0/image.png" />IntelliJ로 SpringBoot를 활용하는 예제에서
Thymeleaf(타임리프)로 화면을 처리하는 부분을 다루던 중,
Run버튼이 눌리지도 않고 실행되지 않는 상황이 발생했다.<span style="color: gray;">
(참고로, Thymeleaf은 동적 컨텐츠를 생성하는 방법인 템플릿 엔진의 일부로,
JSP처럼 서버에서 결과를 만들어 클라이언트로 전송해주는 녀석이다.)</span></p>
<p>Thymeleaf를 이용하는 경우,
변경 후에 만들어진 결과를 서버에 계속 보관(캐싱)하지 않도록
설정해두는 것이 편리하다고 해서</p>
<p>application.properties 파일에 </p>
<pre><code class="language-java">spring.thymeleaf.cache=false</code></pre>
<p> 위 부분을 추가한 뒤로부터 버튼이 사라져버렸다.</p>
<hr />
<h2 id="🚨-얼렁뚱땅-해결">🚨 얼렁뚱땅 해결</h2>
<p>솔직히 아직까지 ...
왜 ? 버튼이 사라진지는 모르겠지만 ..</p>
<p>Thymeleaf파일을 수정하고 저장한 후에 
브라우저에서 잘 변경되었는지 결과를 확인하는 설정이 필요하다고 한다<img alt="" src="https://velog.velcdn.com/images/juuunie/post/afbe9064-2469-4a49-8cc6-26962cfc3d3d/image.png" />프로젝트 재시작에 편리하도록 상단메뉴에서
<code>Edit Configurations</code>를 선택하여 설정을 변경해줬다.
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/9cce0598-7e7a-4d67-8fb6-92971704377b/image.png" />새로운 어플리케이션 실행 환경설정을 추가하자!
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/13e1697a-bdfa-4b87-8ab2-25af60fa703a/image.png" />이름을 적고 main클래스를 지정해주면 된다.
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/ca5ce826-7642-477c-a517-51389346578b/image.png" /> <code>Main Class</code>칸에서 <code>Shift+Enter</code>키를 누르면 
요래요래, 시작을 알리는 Main Class를 지정할 수 있다
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/90a71db1-e668-4272-a3c7-ec5458a5d72b/image.png" />지정해주고 나니 다시 살아난 Run 버튼..!!!
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/a9acfece-1509-4096-ac9d-1b2878f72efb/image.png" /> 서버도 잘 실행되고
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/af7157c7-fc52-4fdc-9643-d18f3e7864e9/image.png" /> localhost:8080 접속해도 정상 작동 되었다!!</p>
<hr />
<p>음.. 
왜 버튼이 사라졌을까 생각을 해봤는데,
소스파일에 시작을 알리는 main class가 없어서
실행할 수가 없었던 ... 것이 아닐까&gt;</p>
<p>하는 개인적인 생각.....
더 알아봐야겠다 </p>
<p>얼렁뚱땅 오늘도 해결을 하긴 했네..</p>
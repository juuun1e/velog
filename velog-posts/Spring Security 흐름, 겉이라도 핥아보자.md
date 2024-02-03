<p>시큐리티가 어떻게 돌아가는 지
흐름을 가볍게 알아봅시당당당</p>
<p>그 전에!
서블릿과 필터의 역할을 먼저 짚고 넘어간다면
이해하는 데 도움이 될 것이다</p>
<hr />
<h2 id="🧐-servlets--filters">🧐 Servlets &amp; Filters</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/54792183-9c44-4372-9ad6-0f21395bf9ca/image.png" />어떤 자바 웹 어플리케이션이든, 
유저의 요청과 그에 대한 응답을 HTTP방식으로 주고 받는다.
<u>➡ 브라우저는 HTTP프로토콜만 이해할 수 있기 때문이다.</u></p>
<p>서로 소통할 수 있도록 도와주는 누군가가 절실하게 필요한데,
이 중재자 역할을 해주는 녀석이 바로 <code>Servlet</code>인 것이다.</p>
<p><span style="color: gray;">== 중재자 == Servlet container  == web server == Apache Tomcat </span>
<br /></p>
<h3 id="💨-중재자-서블릿-컨테이너의-역할">💨 중재자, 서블릿 컨테이너의 역할</h3>
<p>브라우저로부터 받은 HTTP메시지를 
자바코드가 알아들을 수 있도록
<code>ServletRequest object</code>로 변환해준다.</p>
<p>응답을 보낼 때는 변환해뒀던 HTTP ServletRequest object를 
다시 브라우저가 이해할 수 있는 HTTP메시지로 변환해주기에
요청을 주고 받을 수 있는 것이다.</p>
<p>중요한 역할을 맡고 있는 Servlet은 
엄청 복잡하기 때문에 아무도 직접 사용하지 않는다.
➡ 스프링부트와 스프링 프레임워크를 활용하여 사용 중이다.
<span style="color: gray;">(지정만 해주면 알아서 서블릿 생성해주고 복잡한 로직도 처리해줌)</span>
<br /></p>
<h3 id="💨-특별한-종류의-서블릿--필터">💨 특별한 종류의 서블릿 == 필터</h3>
<p>필터는 이름처럼 걸러주는 역할을 한다.
웹 애플리케이션으로 들어오는 모든 요청을 가로채서 판별해주는 것이다.</p>
<p>실질적인 비즈니스 로직이 실행되기 전에 반응하기 때문에
먼저 일어났으면 하는 로직을 정의할 수도 있다!!</p>
<p>Spring Security에서는 필터의 사용해야만 설정에 따른 보안이 시행되기에
필터에 대한 이해가 선행되어 있으면 좋을 것이다.</p>
<p>이제 진짜 Security 흐름을 핥아보자(???)
<br /><br /></p>
<hr />
<br />

<h2 id="🧐-시큐리티-흐름">🧐 시큐리티 흐름</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/74e15eb2-3554-4bb9-b663-52ce56d4363b/image.png" /></p>
<h3 id="1-user의-접근">(1) User의 접근</h3>
<h4 id="u📍-자격증명--서버에-요청-전송u"><u>📍 자격증명 + 서버에 요청 전송</u></h4>
<ul>
<li><p>Servlet container 또는 Tomcat서버나 웹 애플리케이션이 
요청을 받음과 동시에 <strong><code>Security Filters</code></strong> 가 요청을 걸러낸다<img alt="" src="https://velog.velcdn.com/images/juuunie/post/214bb4ca-b418-49db-87a4-f85aee0326b5/image.png" /></p>
</li>
<li><p><strong>Security Filters</strong></p>
<ul>
<li>접근하고자 하는 경로 확인 → 접근 가능한지/보호된 페이지인지 판별 
 → 인증 여부를 판별해 페이지를 보여준다</li>
<li><span style="color: gray;">필터 중 유저가 이미 로그인 했는지 체크하는 로직이 있어 결과에 따라 로그인 페이지를 보여줄 지 말지 결정<ul>
<li><span style="color: gray;">20개 이상의 필터가 각각 고유한 역할과 책임을 가진 채 존재하고 있다</span><img alt="" src="https://velog.velcdn.com/images/juuunie/post/4d0170a2-dfb5-496e-82bf-437104d31956/image.png" />
<br /><br /></li>
</ul>
</li>
</ul>
</li>
</ul>
<h3 id="2-로그인-여부-확인--인증객체에-저장">(2) 로그인 여부 확인 : 인증객체에 저장</h3>
<h4 id="u📍-기존-세션id나-기존-토큰을-활용u"><u>📍 기존 세션id나 기존 토큰을 활용</u></h4>
<ul>
<li>유저가 입력하는 유저네임과 비밀번호를 빼와 → <code>Authentication</code>객체로 변환(=저장)<ul>
<li><span style="color: gray;">Authentication,인증객체  |  사용자의 정보를 저장하기 위한 공간으로 
username과 자격이 증명되었는지에 대한 정보만 들어있다.</span>
<br /><br />

</li>
</ul>
</li>
</ul>
<h3 id="3-authenticationmanager에게-전달">(3) AuthenticationManager에게 전달</h3>
<h4 id="u📍-authenticationmanager는-실질적인--인증-을-관리하는-인터페이스--또는-클래스이다u"><u>📍 AuthenticationManager는 실질적인 [ 인증 ]을 관리하는 인터페이스  또는 클래스이다.</u></h4>
<ul>
<li>특정 요청에 따라 유효한 <em>인증제공자(provider)_가 있는 지 확인 
<span style="color: gray;"> _예를 들어 USER, Admin 등.. 개발자의 요구사항에 따라 무한대로 정의 가능</em> </span> <ul>
<li><span style="color: skyblue;">Manager가 성공 vs 실패지점에 도달할 때까지 존재하는 모~든 provider에게 전송해 인증을 시도한다 </span> (실패했으면 인증이 실패했다고 응답)<br />

</li>
</ul>
</li>
</ul>
<h3 id="4-authentication-provider에게-전달">(4) Authentication Provider에게 전달</h3>
<ul>
<li>실질적인 인증 로직을 직접 작성하거나 spring secutiry에서 제공하는 <code>UserDetailsManager/Service</code> 인터페이스와 클래스 활용
<br /><br /></li>
</ul>
<h3 id="5-userdetailsmanagerservice-인터페이스와-클래스">(5) UserDetailsManager/Service 인터페이스와 클래스</h3>
<h4 id="u📍-데이터베이스에서-유저-정보를-불러와줘u"><u>📍 데이터베이스에서 유저 정보를 불러와줘!</u></h4>
<ul>
<li>데이터베이스에 저장된 정보 == 사용자가 입력한 정보를 비교
<br /><br /></li>
</ul>
<h3 id="6-passwordencoder-인터페이스">(6) PasswordEncoder 인터페이스</h3>
<h4 id="u📍-비밀번호를-암호화-해싱해줘u"><u>📍 비밀번호를 암호화, 해싱해줘!</u></h4>
<p> <code>UserDetailsManager</code> <code>UserDetailsService</code> <code>passwordEncoder</code> 
⇒ 유저가 제공한 자격증명이 유효한 지 협동해서 판별
  그 결과에 따라 provider에게 자격증명이 유효한지 응답 반환
  <br /><br /></p>
<h3 id="7-다시-인증-관리자에게-넘김">(7) 다시 인증 관리자에게 넘김</h3>
<p>provider의 로직이 끝났다면 응답을 Manager에게 넘겨줌
<br /></p>
<h3 id="8-security-filters이-돌아감">(8) Security Filters이 돌아감</h3>
<br />

<h3 id="9-2단계에서-생성한-authentication객체를-security-context에-저장">(9) 2단계에서 생성한 <code>Authentication</code>객체를 Security Context에 저장</h3>
<p> : [ 인증이 성공적이었는지 아닌지 ],[ 세션ID가 무엇인지 ]의 인증 정보<br />     ➡ 첫 번째 시도에서 인증이 성공적이었다면,  자격증명을 다시 요구하지 않음
  <br /></p>
<h3 id="10-유저에게-보안-페이지-반환">(10) 유저에게 보안 페이지 반환</h3>
<hr />
<p>  단순 호기심에서 시작한 Spring Security 공부.
  아직 보안 쪽을 다룰 레벨은 아니지만 ㅎㅎ
  시작한 거 끝을 봐야하지 않겠어?!</p>
<p>  생각한  것만큼 복잡해서
  온전히 내 것으로 만들기에 시간이 걸릴 거 같지만,
  얼른 더 파헤치고 싶은 마음 뿐!!!!!!!!!</p>
<p>  그 땐 지금보다 더 쉽게 재구성하여 기록할 수 있기를 </p>
<h2 id="🚨-에러-발생">🚨 에러 발생</h2>
<p>국비로 학원다니고 있는데 머신러닝/딥러닝을 배우던 중 처음보는 녀석을 만났다 . . . . 
<del>(( 파이썬 코드로 3차원 시각화시켜주는 과정에서부터 에러.. ))</del>
딥러닝 들어가자마자 나 뿐만 아니라 교실 전체가 각기다른 오류로 난리였음💨</p>
<p>참고로 세 번의 시도 끝에 해결했습니다!! 
급하신 분은 세 번째 시도를 참고해주세요!</p>
<br />

<h2 id="🚨-에러-내용">🚨 에러 내용</h2>
<blockquote>
<p>[python]
This application failed to start because it could not find or load the Qt platform plugin &quot;windows&quot; in &quot;&quot;.
Reinstalling the application may fix this problem.</p>
</blockquote>
<p>실행되다 말고 위와 같은 에러가 뜨면서 중단되고 있었다...</p>
<p>Qt는 뭐하는 작자이신지 ...?
생소한 단어라 바로 구글링 해봤다</p>
<pre><code>[Qt란]
C++을 주 언어로 사용하는 GUI 프레임워크(또는 툴킷-Toolkit). '큐트'라고 읽는다. 
C++와 QML이라는 자체 스크립트 언어를 기반으로 한다.  
</code></pre><p>흠 이렇게만 봐선 잘 모르겠다</p>
<p>GUI 툴킷이 무엇인지 찾아보니, 
프로그래밍을 쉽게하기 위해서 버튼이나 박스, 윈도우 같은 클래스들을 모아놓은 라이브러리라고 한다.</p>
<p>맥락상 Qt는 윈도우 체제에서 위젯을 만들기 위해 사용된 라이브러리인 듯 했다.</p>
<p>다시 본론으로 돌아와 오류를 처리해보장</p>
<br />

<hr />
<br />

<h2 id="첫-번째-시도--환경변수-추가">첫 번째 시도 : 환경변수 추가</h2>
<p>구글링 해보니까 Qt plugin 경로를 환경변수에 추가해야 한다고 했다.
(Qt가 설치되어있는지 확인 먼저 했더라면 빠르게 해결할 수 있었을텐데 ...)</p>
<p>뱡법은 어렵지 않았다! 파이썬 설치된 경로를 찾아 추가해주면 되는 것!
<del>(( 파이참에서  파이썬으로 사용하는 것이기에 파이썬 경로를 넣어줘야 함 ㅇㅇ))</del>
<br /></p>
<p>환경변수는 <code>시스템</code> 의 <code>고급 시스템 설정</code>에서 설정할 수 있다.
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/2d5a22f7-00ac-4a30-b726-4e108dc75b3e/image.png" />파일탐색기 ➡ 내pc에서 마우스 우클릭 ➡ 속성으로 들어가면
<code>시스템</code> 으로 쉽게 접근할 수 있다.
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/83002f74-0bac-45f4-bfb6-7db0edb6c812/image.png" /> 하단이나 사이드 메뉴에 작게 적혀있는 <code>고급 시스템 설정</code> 으로 들어가자.
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/8a93de18-2e60-4974-b543-708e30e021af/image.png" /> <code>환경변수</code> 로 들어가면 사용자(KOREAVC)에 대한 사용자변수와 시스템변수, 두 가지가 보일 것이다. 
우리가 지금 봐야할 것은 <code>시스템 변수</code>!
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/363cb640-41c7-4df4-a244-8fa73850f2ba/image.png" />
생각해보니까 나는 이미 pythonhome 이라는 이름으로 설정해뒀던 상태였다..
어찌하지 -_-;;  싶다가 일단 하라는대로 
<code>QT_QPA_PLATFORM_PLUGIN_PATH</code> 이라는 새로운 이름의 변수를 만들어봤는데 오류는 해결되지 않았다.</p>
<p>포기란 없지, 다른 방법을 시도해보기로 했다 !
<br /></p>
<hr />
<br />

<h2 id="두-번째-시도--힌트를-얻음">두 번째 시도 : 힌트를 얻음!</h2>
<br />
호기롭게 새로운 방법을 찾아 덤볐지만 실패...

<p>Qt 플러그인에 필요한 DLL 파일이 모두 존재하는지 확인하는 방법이 두 번째 방법이었는데,
((platforms 폴더에 qwindows.dll 파일이 있는지 확인해야했음))</p>
<p>Windows 명령 프롬프트에서 where 명령어를 사용하여 
특정 DLL 파일의 위치를 확인할 수 있었다
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/b4f45b8f-97c0-4a50-9d58-2e193df2c7f9/image.png" />
해당되는 파일을 찾지 못했습니다 ...🤦‍♂️
<br /></p>
<p>이렇게 타고타고 .. 뒤적뒤적 찾아보다가
내가 사용하고 있는 PC에 Qt자체가 없었던 것..을 알게 되었다 </p>
<p>결국 <code>PyGLM PySide2 pyopengl</code> 이라는 것을 설치하는 방법 선택!😇
<br /></p>
<hr />
<br />

<h2 id="세-번째-시도--성공">세 번째 시도 : 성공!</h2>
<p>있는지 없는지 잘 모른다면 cmd창에서 아래 코드를 입력해보면 될 듯하다</p>
<pre><code>pip uninstall PyGLM PySide2 pyopengl</code></pre><p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/e6f276f8-b0d0-4a04-a22d-55858531a969/image.png" />
나같은 경우에는 설치가 안되어있었음!! 
기존에 있다면 삭제가 될 것임다
<br /></p>
<p>아래 3개를 차례대로 설치해주면 된다</p>
<pre><code>pip install PyGLM PySide2 pyopengl</code></pre><pre><code>pip install pyqt5</code></pre><pre><code>pip install pyqt5-tools</code></pre><p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/59e4498d-2cd3-4371-b64c-c98c83404ee6/image.png" />
참고) 이미 설치되어있다면 위처럼 already 어쩌구가 나온다
uninstall하고 다시 설치해주기!
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/0372deea-df37-48ce-bdd7-fee133908544/image.png" />
재설치 하고 나서
파이참 재로딩하니까 정상작동 됐다 ㅎㅎ
오류해결 완료</p>
<hr />
<p>아직까지 오류가 나면 당황타기 바쁘고
왜 났고 해결되어도 왜 해결되었는지 정확한 경위는 모르겠지만
차근차근 하다보면 어느순간 알게될 거라고 생각한다!!</p>
<p>이 오류 덕분에 qt라는 것도 알게 되고
GUI 툴킷이라는 것도 알게 되었구나!!!!!!!!</p>
<p>참고 </p>
<ul>
<li><a href="https://log-mylife.tistory.com/entry/Could-not-load-the-Qt-platform-plugin-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0%EB%B2%95">https://log-mylife.tistory.com/entry/Could-not-load-the-Qt-platform-plugin-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0%EB%B2%95</a></li>
<li><a href="https://blog.naver.com/sunra2k/40036017432">https://blog.naver.com/sunra2k/40036017432</a></li>
</ul>
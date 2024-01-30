<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/4ad10ffa-66aa-4bde-81f1-6837a31de4ac/image.png" />Pycham에서 딥러닝 예제를 다루고 있었다.
처음에는 line1에 tensorflow도 오류가 있어서 하던대로 설치했다</p>
<blockquote>
<p>(venv) pip install tensorflow </p>
</blockquote>
<p>당연히 keras도 함께 설치되었을 거라고 생각했는데<br />무슨 일인지 line 3의 오류는 사라지지 않았다.
<br /><br /></p>
<h2 id="🤔-오류-전문">🤔 오류 전문</h2>
<pre><code>Cannot find reference 'keras' in '__init__.py | __init__.py</code></pre><p>어떠한 이유로 라이브러리를 인식을 못하고 있음을 뜻한다.</p>
<p>터미널 창에서 tensorflow랑 keras를 삭제 후 재설치해보고,
상단 메뉴 <code>File &gt; setting &gt; Project&gt; Python interpreter 메뉴</code>로 가서
가상환경 path를 다시 설정해보기도, 재설치도 해봤는데 해결되지 않았다.</p>
<p>교과서를 뒤적거리니 thensorflow를 2.8버전으로 사용했다고 하길래
버전을 맞춰서 다시 설치해보기로 했다</p>
<p><br /><br /></p>
<h2 id="🤔n번째-시도--재설치버전변경">🤔N번째 시도 : 재설치(버전변경)</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/460f978d-829e-472c-90bd-6f8849bbdb9a/image.png" /> interpreter로 이동해보자!
상단메뉴 file의 Setting으로 들어가면</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/0cc0972e-f483-4790-88fd-598b0a3322d5/image.png" />project의 Python Interpreter라는 곳에서 설치도 하고, 버전 관리도 할 수 있다.
<br /><br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/f820c1c4-47a3-4dba-91b1-87cd69e580f1/image.png" />기존 2.15.0버전을 가지고 있었는데 2.8.0버전으로 새로 설치해봤다</p>
<br />

<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/fc55ffe8-5a8d-46e4-968a-c5f99fb1ca19/image.png" /> 실행해보니 <code>protobuf</code>라는 패키지의 버전이 맞지 않아 충돌한다는 에러가 떴다.
3.20이나 그 아래의 버전이 필요한가보다
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/d31c6029-0e39-48f3-836f-66ecd7f5b91f/image.png" /> 확인해보니 나는 4.23.4 버전을 가지고 있었다</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/b776b5ce-3884-4522-8ef8-07bc9f5fe9a9/image.png" /> 더블클릭해서 들어가 specify version을 체크하면 
보이는 것처럼 버전을 선택해서 설치할 수 있다!
원하는 버전을 클린한 뒤 왼쪽 아래에 있는 <code>install Package</code> 클릭~!
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/bfb38520-eef5-4646-9237-8916817bca5d/image.png" />했는데...? 그래도 여전히 같은 오류가 뜨고 있었다... 
근데 빨간줄만 뜨고 또 실행은 된다. 왜지 ????????</p>
<p>너 .. 살짝 약오른다?
<br /><br /></p>
<h3 id="💨-추가-확인">💨 추가 확인</h3>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/6d9114e0-25a2-4fff-8e86-29e2896b4e1e/image.png" /> 인식을 못한다길래 
keras.json파일에 tesorflow가 잘 설정되어있는지 확인해봤다.
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/deb0b1d2-717c-4d7f-be85-d8fa98f71d2b/image.png" /> 잘 되어있네용 ...
빨간줄 안없어져도 되니까 
제발 이유만 알려주라....주라주라 제바류</p>
<p><br /><br /></p>
<hr />
<br />

<h2 id="😲-어쩌다-해결">😲 어쩌다 해결</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/3d5a8eb1-9ff1-4011-a696-eef6b0282b0e/image.png" /> Input과 Dense의 클래스를 찾지 못한다는 메시지가 보여지고 있었다. 
<em>tensorflow에 이런 클래스가 없나?</em> 하면서
혹시..! 하는 마음에 스리슬쩍 지워봤다 
<br />
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/8b5d7847-5f2a-4194-80ab-8dda5bb06bc5/image.png" />뭥미.. 이렇게 간단하게 해결될 일이냐고오
찾아보니까 keras랑 tensorflow.keras랑 별개의 패키지라고 인식된다고 하던데,
무슨 말인지 전혀 모르겠고 . . . . 어떤 차이가 있는지는 더 알아봐야겠다.
<br /><br /></p>
<hr />
<br />

<h3 id="-💨-로그-수준-설정법">+) 💨 로그 수준 설정법!</h3>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/70f80318-d3e4-4b78-98db-753a14e77891/image.png" /> 실행할 때 GPU 관련된 WARNING 메시지가 엄청 떴다.
에러는 아니지만 .. 물론 해결하면 좋겠지만 .. 그럴 여유가 없을 때
출력하는 로그의 수준을 설정할 수 있다</p>
<blockquote>
<p>import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'</p>
</blockquote>
<p>맨 윗 부분에 위 코드를 입력해두면 INFO 레벨의 로그를 표시하지 않고, ERROR 로그만 보여지게 된다. 
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/442f7a8f-c302-4c82-94d6-58d51429f4f1/image.png" /> 추가한 결과 사진처럼 출력코드가 깔끔하게 나타난다!!
<br /><br /></p>
<hr />
<br />

<p>⭐참고하면 좋은 글 </p>
<ul>
<li><a href="https://pyimagesearch.com/2016/11/14/installing-keras-with-tensorflow-backend/">https://pyimagesearch.com/2016/11/14/installing-keras-with-tensorflow-backend/</a></li>
</ul>
<p>파이참에서... OpenCV 머신러닝 모듈 예제를 다루려고 켜자마자 
임포트 부분에 빨간줄 천지 ㅋㅅㅋ</p>
<p>_까이꺼<del>! 설치해버리면 되지</del>!  _</p>
<p>했는데 오류가 자꾸 뜨더라고요 ........?
같은 실수 하지 말라고 기록 남기러 왔습니다 ㄱ-
<del>급하신 분은 맨 아래로💨💨</del>
<br /></p>
<hr />
<br />



<p>설치 하기에 앞서 OpenCV가 뭔지 간단하게 살펴볼까나</p>
<h2 id="💨-opencv-라이브러리">💨 OpenCV 라이브러리</h2>
<blockquote>
<p>Open source Computer Vision Library
이미지와 비디오 처리를 위한 오픈 소스 라이브러리로
C++, Java, Python 등 다양한 언어에서 사용할 수 있다.</p>
</blockquote>
<p>이미지파일을 읽고 화면에 그려내는 방식은 참으로 다양하다.
2차원 배열을 다루는데 제 격인 <code>numpy(넘파이)</code>로 표현한 배열을
<code>matplotlib(맷플로립)</code>으로 그려내는 방법도 있다.
<span style="color: gray;">
<del>matplotlib의 처리방식을 간단하게 설명하자면,
pyplot모듈이 가지고 있는 imshow()함수로 저장된 이미지를 시각적으로 확인하고,
pyplot의 show()함수로 최종적으로 그림을 그리는 방식이다.
  <span style="color: gray;">
-&gt; plt.imshow(img)
-&gt; plt.show()
  </span>
 위처럼 이미지를 그릴 때 pyplot과 img를 섞어가며 처리해야 한다.</del>
</span></p>
<p>맷플로립의 번거로움을 해소시켜준 것이 
오늘 다루는 <code>OpenCV 모듈</code> 이라고 할 수 있다.</p>
<p>범용적인 프로그래밍 언어인 Python에서
이미지 조작하는 강력한 모듈, OpenCV를 제공하고 있다!<br /></p>
<p>이 모듈은 <code>import cv2</code> 명령을 통해 사용할 수 있고,
사용하기 위해서는 <code>opencv-python</code> 패키지를 설치해야만 했다.
<br /><br /></p>
<hr />
<br />

<h2 id="🧐-pycham에-opencv-설치하기">🧐 Pycham에 OpenCV 설치하기</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/e15b259d-e4b5-494e-bac8-cf11ed6cec98/image.png" /> A ㅏ...
<span style="color: gray;"><del>나에게 왜 이런 시련이</del></span>
새로운 걸 알아갈 기회를 주셨네 또 ㅎㅎ</p>
<p>무작정 cv2 를 설치하려고 하면 위와 같은 오류가 찾아올 것이다
앞서 말했듯이 <strong><code>cv2</code>를 사용하기 위해서는 <code>opencv-python</code> 패키지</strong>를 설치해야만 했다.
<br /><br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/86443ecf-28e4-4509-ab24-3ffd61ab2dda/image.png" /></p>
<pre><code>pip install opencv-python</code></pre><p>패키지를 먼저 설치했는데도 여전히 빨간 줄이 뜨길래 .. ㅎㅎ
<br />
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/ffba5c0b-d527-4405-b866-eb9891511327/image.png" /> 냅다 <code>cv2</code>를 설치하려 시도해봤더니 처음에 나왔던 오류가 맞이해줬다.</p>
<p>ㅎㅎ..ㅎㅎ ㅎ...ㅋㅎㅎ... ㅎㅎ..
흐음... 패키지 설치 됐다고 했는데...?</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/51ad08bc-b95a-4142-8e5d-6928be569042/image.png" />역시.. 바보는.. 시간을 막 내다 버리고.. 그런ㄷr ...?
혹시 옥의 티 찾으신 분 ...?😇</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/5bf1a964-a611-424d-ac61-864ef5b25ae2/image.png" />
가상환경이 아니고 ... 파워셀에서 하니까 당연히 적용이 안되죠... 네...</p>
<hr />
<h3 id="여기서-잠깐---파워셀ps이-뭐야"><em>여기서 잠깐-!</em>  <em>파워셀(PS)이 뭐야?</em></h3>
<blockquote>
<p>⭐ 쉽게 말해서, <strong>cmd의 확장형</strong>이라고 생각해주면 될 듯하다...!
⭐ PS는 윈도우 전체! OS에서 사용하는 환경을 말한다.</p>
</blockquote>
<p>++ 우리가 사용하는 <span style="color: green;"><strong>가상환경</strong></span>은 (( OS 상관없이 )) 
<span style="color: green;"><strong>프로젝트마다 라이브러리를 관리해주는 용도</strong></span>라고 할 수 있다. </p>
<p>파이썬은 버전이 호환이 안되기 때문에 
각각의 프로젝트에 맞게 적절한 버전으로 설정하고 
꼭 필요로 하는 패키지만 설치하도록 독립시켜 
<strong><span style="color: green;">충돌</span>을 <span style="color: green;">최소화</strong></span> 시켜주는 목적이다.</p>
<p>괜히 가상환경을 만들어서 사용하고 있는 게 아니었다..ㅎㅎ 
가상환경 덕분에 하나의 OS아래에서 여러버전의 파이썬을 사용할 수 있는 것이다!</p>
<hr />
<h2 id="💨-가상환경에서-다시-설치-해보자">💨 가상환경에서 다시 설치 해보자!</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/f4bea7d0-2cd7-4c8d-a388-9c2a559a3601/image.png" />1. cmd 창으로 이동한다
2. 가상환경으로 이동한다
3. <code>opencv-python</code> 패키지를 설치한다!!!</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/2cff011c-7357-4bf3-8d65-838f71aded83/image.png" />히히 이제 마음껏 사용할 수 있다!!
<br /></p>
<hr />
<p><br />참고로 가상환경에서 탈출은 exit로 ~!
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/9f64c456-5f2d-4a60-88b9-c233efce6ddd/image.png" /></p>
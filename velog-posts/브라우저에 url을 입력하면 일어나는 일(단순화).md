<p>웹 브라우저에 '<a href="https://velog.io'">https://velog.io'</a> 라는 url을 입력했을 때,
어떤 일이 일어나기에 벨로그 페이지로 이동하는 걸까?</p>
<p>라는 막연한 호기심에서 시작하는 포스팅 시작하겠수다.</p>
<p>찾아보다가..... 어려워서 일단 단순화 시켜봤다.
나중에 업그레이드 시켜야지!!</p>
<p><del>(아직 많이 부족합니다. 정정해야할 부분이 있다면 댓글 부탁드리겠습니다 .. ❤️‍🔥)</del><br /><br /></p>
<hr />
<br />
일단 내가 url주소를 입력하고 있는 pc와 <br />
연결해주는 웹 서버 프로그램은 다른 컴퓨터에서 실행되고 있다.

<p>그렇기에 웹 브라우저가 웹 서버에 연결해야만 
원하는 웹페이지를 보여줄 수 있다.</p>
<p>서버가 실행 중인 컴퓨터의 주소를 알아야만 
연락을 하든 문을 두드려서 연결하겠지?
이 때 필요한 컴퓨터의 주소를 <code>ip주소</code> 라고 부른다.</p>
<p>휴대폰마다 전화번호가 다른 것처럼,
인터넷에 연결되는 컴퓨터들도 고유의 번호를 가지고 있는 것이다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/34cab61b-4d9c-4d3d-a08f-2e54b2c2bcb8/image.png" /> cmd창에서 
window는 <code>ipconfig</code>, 
ios는 <code>ipconfig getifaddr en0</code> 명령어로 
ip주소를 알 수 있다.</p>
<p>보면 알겠지만, ip주소는 숫자로 구성되어 있기에 외우기 쉽지 않았다,,
대신! 기억하기 좋은 도메인 이름을 사용하기로 한다. (google.com 과 같은..!) </p>
<p>전화번호로 비유하자면,
<code>친구의 전화번호(ip주소)</code>를 외우기 어려우니까
<code>'나의 ㄹr잎뿌렌드'(도메인이름)</code>과 같이 저장해 사용한다는 이야기이다.
<br /></p>
<p>하지만 위에서 말했듯
ip주소를 이용해서 브라우저와 서버가 연결되고 있었다.
도메인 이름을 ip주소로 바꿔줘야만 하는데,
이 역할을 해주는 녀석이 바로 <code>DNS(Domain Name Server)</code> 이다.
<br />
<br /></p>
<hr />
<br />

<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/06dec46d-448f-47bd-9d18-ace7327b18f2/image.png" /></p>
<p>이 그림을 다시 보면 이제 이해가 잘 될 것이다.</p>
<p>DNS로부터 ip를 받으면, 웹 브라우저는 3번 과정처럼 ip주소를 이용해서 웹서버에 연결한 뒤 url에 해당하는 웹 페이지를 요청하여 응답도 받게 되는 것이다.</p>
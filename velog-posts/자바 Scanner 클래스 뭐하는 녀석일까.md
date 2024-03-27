<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/1de4e1a9-8368-4eda-aef3-9b0d397a0f6e/image.png" />
기술 블로그 오랜만이로군. </p>
<p><del>그간 많은 일들이 있었지만 . . . 잠시 넣어두고 흑흑 . .</del> 
알고리즘 공부하다가 만난 <code>Scanner class</code>에 대해 파헤쳐보고 싶었다.</p>
<p><a href="https://docs.oracle.com/javase/8/docs/api/">자바 공식문서</a>도 조금 뒤져봤겠다~
휘발되기 전에! 얼른 끄적여 놓아야지.
<br /></p>
<hr />
<br />

<h2 id="🧐-스캐너scanner란">🧐 스캐너(Scanner)란?</h2>
<p><code>java.util</code>패키지 안에 존재하는 클래스로,
사용자(키보드)로부터 입력 받을 수 있도록 도와주는 녀석이다.
<br />
다음과 같은 특징을 가지고 있다.</p>
<ul>
<li><p>정수(int), 실수(double)등의 <strong>기본적인 데이터 타입</strong>을 
모두 입력받을 수 있는 <code>자바의 기본 입력 클래스</code>이다.</p>
</li>
<li><p>토큰 기준으로 읽는다. 
<strong>토큰</strong>이란 <strong>공백(띄어쓰기), 탭(Tab), 개행(Enter)</strong>으로 구분되는 요소를 의미한다.</p>
</li>
<li><p>위에서 말한 것처럼 <code>java.util</code> 패키지에 위치하기에 <strong>호출하여 사용</strong>해야 한다. 
자바에서 쓰이는 대부분의 클래스는 java.lang에 위치해 있다. 
사용하고자 하는 클래스가 lang패키지에 있는 게 아니라면 import가 필요하다.</p>
</li>
</ul>
<p><br /><br /></p>
<hr />
<br />

<h2 id="💨-스캐너-클래스의-사용">💨 스캐너 클래스의 사용</h2>
<h3 id="1-import문">1. import문</h3>
<p>쉬는 시간에 철수랑 같이 놀려면 철수 교실 앞에서
<em>&quot;철수야~ 노올자~&quot;</em> 하고 불러내야 한다. </p>
<p>우리는 Scanner와 놀고 싶으니까
util 교실에 앉아 있는 Scanner를 불러내보자.</p>
<pre><code class="language-java">// Scanner 클래스의 호출
import java.util.Scanner;
import java.util.*;</code></pre>
<p>Scanner 를 포함한 util 교실에 있는 모~든 친구들을 불러내고 싶을 때 <code>java.util.*</code> 와 같은 형식으로 호출한다면 모든 친구들을 한 번에 불러낼 수 있다.
<br /></p>
<h3 id="2-객체-생성">2. 객체 생성</h3>
<p> 다음과 같이 new(); 생성자 메서드로 객체를 생성한다.
<code>클래스_이름 객체_이름 = new 클래스_이름();</code> </p>
<p>우리는 Scanner 구조의 실체(객체)를 만들어 줄 것이기에 클래스 이름에는 Scanner를 넣고 객체 이름을 붙여주어 다음과 같이 생성한다.</p>
<p>참고로 Scanner의 객체 이름은 보통 sc로 네이밍한다.</p>
<pre><code class="language-java">    // 객체 생성
    Scanner sc = new Scanner(System.in);</code></pre>
<p><br />위 짧은 코드를 잘게 쪼개어 살펴보자면,</p>
<p><strong>new Scanner();</strong> 는
 메모리에 Scanner구조를 갖춘 실체를 만들어준다는 의미이다. (heap메모리에 할당)<br />
<strong>System.in</strong> 은 입력한 값을 Byte단위로 읽어주는 <code>자바의 표준 입력 스트림 InputStream</code>으로 <strong>화면에서 입력을 받겠다</strong>는 의미인데... </p>
<p><em>쉽게 말해, 입력되는 데이터들은 <code>in</code>이라는 통로를 통해서 들어온다는 말이다.</em></p>
<p>그렇기에 Scanner 뿐만 아니라 다른 입력 방식들도 
사용자로 부터 입력을 받기 위해서는 System.in을 사용하게 된다. 
<img alt="" src="https://velog.velcdn.com/images/juuunie/post/c67ca999-41ac-4fdf-bc7a-e1b774048951/image.png" />여기서 더 살펴보면 <strong>System</strong>클래스에서 필드 <strong>in</strong>은 
<u>InputStream 타입의 정적(static) 필드</u>이다. </p>
<p>정리하자면 </p>
<ol>
<li>inputStream은 java.io패키지의 최상위 입력 스트림 클래스이며</li>
<li>변수 in은 inputStrean타입의 새 변수를 선언하고 
그 변수에 System.in을 할당시킬 수 있다는 것이다.</li>
</ol>
<p>그러니까 
<code>Scanner sc = new Scanner(System.in);</code> 
    한 줄을 풀어서 적게 된다면~~
    <br /></p>
<pre><code class="language-java">    InputStream input = System.in;
    Scanner sc = new Scanner(input); </code></pre>
<p>   이렇게 된다는 말이다..!
   결론은 System.in을 사용해서 입력 받는다구!! </p>
<br />

<h3 id="3-입력-메소드로-입력하기">3. 입력 메소드로 입력하기</h3>
<p>Scanner의 입력 메소드는 다음과 같은 종류들이 있다.</p>
<pre><code class="language-java">    byte b = sc.nextByte();       // Byte형 - 입력받은 byte를 b에 저장
    short s = sc.nextShort();     // short형      
    int i = sc.nextInt();         // int형 
    ling l = sc.nextLong();       // long형

    float f = sc.nextFloat();     // float형
    double d = sc.nextDouble();   // double형

    boolean b = sc.nextBoolean(); // boolean형

    String str = sc.next();       // String형 - 공백 기준으로 한 단어
    String str = sc.nextLine();   // String형 - 개행(줄바꿈) 기준으로 한 줄</code></pre>
<p>눈치챘겠지만 String 입력을 제외하면
next+Type() 의 규칙이 존재한다.</p>
<p>참고로 단일문자형인 Char타입을 입력받는 메소드는 따로 없다.
<code>next()</code>함수와 <code>charAt()</code> 함수를 함께 사용할 수 있다.
  ---&gt; <code>next()</code> : String으로 받은 뒤,   <code>charAt()</code> :  단일문자로 반환해야 한다. </p>
<pre><code class="language-java">  char c = scanner.next().charAt(0);</code></pre>
  <br />
  스캐너 사용 시 주의사항을 살펴보며 
  얼렁뚱땅 마무리 하자!!<br /><br />
<br />

<hr />
<br />

<h2 id="🧐-스캐너-사용-시-주의사항">🧐 스캐너 사용 시 주의사항</h2>
<ul>
<li>객체를 생성하려면 이미 정의 되어있는 <code>표준 입력 스트림 System.in</code> 를 전달해야 한다. </li>
<li>특정 데이터 유형의 값을 읽기 위해서는 <code>next..()</code> 함수를 사용한다.</li>
<li><code>next()</code>와 <code>nextLine()</code>를 정확하게 구분하여 사용하자!</li>
</ul>
<br />
끗-!

<p><br /><br /><br /></p>
<p>⭐️ 이 글 어렵고 좋더라~
<a href="https://st-lab.tistory.com/41">https://st-lab.tistory.com/41</a></p>
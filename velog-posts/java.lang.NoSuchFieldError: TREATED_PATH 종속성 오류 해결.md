<h2 id="🚨오류와의-만남">🚨오류와의 만남</h2>
<p>Spring Boot의 JPA를 구현하기 위한 예제를 다루다가,
<code>java.lang.NoSuchFieldError: TREATED_PATH</code>라는 오류를 만나게 되었다.
<br /><br /></p>
<h2 id="🚨오류와의-이별">🚨오류와의 이별</h2>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/fca52b5e-8e23-4fc5-a3c2-532906813f06/image.png" /> 경로의 문제인가 싶었는데 역시나 QueryDSL의 버전이 명시되지 않아서 발생되는 오류였다.<br /><br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/be1e40cc-3c72-491c-b7c2-8b045c50225d/image.png" /> gradle에 querydsl-core 종속성을 추가해주었더니 해결되었다.<br /></p>
<pre><code class="language-java">//gradle 인 경우
implementation &quot;com.querydsl:querydsl-core:5.0.0&quot;


//pom.xml 인 경우
&lt;dependency&gt;
    &lt;groupId&gt;com.querydsl&lt;/groupId&gt;
    &lt;artifactId&gt;querydsl-core&lt;/artifactId&gt;
    &lt;version&gt;5.0.0&lt;/version&gt;
&lt;/dependency&gt;</code></pre>
<br />


<p><img alt="" src="https://velog.velcdn.com/images/juuunie/post/603f75c8-fc93-40d1-944a-20e3d1bd7d31/image.png" />정상작동 !! <span style="color: gray;">되어서 기쁘지만, ,
알멩이를 알아내지 못한 기분이라 찝찝's , , </span>
어쨌거나 오늘도 오류 해결 완<br /><br /></p>
<hr />
<br />

<h3 id="⭐-참고한-글-감사합니다">⭐ 참고한 글, 감사합니다</h3>
<ul>
<li><a href="https://stackoverflow.com/questions/68115868/querydsl-java-lang-nosuchfielderror-treated-path">https://stackoverflow.com/questions/68115868/querydsl-java-lang-nosuchfielderror-treated-path</a></li>
</ul>
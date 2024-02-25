# 에러코드

`Uncaught TypeError: Cannot read properties of null (reading 'value')`<br>
**이 에러코드는 주로 HTML에서 DOM이 형성되지 않았으나 JS를 이용해 이벤트를 줄 경우나 크롬에서 정의되지 않은 객체의 프로퍼티를 읽어내거나 method를 호출할 때 발생하는 거였다.**<br>
**이는 HTML에 JS를 넣는 스크립트 태그를 body의 가장 밑부분으로 내리면 되는거였다.**<br>
`<html>

  <head>
    ...
      <h2>응답</h2>
      <div id="response_area"></div>
    </div>

    <script type='text/javascript' src="./App.js"></script>

  </body>
</html>`

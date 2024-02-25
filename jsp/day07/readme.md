# 에러코드

`Uncaught TypeError: Cannot read properties of null (reading 'value')`<br>
**이 에러코드는 주로 HTML에서 DOM이 형성되지 않았으나 JS를 이용해 이벤트를 줄 경우나 크롬에서 정의되지 않은 객체의 프로퍼티를 읽어내거나 method를 호출할 때 발생하는 거였다.**<br>
**이는 HTML에 JS를 넣는 스크립트 태그를 body의 가장 밑부분으로 내리면 되는거였다.**<br>

````html
<html>
  <head>
    ...
      <h2>응답</h2>
      <div id="response_area"></div>
    </div>

    <script type='text/javascript' src="./ajax.js"></script>
  </body>
</html>```

````

**그럼에도 불구하고 위 코드처럼 수정하여도 작동을 하지 않는 경우가 있었는데 그런경우 3가지 경우를 볼 수 있었는데**<br>
**1. Button자체에 함수가 들어가지 않은 경우(document로 버튼을 아이디명으로 불러오지 못한경우)<br> 2. html에서 type설정이 제대로 안되어 있는 경우<br>3. html이 javascript를 제대로 불러오지 못한 경우.**<br>
**첫번째 기준으로는**

```
buttonElement.addEventListener('click', function (event) {
  alert('누름!');
});
```

**이 부분을 확인해야 하고**<br>
**두 번째 기준으로는 번째 방법은 확인결과 애초에 'script'로 html에 기입하여 파일을 넣어주면 기본값으로 javascript가 설정되어 있는 것을 확인했다.**<br>
**HTML5에서는**<br>
**script 엘리먼트의 type 디폴트가 text/javascript로 지정이 되기 때문에 선언을 해줄 필요가 없으며, 동일한 문장이라고 봐도 무방하다.**<br>
**유사하게 css도 지정이 되기 때문에 type="text/css" 를 지정해줄 필요가 없다.**<br>
**실제로 입력하여도 해결 되지는 않았다.**<br>
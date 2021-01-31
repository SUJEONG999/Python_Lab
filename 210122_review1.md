# 1월22일_1

## [실습1]

파일명 : exercise4.html
다음 자바스크립트로 기능을 구현해 본다.
**1부터 3까지의 랜덤값을 추출하여**
**1이면 다음**으로, **2이면 네이버**로, **3이면 구글로 이동**하는 기능을 구현해 본다.
단, 무조건 이동하는 것이 아니며 **사용자에게 확인 받는 서브 윈도우(힌트:window.confirm()) 를 출력**하여 **확인 버튼을 클릭하면 이동**하고 **취소 버튼이 클릭되면 first.html로 이동**한다.

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>

<script>
var n = (Math.floor(Math.random()*3)+1);
console.log(n);
if (window.confirm("페이지 이동하시겠어요?")) {
	    if (n==1)
            location.href = "http://www.daum.net/";
        else if (n==2)
            location.href = "https://www.naver.com/";
        else if (n==3)
            location.href = "https://www.google.co.kr/";
}
else {
	location.href = "http://localhost:8000/edu/first.html";
							  };
</script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>exercise4</title>
</head>
<body>
<script>
    var random = Math.floor(Math.random()*3+1);
    const first = "http://localhost:8000/edu/first.html"
    if(random == 1) {
        var d = confirm("다음으로 이동하시겠습니까?")
        if(d == true){
            location.href = "https://www.daum.net/";
        } else {
            location.href = first;
        }
    }
    if(random == 2) {
        var n = confirm("네이버로 이동하시겠습니까?")
        if(n == true){
            location.href = "https://www.naver.com/";
        } else {
            location.href = first;
        }
    }
    if(random == 3) {
        var n = confirm("구글로 이동하시겠습니까?")
        if(n == true){
            location.href = "https://www.google.com/";
        } else {
            location.href = first;
        }
    }
</script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<script>
var num = Math.floor(Math.random() * 3 + 1);
console.log(num)

if (num == 1){
    submit("다음");
}
if (num == 2){
    submit("네이버");
}
if (num == 3){
    submit("구글");
}

function submit(str){
    result = window.confirm(str+"페이지로 이동");
    if(result == false){
        location.href = "first.html";
    }
    if(result == true && str == "다음"){
        location.href = "https://www.daum.net/";
    }
    if(result == true && str == "네이버"){
        location.href = "https://www.naver.com/";
    }
    if(result == true && str == "구글"){
    	location.href = "https://www.google.com/";
    }
}

</script>
</body>
</html>
```

![image-20210131023226023](C:\Users\jinsujeong\AppData\Roaming\Typora\typora-user-images\image-20210131023226023.png)



## [실습2]

파일명 : exercise5.html

mbox 에서 exercise5.html 파일을 가져가서 다음에 제시된 기능을 자바스크립트로 구현해 본다.
브라우저에 출력된 버튼이 클릭되면
**선택된 버튼에 따라서 칼라를 적용**하여 제시된 `<h2>` 태그에 **"오늘은 XXXX년 X월 X일입니다."**
**문자열을 출력하도록 변경**하는 자바스크립트 코드를 완성하는데 **이벤트 핸들러 구현은 인라인 방식**으로 한다.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Insert title here</title>
    <style>
        button:nth-of-type(1) {
	color : red;
	font-size : 1.5em;
        }
        button:nth-of-type(2) {
	color : blue;
	font-size : 1.5em;
        }
        button:nth-of-type(3) {
	color : green;
	font-size : 1.5em;
        }
    </style>
</head>
<body>
    <button onclick="displayDate('red')">빨강색</button>
    <button onclick="displayDate('blue')">파랑색</button>
    <button onclick="displayDate('green')">녹&nbsp;&nbsp;색</button>
    <hr>
    <output id="target"></output>
    <script>
        var today = document.getElementsByTagName("output")[0];
        function displayDate(colorname) {
		    var now = new Date();
            var strnow = "오늘은 "+ now.getFullYear()+"년 " + (now.getMonth()+1)+"월 " + now.getDate()+"일입니다.";
            today.innerHTML = "<h2>"+ strnow +"</h2>";

            var targetDom = document.getElementById("target");
            console.log(targetDom);
            targetDom.textContent = strnow;
            targetDom.style.color = colorname;
        }
    </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Insert title here</title>
    <style>
        button:nth-of-type(1) {
	color : red;
	font-size : 1.5em;
        }
        button:nth-of-type(2) {
	color : blue;
	font-size : 1.5em;
        }
        button:nth-of-type(3) {
	color : green;
	font-size : 1.5em;
        }
    </style>
</head>
<body>
    <button onclick = "today('red')">빨강색</button>
    <button onclick = "today('blue')">파랑색</button>
    <button onclick = "today('green')">녹&nbsp;&nbsp;색</button>
    <hr>
    <h2></h2>

    <script>
	    function today(p) {
	        var d = new Date();
	        var year = d.getFullYear();
	        var month = d.getMonth()+1;
	        var day = d.getDate();
	        var target = document.querySelector("h2");
	        target.style.color = p;
	        target.textContent = "오늘은 "+year+"년 "+month+"월 "+day+"일입니다.";
	    }
    </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Insert title here</title>
    <style>
        button:nth-of-type(1) {
	color : red;
	font-size : 1.5em;
        }
        button:nth-of-type(2) {
	color : blue;
	font-size : 1.5em;
        }
        button:nth-of-type(3) {
	color : green;
	font-size : 1.5em;
        }
    </style>
</head>
<body>
    <button onclick="f1()">빨강색</button>
    <button onclick="f2()">파랑색</button>
    <button onclick="f3()">녹&nbsp;&nbsp;색</button>
    <hr>
    <h2></h2>

    <script>
        var target = document.getElementsByTagName("h2")[0];
        var date = new Date();
        var year = date.getFullYear();
        var month = date.getMonth()+1
        var day = date.getDate();
        var today = year+"년 "+month+"월 "+day;

        function f1() {
            target.style.color = 'red'
		    target.innerHTML = "<h2> 오늘은 "+today+"일입니다. </h2>";

		}

		function f2() {
		    target.style.color = 'blue'
		    target.innerHTML = "<h2> 오늘은 "+today+"일입니다. </h2>";
		}

		function f3() {
		    target.style.color = 'green'
		    target.innerHTML = "<h2> 오늘은 "+today+"일입니다. </h2>";
		}

    </script>
</body>
</html>
```

![image-20210131023137539](C:\Users\jinsujeong\AppData\Roaming\Typora\typora-user-images\image-20210131023137539.png)


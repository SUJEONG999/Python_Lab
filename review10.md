# 1월21일_1

파일명 : exercise1.html
1. 다음 값들을 저장하여 **배열을 생성**한다.
  10, 5, 7,21, 4, 8, 18

2. 모든 원소 값들을 더하여 다음 형식으로 **HTML 첫 번째 제목 크기(`<h1>`)로 출력**한다.(document.write())
**모든 원소의 합 : XX**

3. 최대값과 최소값을 구해서 **순서없는 리스트 형식(`<ul>`)으로 출력**한다.
  **- 최대값 : XX**

  **- 최소값 : XX** 

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<script>
var a1 = new Array(10,5,7,21,4,8,18);
var result = 0 ;
for(var i in a1)
    result += a1[i]
    document.write("<h1>모든 원소의 합 : "+result+"</h1>");
document.write("<ul>");
var max = Math.max.apply(null, a1);
document.write("<li>최대값 : "+max +"</li>");
var min = Math.min.apply(null, a1);
document.write("<li>최소값 : "+min +"</li>");
document.write("</ul>");
</script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>배열 실습</title>
</head>
<body>
    <script>
        var arr = new Array(10, 5, 7, 21, 4, 8, 18);
        var sum = 0;
        var max = 10;
        var min = 5;
        for(var i in arr)
        {
            sum += arr[i];
            if(max<arr[i])
                max = arr[i];
            if(min>arr[i])
                min = arr[i];
        }
        document.write("<h1>모든 원소의 합: "+sum+"</h1>");
        document.write("<ul>");
        document.write("<li>최대값: "+max+ "</li>");
        document.write("<li>최소값: "+min+ "</li>");
        document.write("</ul>");

    </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>배열 실습</title>
</head>
<body>
    <script>
        var arr = new Array(10, 5, 7, 21, 4, 8, 18);
        var sum = arr[0];
        var max = arr[0];
        var min = arr[0];
        for(var i=1; i < arr.length; i += 1)
        {
            sum += arr[i];
            if(max<arr[i])
                max = arr[i];
            if(min>arr[i])
                min = arr[i];
        }
        document.write("<h1>모든 원소의 합: "+sum+"</h1>");
        document.write("<ul>");
        document.write("<li>최대값: "+max+ "</li>");
        document.write("<li>최소값: "+min+ "</li>");
        document.write("</ul>");

    </script>
</body>
</html>
```

![image-20210131015408266](C:\Users\jinsujeong\AppData\Roaming\Typora\typora-user-images\image-20210131015408266.png)
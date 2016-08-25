---
layout: post
title: "초를 시:분:초로 변경해주는 함수"
date: 2016-07-17 07:00:00
image: '/assets/img/'
description: 'javascript'
main-class: 'javascript'
color: '#B31917'
tags:
- 
categories:
introduction: "자바스크립트(JavaScript)는 객체 기반의 스크립트 프로그래밍 언어이다. 이 언어는 웹브라우저 내에서 주로 사용하며, 다른 응용 프로그램의 내장 객체에도 접근할 수 있는 기능을 가지고 있다. 또한 Node.js와 같은 런타임 환경과 같이 서버 사이드 네트워크 프로그래밍에도 사용되고 있다."
---

초를 시:분:초로 변경해주는 function 
[javascript test page](http://www.w3schools.com/js/tryit.asp?filename=tryjs_inaccurate2).

{% highlight html %}

<!DOCTYPE html>
<html>
<body>

<p>초를 시 분 초로 변경</p>

<button onclick="test('1237')">Try it</button>

<p id="demo"></p>

<script>
function test(seconds) {

var hour = parseInt(seconds/3600);
var min = parseInt((seconds%3600)/60);
var sec = seconds%60;

document.getElementById("demo").innerHTML = hour+":"+min+":" + sec

}
</script>

</body>
</html>

{% endhighlight %}


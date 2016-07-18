---
layout: post
title: "javascript"
date: 2016-07-17 07:00:00
image: '/assets/img/'
description: 'javascript'
main-class: 'javascript'
color: '#B31917'
tags:
- 
categories:
introduction: "자바스크립트(JavaScript)는 객체 기반의 스크립트 프로그래밍 언어이다. 이 언어는 웹브라우저 내에서 주로 사용하며, 다른 응용 프로그램의 내장 객체에도 접근할 수 있는 기능을 가지고 있다. 또한 Node.js와 같은 런타임 환경과 같이 서버 사이드 네트워크 프로그래밍에도 사용되고 있다. 자바스크립트는 본래 넷스케이프 커뮤니케이션즈 코퍼레이션의 브렌던 에이크(Brendan Eich)가 처음에는 모카(Mocha)라는 이름으로, 나중에는 라이브스크립트(LiveScript)라는 이름으로 개발하였으며, 최종적으로 자바스크립트가 되었다. 자바스크립트가 썬 마이크로시스템즈의 자바와 구문(syntax)이 유사한 점도 있지만, 이는 사실 두 언어 모두 C 언어의 기본 구문을 바탕했기 때문이고, 자바와 자바스크립트는 직접적인 관련성이 없다. 이름과 구문 외에는 자바보다 셀프와 유사성이 많다"
---

초를 시간:분:초로 변경해주는 function 
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


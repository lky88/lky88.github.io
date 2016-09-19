---
layout: post
title: "linux iptables 설정 방법"
date: 2016-09-19 00:00:00
image: '/assets/img/'
description: 'linux 명령어'
main-class: 'linux'
color: '#B31917'
tags:
- 
categories:
introduction: "리눅스(Linux)는 컴퓨터 운영 체제의 하나이며, 그 커널을 뜻하기도 한다. 리눅스는 자유 소프트웨어와 오픈 소스 개발의 가장 유명한 표본으로 들 수 있다. 리눅스는 다중 사용자, 다중 작업(멀티태스킹), 다중 스레드를 지원하는 네트워크 운영 체제(NOS)이다."
---


#iptable 설치 방법
 
{% highlight ruby %}

yum -y install iptables
yum -y install iptables-service

{% endhighlight%}

#iptables service 설치 확인 방법

{% highlight ruby %}

rpm -qa | grep iptables

{% endhighlight %}

> 결과

![Imagem em um ipad](/assets/img/linux/iptables1.jpg)

#/etc/sysconfig 이동

{% highlight ruby %}

cd /etc/sysconfig

{% endhighlight%}

> 결과

![Imagem em um ipad](/assets/img/linux/iptables2.jpg)


#iptables 열기

{% highlight ruby %}

vi iptables

{% endhighlight%}

> 결과

![Imagem em um ipad](/assets/img/linux/iptables3.jpg)


{% highlight ruby %}

-A INPUT -p tcp --dport PORT -j ACCEPT

{% endhighlight%}

> EX) -A INPUT -p tcp --dport 1521 -j ACCEPT





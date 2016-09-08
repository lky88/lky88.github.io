---
layout: post
title: "java socket 통신 sample"
date: 2016-09-08 00:00:00
image: '/assets/img/'
description: 'java sample'
main-class: 'java'
color: '#B31917'
tags:
- 
categories:
introduction: "자바(영어: Java, 문화어: 쟈바)는 썬 마이크로시스템즈의 제임스 고슬링(James Gosling)과 다른 연구원들이 개발한 객체 지향적 프로그래밍 언어이며, 썬 마이크로시스템즈에서 무료로 제공하고 있다"
---

# 소켓 서버 Sample 코드 

> 소켓 서버 구동시 특정 포트를 사용하게 되므로 기존 다른 서버에서 사용되지 않는 포트로 설정
> Windows 포트 확인 방법

1. 윈도키+R
2. cmd
3. telent IP PORT

> 연결 대상 IP...호스트에 연결할 수 없습니다. 포트 5090: 연결하지 못했습니다. <br/>
> 위와 같은 메세지일 경우 5090 포트는 사용 가능한 포트입니다.

# Server Sample Code

{% highlight java %}
import java.io.IOException;
import java.io.PrintWriter;
import java.net.ServerSocket;
import java.net.Socket;
import java.util.Date;

public class SocketServerTEST {

  public static void main(String[] args) throws IOException {
    ServerSocket listener = new ServerSocket(5090);
    try {
        while (true) {
            Socket socket = listener.accept();
            try {
                PrintWriter out =
                    new PrintWriter(socket.getOutputStream(), true);
                out.println(new Date().toString());
            } finally {
                socket.close();
            }
        }
    }
    finally {
        listener.close();
    }
	
	} 
}
{% endhighlight %}


# Client Sample Code

{% highlight java %}
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.PrintWriter;
import java.net.Socket;

public class SocketClientTEST {
  
  public static void main(String[] args) throws Exception {
    
    Socket socket = new Socket("IP", 5090);
    
    PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
    
    out.write("hi");
    out.flush();
    
    BufferedReader input =
        new BufferedReader(new InputStreamReader(socket.getInputStream()));
    String returnMessage = input.readLine();
    System.out.println(returnMessage);
    
    input.close();
    socket.close();
    
  }
  
}
{% endhighlight %}
	



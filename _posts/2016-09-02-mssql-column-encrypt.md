---
layout: post
title: "Mssql 패스워드 암호화 PwdEncrypt"
date: 2016-09-02 00:00:00
image: '/assets/img/'
description: 'mssql sql'
main-class: 'mssql'
color: '#B31917'
tags:
- 
categories:
introduction: "마이크로소프트 SQL 서버(영어: Microsoft SQL Server)는 마이크로소프트가 1989년 사이베이스(Sybase)를 기반으로 개발한 관계형 데이터베이스이다."
---

# MSSQL 패스워드 암호화 함수

{% highlight sql %}

SELECT PwdEncrypt('데이터') as PWDEncrypt;

{% endhighlight %}

# MSSQL 패스워드 복호화 함수

{% highlight sql %}

SELECT PwdCompare('데이터', 컬럼명) as PwdCompare;

{% endhighlight %}

# 샘플 코드

{% highlight sql %}

--테이블 생성
CREATE TABLE TEST_USER ( id varchar(30), password varbinary(max));

--데이터 입력
INSERT INTO test_user VALUES ( 'lee', PwdEncrypt('1234') );
INSERT INTO test_user VALUES ( 'eum', PwdEncrypt('password') );

--데이터 조회
SELECT id, PWDCompare('1234', password ) as PWDCompare
FROM test_user

{% endhighlight %}

> 데이터 조회 화면<br/>
> PWDCompare -> 1 경우 일치 <br/>
> PWDCompare -> 0 경우 틀림
	



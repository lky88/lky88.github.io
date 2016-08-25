---
layout: post
title: "MSSQL 버전 확인 방법 "
date: 2016-07-18 07:00:00
image: '/assets/img/'
description: 'mssql 명령어'
main-class: 'mssql'
color: '#B31917'
tags:
- 
categories:
introduction: "마이크로소프트 SQL 서버(영어: Microsoft SQL Server)는 마이크로소프트가 1989년 사이베이스(Sybase)를 기반으로 개발한 관계형 데이터베이스이다."
---

MSSQL 버전 확인 쿼리

{% highlight sql %}

SELECT CAST(SERVERPROPERTY('productversion') AS VARCHAR) + ' - '
+ CAST(SERVERPROPERTY('productlevel') AS VARCHAR) + ' ('
+ CAST(SERVERPROPERTY('edition') AS VARCHAR) + ')' as version

{% endhighlight %}

<table style="width: 800px">
<tbody><tr>
<th></th>
<th>RTM (no SP)</th>
<th>SP1</th>
<th>SP2</th>
<th>SP3</th>
<th>SP4</th>
</tr><tr>
</tr><tr>

<td rowspan="4">SQL Server 2016</td>
<td rowspan="2">13.0.1601.5</td>
<td></td>
<td></td>
<td></td>
<td></td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4">SQL Server 2014</td>
<td rowspan="2">12.0.2000.8</td>
<td>12.0.4100.1<br/>
or 12.1.4100.1</td>
<td>12.0.5000.0<br/>
or 12.2.5000.0</td>
<td></td>
<td></td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4"> SQL Server 2012</td>
<td rowspan="2">11.0.2100.60</td>
<td>11.0.3000.0<br/>
or 11.1.3000.0</td>
<td>11.0.5058.0<br/>
or 11.2.5058.0</td>
<td>11.0.6020.0<br/>
or 11.3.6020.0</td>
<td></td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4"> SQL Server 2008 R2</td>
<td rowspan="2">10.50.1600.1</td>
<td>10.50.2500.0<br/>
or 10.51.2500.0</td>
<td>10.50.4000.0<br/>
or 10.52.4000.0</td>
<td>10.50.6000.34<br/>
or 10.53.6000.34</td>
<td></td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4"> SQL Server 2008</td>
<td rowspan="2">10.0.1600.22</td>
<td>10.0.2531.0<br/>
or 10.1.2531.0</td>
<td>10.0.4000.0<br/>
or 10.2.4000.0</td>
<td>10.0.5500.0<br/>
or 10.3.5500.0</td>
<td>10.0.6000.29<br/>
or 10.4.6000.29</td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4"> SQL Server 2005</td>
<td rowspan="2">9.0.1399.06</td>
<td>9.0.2047</td>
<td>9.0.3042</td>
<td>9.0.4035</td>
<td>9.0.5000</td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4"> SQL Server 2000</td>
<td rowspan="2">8.0.194</td>
<td>8.0.384</td>
<td>8.0.532</td>
<td>8.0.760</td>
<td>8.0.2039</td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>

<td rowspan="4">SQL Server 7.0</td>
<td rowspan="2">7.0.623</td>
<td>7.0.699</td>
<td>7.0.842</td>
<td>7.0.961</td>
<td>7.0.1063</td>

<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>
<tr></tr>



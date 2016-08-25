---
layout: post
title: "UTC시간을 로컬시간으로 변경하는 함수"
date: 2016-07-18 06:00:00
image: '/assets/img/'
description: 'mssql 명령어'
main-class: 'mssql'
color: '#2c50f5'
tags:
- 
categories:
introduction: "마이크로소프트 SQL 서버(영어: Microsoft SQL Server)는 마이크로소프트가 1989년 사이베이스(Sybase)를 기반으로 개발한 관계형 데이터베이스이다."
---

UTC시간을 로컬 시간으로 변경해주는 함수

{% highlight sql %}
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

create function [dbo]. [utctolocaltime] ( @times int )
returns datetime
as
begin
declare @ret datetime
declare @offset bigint, @localdate bigint;
    set @offset = datediff(second ,getdate(), getutcdate());
    set @localdate = @times - @offset;
select @ret = dateadd(second , @localdate , '1970/01/01 00:00:00' )
return @ret
end

GO
{% endhighlight %}


 함수 호출 방법:

> 파라미터 타입 -> int(UTC 시간) <br/>



{% highlight sql %}
	select dbo.utctolocaltime(1457241219) as localtime;
{% endhighlight %}



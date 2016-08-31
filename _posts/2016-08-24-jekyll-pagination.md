---
layout: post
title: "jekyll pagination 방법"
date: 2016-07-19 07:00:00
image: '/assets/img/'
description: 'jekyll'
main-class: 'jekyll'
color: '#e3908f'
tags:
- 
categories:
introduction: "Jekyll is a simple, blog-aware, static site generator for personal, project, or organization sites. Written in Ruby by Tom Preston-Werner, GitHub's co-founder, it is distributed under an open source license"
---




# 1. jekyll의 pagination을 사용 하기 위해서는 jekyll-pagination을 설치 작업이 필요합니다.

{% highlight ruby %}
gem install jekyll-pagination
{% endhighlight %}

# 2. _config.yml 파일 수정:

> paginate: 2 <br/>
> paginate_path: "/blog/page:num/"

# 3. index.html 파일 수정

아래와 같이 수정할 경우 paginate의 값만큼 포스트가 표시됩니다.

as-is : 

> site.posts을 변경 <br/>

{% highlight liquid %}

{%raw%}
{% for post in site.posts %}
{% endfor %}
{%endraw%}

{% endhighlight %}


to-be : 

> paginator.posts으로 변경

{% highlight liquid %}

{%raw%}
{% for post in paginator.posts %}
{% endfor %}
{%endraw%}

{% endhighlight %}

add :

> endfor 하단에 추가

{% highlight liquid %}
{%raw%}

{% if paginator.total_pages > 1 %}  
  	<div class="pagination">
  {% if paginator.previous_page %}  
    <a class="cusInnerPage" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a>  
  {% else %}  
    <span class="cusInnerPage">&laquo; Prev</span>  
  {% endif %}  
  
  {% for page in (1..paginator.total_pages) %}  
    {% if page == paginator.page %}  
      <em class="cusInnerPage">{{ page }}</em>  
    {% elsif page == 1 %}  
      <a class="cusInnerPage" href="/">{{ page }}</a>  
    {% else %}  
      <a class="cusInnerPage" href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>  
    {% endif %}  
  {% endfor %}  
  
  {% if paginator.next_page %}  
    <a class="cusInnerPage" href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a>  
  {% else %}  
    <span class="cusInnerPage" >Next &raquo;</span>  
  {% endif %}  
</div> 
{% endif %}

{%endraw%}

{% endhighlight %}


# 4. CSS 추가

{% highlight css %}
.pagination{
	text-align : center;
}
.cusInnerPage{
	border : 1px solid #dddddd;
	padding : 4px 12px;
	margin : -2px;
	text-decoration : none;
	font-style : normal;
}
a.cusInnerPage:hover{
	background : #f5f5f5;
}
a.cusInnerPage:visited{
	color : #0088cc;
}
{% endhighlight %}









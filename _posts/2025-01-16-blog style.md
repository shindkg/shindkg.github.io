---
layout: post
title:  "[깃허브 블로그] 4. Chirpy Theme 디자인 바꾸기"
date:   2025-01-16 16:30:00 +0900
categories: [깃허브블로그, 블로그꾸미기]
tags: [blog, chirpy, scss, css, html]
---

기본 테마 디자인도 좋지만 내 스타일대로 꾸미려고 scss 파일을 고쳐봤다.

## 💡 아카이브 디자인 바꾸기
사이드바에 있는 메뉴 중 아카이브 디자인을 바꿨다.  
글꼴이 바뀌어서 그런가? 원의 위치도 틀어져서 다시 바꿔준다. 아래처럼 '일/월' 형식도 '월.일' 형식으로 바꿨다. 

```scss
    // 수정 전
    left: 21.5px; 
    // 수정 후
    left: 16px;
```
{: file='_sass\pages\_archives.scss'}

```html
    <!-- 수정 전 -->
    ... | default: '/ %m' %}
    <!-- 수정 후 -->
    ... | default: '%m.' %}
```
{: file='_layouts\archives.html'}

![아카이브 디자인 수정](/assets/img/post/post-blog-style-archive.png){: .normal  }

## 💡 홈 & 관련된 글 디자인 바꾸기
사이드바에 있는 메뉴 중 홈 hover 디자인을 바꿨다. 자동으로 포스팅 글 하단 관련된 글 디자인까지 같이 바뀐다.  
`opacity: 0.3;` 으로 되어있는 것을 `background-color`로 바꿨다.

```scss
    // 수정 전
    &::before {
      opacity: 0.3;
    }
    // 수정 후
    background-color: var(--sidebar-border-color);
```
{: file='_sass\base\_base.scss'}

![홈 디자인 수정](/assets/img/post/post-blog-style-home.png){: .normal  }


나중에 또 수정하고 싶은 디자인이 보이면 틈틈히 바꿔야겠다.  
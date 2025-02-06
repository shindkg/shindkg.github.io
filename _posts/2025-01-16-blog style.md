---
layout: post
title:  "[깃허브 블로그] 4. Chirpy Theme 디자인 바꾸기"
date:   2025-01-16 16:30:00 +0900
categories: [깃허브블로그, 블로그꾸미기]
tags: [blog, chirpy theme, scss, css, html]
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

## 💡 포스팅 하단 이전 글/다음 글 hover 바꾸기
기존 포스팅 하단 이전 글/다음 글 마우스 오버 배경 색상이 쨍한 파란색이다. 또 내 마음대로 색을 바꾼다.
파비콘이랑 포스팅에 자주 쓰는 전구아이콘에 노란색이 들어가니까 노란색으로 바꿔야지!

```scss
    // 추가
    --summary-bg-color: #fffdf0;
    --summary-border-color: #fff2c2;
```
{: file='_sass\base\_light.scss'}

```scss
.btn.btn-outline-primary {
  &:hover {
    // 추가
    background-color: var(--summary-bg-color);
    border-color: var(--summary-border-color);
  }
}
```
{: file='_sass\base\_base.scss'}

![이전 글/다음 글 마우스오버](/assets/img/post/post-blog-style-posted-hover.png){: .normal  }

## 💡 본문 인라인 코드 스타일 바꾸기
포스팅한 글 본문에 인라인 코드를 적었는데 폰트 사이즈가 다른 글에 비해 작아보이기도 하고 배경색이 잘 안보이는 것 같아서 아주 살짝 더 진하게 바꿨다.
```scss
    // 삭제
    font-size: v.$code-font-size;
    // 추가
    letter-spacing: -0.02rem;
```
{: file='_sass\base\_syntax.scss'}
```scss
    // 수정 전
    --inline-code-bg: rgba(25, 25, 28, 0.05);
    // 수정 후
    --inline-code-bg: rgba(25, 25, 28, 0.08);
```
{: file='_sass\base\_light.scss'}


![인라인 코드 스타일 바꾸기](/assets/img/post/post-blog-style-inline-code.png){: .normal  }


나중에 포스팅 하다가 또 수정하고 싶은 디자인이 보이면 틈틈히 바꿔야겠다!
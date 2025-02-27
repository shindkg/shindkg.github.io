---
layout: post
title:  "[퍼블리싱] 이러닝 관련 웹페이지 퍼블리싱"
date:   2025-02-24 11:00:00 +0900
categories: [publishing, HTML CSS]
tags: [publishing, html, css]
---

지인의 소개로 퍼블리싱을 할 일이 생겼다. PPT 파일로 받은 기획서를 참고하여 HTML과 CSS로 퍼블리싱을 하였다.  
이러닝 관련 웹페이지에서 테이블 형태로 퍼블리싱 했던 내용을 정리했다.  

## 💡 1. HTML 구조 잡기

HTML 구조를 잡아야 해서 고민하다가 중간에 스크롤이 들어갈 부분을 보고 div 안에 table 태그를 사용했다.  

우선 전체 표를 div 태그로 감싸고, 표의 헤더 부분과 스크롤 할 내용이 있는 부분으로 나눴다. 표 안에 행이 한 줄로 합쳐진 부분은 colspan을 사용하고, 체크박스가 있는 행은 tr 태그를 썼다.  

```html
<div class="전체_표">
    <div class="표의_헤더_부분">...</div>
    <div class="스크롤_할_내용이_있는_부분"> 
        <table class="테이블_태그_스타일">
            <tr class="표_안에_행이_한_줄로_합쳐진_부분">
                <td colspan="3">
                    ...
                </td>
            </tr>
            <tr class="표_안에_행이_셀로_나뉜_있는_부분">
                <td>...<td>
                <td>...<td>
                <td>...<td>
            </tr>
            ...
        </table>
    </div>
</div>
```



## 💡 2. CSS로 디자인 하기
표의 헤더 부분을 제외한 나머지에 있는 내용에 세로로 스크롤이 있어야 한다.  
그래서 table 태그 바로 상위 태그인 div에 일정 height와 overflow-y: scroll을 넣고 흰색 배경을 넣어준다.  
그리고 table 태그에는 table-layout: auto; width: 100%; 을 넣어준다! 이렇게 하면 전체 테이블 너비를 100%로 하고 표 안의 셀 간격을 원하는 간격으로 조절할 때 편하다.  

```css
.스크롤_할_내용이_있는_부분 {
    height: 200px; 
    overflow-y: scroll; 
    background-color: #fff;
}
.테이블_태그_스타일 {
    table-layout: auto; 
    width: 100%;
}
```

## 💡 3. 스크롤이 있는 표 완성하기

구조를 잡은 HTML에서 표 안의 내용을 채워주고, CSS에서 간격을 조절하고 색상을 적절히 넣어주면 아래 이미지처럼 완성된다!

![표 작업 퍼블리싱 이미지](/assets/img/post/post-publish-01.png){: .normal  }
_스크롤 하기 전 이미지_

  
![스크롤 내렸을 때 표 작업 퍼블리싱 이미지](/assets/img/post/post-publish-02.png){: .normal  }
_스크롤 내렸을 때 이미지_
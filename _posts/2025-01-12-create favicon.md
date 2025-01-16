---
layout: post
title:  "[깃허브 블로그] 2. Favicon 만들기"
date:   2025-01-12 15:35:00 +0900
categories: [깃허브블로그, 블로그생성하기]
tags: [blog, theme, chirpy, favicon]
image:
  path: /assets/img/post/post-create-favicon.png
  alt: favicon 예시
---

## 💡 1. Favicon이란?

Favicon(파비콘)은 웹사이트의 아이콘을 의미한다. 보통 웹 브라우저의 탭, 북마크, 즐겨찾기 목록에 작은 이미지로 표시된다. 파비콘은 웹사이트의 아이덴티티를 시각적으로 표현하는 데 도움을 주며, 사용자가 여러 탭을 열었을 때 사이트를 쉽게 식별할 수 있도록 도와준다.


## 💡 2. Favicon 만들기

favicon을 만들기 위해 그림판을 열었다. 아래 이미지처럼 내맘대로 귀여운 꽃을 그렸다.  
![favicon 그리기 이미지 예시](/assets/img/post/post-create-favicon.png){: .normal  }

이번에도 Chirpy Theme Live Demo에서 확인할 수 있다. 아래 Favicon Generator 링크로 들어간다.
- <https://chirpy.cotes.page/posts/customize-the-favicon>
  - <https://realfavicongenerator.net/>

생성된 패키지를 다운로드하고 압축을 풀고 추출된 파일에서 다음 두 가지를 삭제한다. ~~난 삭제 안하고 기존 테마에 있던 걸로 그냥 뒀다.~~
- browserconfig.xml
- site.webmanifest

Favicon Generator로 생성된 파일을 기존 /assets/img/favicons 에 있는 파일에 덮어쓴다.
![favicons 파일들](/assets/img/post/post-create-favicons-ex.png){: .normal  }


## 💡 3. Favicon 적용하기

git commit & push 후 잘 적용됐는지 확인한다. Favicon(파비콘) 적용 완료!  
![shindkg 블로그에 favicon 적용](/assets/img/post/post-create-favicons-applied.png){: .normal  }

---
정리
: 1. Favicon 만들기
2. Favicon Generator로 Favicon(파비콘) 변환하기
3. Favicon(파비콘) 적용하기

---

---
layout: post
title:  "[깃허브 블로그] 1. Github 블로그에 Jekyll Chirpy 테마 적용 후 실행하기"
date:   2025-01-10 10:10:00 +0900
categories: [깃허브블로그, 블로그생성하기]
tags: [blog, jekyll theme, chirpy theme]
---

## 💡 1. 깃허브 블로그 만들기

시간이 지나면 금방 잊어버리니 기록용+참고용 블로그를 만들어 볼까 해서 시작했다.     

네이버 블로그, 티스토리 등 많지만 github 블로그를 선택했다.  
블로그 테마 선택 폭도 자유롭고 내 취향대로 블로그를 꾸밀 수 있다는 장점이 있기 때문이다.    
그리고 포스팅 전에 글이 어떻게 보이는지 로컬에서 한 번 확인 후 올릴 수도 있다!  

깃허브 블로그에서 테마를 골라야 하는데 아래 Jekyll Theme - pick up a theme 링크에서 원하는 템플릿을 골라본다.
- Jekyll Theme - <https://jekyllrb.com/docs/themes/#pick-up-a-theme>   
    - <https://github.com/topics/jekyll-theme>
    - <https://jamstackthemes.dev/ssg/jekyll/>


## 💡 2. 블로그 테마 고르기
    
테마 종류가 너무 많아서 고민하다가 무료 깃허브 블로그 테마로 많이 보이고, 깔끔하기도 한 chirpy 테마로 골랐다.  
- Jekyll Theme - Chirpy    
  - <https://github.com/cotes2020/jekyll-theme-chirpy>

Chirpy Theme의 Live Demo 페이지에 들어간다.   
- Chirpy Theme Live Demo    
  - <https://chirpy.cotes.page/posts/getting-started/>

## 💡 3. 블로그에 Chirpy Theme 적용하기

친절한 getting started 페이지를 보며 따라했다.  
GitHub에 로그인 후 테마 저장소를 fork 후 새 저장소 이름을 username.github.io로 설정한다.   
(username은 GitHub 사용자인 내 아이디로 바꾸기!)    

기존 fork 할 때 브랜치 이름이 master라 브랜치 이름을 main으로 바꿔줬다. ~~인종차별적 의미를 피하기 위한 노력의 일환으로..~~

Chirpy Theme 기준으로 그 다음 `tools/init.sh`을 루트 디렉토리에서 실행하여 저장소를 초기화한다.
```terminal
$ tools/init.sh
```

실행하면 (2025년 1월 9일 기준으로) 'chore: initialize the environment' 커밋 메시지와 함께 파일을 알아서 정리해준다. 수정이 된 파일은 .gitignore, _config.yml, 삭제가 된 파일은 .github, _posts, tools 폴더 안에 있고, 추가가 된 파일은 _sass, assets/js/dist에 있다!  


이제 Jekyll theme 블로그를 실행해본다.  
- <https://chirpy.cotes.page/posts/getting-started/#usage>  

로컬 서버를 http://127.0.0.1:4000 에서 확인할 수 있다!

```terminal
$ bundle exec jekyll s
```

---
📄 정리
: 1. 깃허브 블로그 Chirpy 테마 fork 하기
2. tools/init.sh 실행하여 초기화
3. bundle exec jekyll serve로 실행하기

---

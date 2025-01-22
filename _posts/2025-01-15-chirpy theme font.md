---
layout: post
title:  "[깃허브 블로그] 3. Chirpy Theme에서 글꼴 변경하기"
date:   2025-01-15 17:16:00 +0900
categories: [깃허브블로그, 블로그꾸미기]
tags: [blog, chirpy theme, font, scss]
---

기존 Chirpy Theme이 영어 기반이라 그런지 한국어 폰트가 뭔가 어색해보였다. 그래서 폰트를 바꾸고 싶었다. 다른 테마는 어떻게 바꿀지 모르겠지만 Chirpy Theme 기준으로 바꾸는 방법을 정리했다. 


## 💡 1. 원하는 폰트 찾기

폰트를 다운로드 받기 위해 인터넷에 구글 폰트를 검색한다. 구글 폰트에 있는 대부분의 폰트는 저작권 걱정할 필요가 없어서 활용하기 좋다.  

> 구글 폰트란? 대부분 오픈 소스로 제공되며, 대부분의 글꼴은 자유롭게 사용할 수 있다. 그러나 글꼴에 따라 저작권과 라이선스 조건이 다를 수 있으므로, 사용하기 전에 각 글꼴의 라이선스를 확인하는 것이 중요하다.
{: .prompt-info }

아래 구글 폰트 링크로 들어가서 원하는 폰트를 고른다.  
- Google Fonts    
  - <https://fonts.google.com/>

무난한 Noto Sans Korean을 다운로드 했다. 지금(2025년 1월)은 예전과 UI가 달라져서 우측 Get font 버튼을 누르고 Download all 버튼을 눌러서 다운로드 한다. 


## 💡 2. Chirpy Theme 폰트 바꾸기

아래 친절한 Chirpy Theme 링크에 새로운 폰트를 적용하는 방법이 잘 나와있다. 우선 chirpy-static-assets을 Fork한다.

- Static Assets for Chirpy Jekyll Theme
  - <https://github.com/cotes2020/chirpy-static-assets?tab=readme-ov-file#usage>

jekyll-theme-chirpy의 _config.yml 에서 `enabled: true`로 바꾼다.

```yml
assets:
  self_host:
    enabled: true # boolean, keep empty means false
```
{: file='_config.yml'}

pages-deploy.yml 에서 기존 주석 처리된 `submodules: true` 라인의 주석을 풀어준다.  

```yml
steps:
  with:
    submodules: true
```
{: file='.github\workflows\pages-deploy.yml'}

아까 Fork한 chirpy-static-assets에 다운 받은 폰트를 커밋한다.
jekyll-theme-chirpy의 .gitmodules 파일의 url을 fork한 repository로 바꾼다.

```yml
[submodule "assets/lib"]
    path = assets/lib
    url = https://github.com/shindkg/chirpy-static-assets.git
```
{: file='.gitmodules'}

## 💡 3. Chirpy Theme 폰트 적용하기

scss 파일에서 font-family를 다운 받은 폰트로 바꿔준다.

```scss
$font-family-base: 'Noto Sans KR', ...
$font-family-heading: 'Noto Sans KR', ...
```
{: file='_sass\abstracts\_variables.scss'}

잘 적용됐는지 확인한다. 바뀐 폰트가 마음에 든다!  
![shindkg 블로그에 새로운 font 적용](/assets/img/post/post-chirpy-theme-font.png){: .normal  }




---
📄 정리
: 1. 원하는 폰트 찾기
2. 폰트 바꾸기(참고: Static Assets for Chirpy Jekyll Theme)
3. 폰트 적용된 것 확인하기 

---

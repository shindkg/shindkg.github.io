---
layout: post
title:  "Git 계정 정보 바꾸기"
date:   2025-02-06 14:00:00 +0900
categories: [git, 계정 정보]
tags: [git, git config, unset]
---


## 💡 1. git 계정 정보 바꾸기
새로운 git 계정으로 로그인 하고 커밋하려니까 오류가 나서 초기화했다.

```bash
# 1.local
$ git config --local --unset credential.helper  

# 2.global
$ git config --global --unset credential.helper 

# 3.system 
$ git config --system --unset credential.helper
```

앞으로는 이 아이디 위주로 사용할 것 같아서 3번 시스템까지 초기화 하고 다시 사용자 아이디랑 이메일을 global로 세팅한다.

```bash
$ git config --global user.name "아이디"
$ git config --global user.email "이메일"
```

## 💡 2. git 계정 정보 확인하기
`git config --list`로 설정한 내용을 확인해보면 아래 내용처럼 바뀐 아이디와 이메일로 설정된 걸 확인할 수 있다!

```bash
user.name=아이디
user.email=이메일
```


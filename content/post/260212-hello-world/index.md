---
title: Let's go hugo
description: Welcome to Hugo Theme Stack
slug: Let's go hugo
date: 2026-02-12 07:58:00+0900
draft: false
categories:
    - Hugo
tags:
    - stack
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---
### 오늘부터 Github 블로그를 시작
최근에 티스토리에서 정책이 계속 바뀌는 상황이 일어났었습니다.  
다음 블로그도 그런 일이 있었다가 사라졌다는 말을 듣게 되어서,  
이 참에 어느 플랫폼에 종속되지 않고 내 맘대로 글을 올릴 수 잇는 곳을 만들고 싶어졌습니다.

프론트엔드를 잘하는 개발자가 아니고, 그렇다고 ai로 다 밀어버리면 유지보수는 답이 없어질테니  
Hugo라는 가이드 툴을 이용해서 블로그 작업을 진행할 예정입니다.

https://stack.jimmycai.com/  
Hugo에서 stack이라는 테마에 관한 링크입니다.  

```bash
#정적 파일 빌드
#-public/ 폴더 생성
#-GitHub Pages / 배포용 결과물 생성
#-GitHub Actions 쓰면 보통 여기서 자동으로 실행됨
hugo
#HTML/CSS/JS 압축 (배포용) - 옵션 버전
hugo --minify

#로컬 서버 실행
hugo server
#로컬 서버 draft 글도 같이보면서 실행
hugo server -D

#새글 생성 (post)
hugo new post/파일명_날짜.md
```
# dldl8819.github.io

개인 기술 블로그 겸 포트폴리오. [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 테마 기반 Jekyll 사이트.

- 사이트: https://dldl8819.github.io
- 콘텐츠: 프로젝트 정리, 기술 글 (일과 기록은 [네이버 블로그](https://blog.naver.com/dldl8819/)에 따로 씁니다)

## 로컬 실행 (Ruby/Bundler 필요)

```bash
bundle install
bundle exec jekyll serve
```

## 새 글 작성

`_posts/YYYY-MM-DD-제목.md` 형식으로 파일을 만들고 아래 front matter를 채운다.

```yaml
---
title: 제목
date: YYYY-MM-DD HH:MM:SS +0900
categories: [카테고리1, 카테고리2]
tags: [태그1, 태그2]
---
```

## TODO

- [ ] `_config.yml`의 title/tagline/description/social.name 채우기
- [ ] `assets/img/`에 프로필 사진(avatar) 추가 후 `_config.yml`의 `avatar:` 연결
- [ ] GitHub Pages 배포 설정 (Settings → Pages → Source: GitHub Actions)
- [ ] 글이 어느 정도 쌓이면 AdSense 신청 (`ads.txt` 필요)

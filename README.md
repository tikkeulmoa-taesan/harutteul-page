# 하루뜰 페이지

안드로이드 앱 **[하루뜰](https://play.google.com/store/apps/details?id=kr.co.harutteul)** 의 소개 페이지와 개인정보처리방침입니다.
빌드 도구 없는 정적 HTML이며, GitHub Pages로 서비스합니다.

- 소개 페이지: https://tikkeulmoa-taesan.github.io/harutteul-page/
- 개인정보처리방침: https://tikkeulmoa-taesan.github.io/harutteul-page/privacy/

## 구성

| 파일 | 내용 |
|---|---|
| `index.html` | 랜딩 페이지. 스크린샷·로고·런타임이 base64로 들어간 단일 번들 파일 (약 600KB) |
| `privacy/index.html` | 개인정보처리방침. 스타일까지 포함된 평범한 HTML |

## 로컬에서 보기

파일을 브라우저로 바로 열면 됩니다. 이미지가 blob URL로 풀리도록 만들어져 있어 `file://` 에서도 정상 동작합니다.

```bash
start index.html
```

## 배포

`main` 에 push 하면 GitHub Pages가 자동으로 반영합니다 (경로 `/`, 별도 워크플로 없음).

## index.html 수정 시

번들 결과물이라 손으로 고치는 파일이 아닙니다. 실제 마크업은 `<script type="__bundler/template">` 안에 **JSON 문자열 한 줄**로 들어 있고, `src` 값은 UUID라 페이지가 로드될 때 base64 자산의 blob URL로 치환됩니다.

- 디자인·스크린샷 변경: 원본 캔버스에서 다시 내보내 `index.html` 을 통째로 교체
- 문구·링크 정도의 소소한 수정: 템플릿 JSON 문자열 안에서 고치되 따옴표 이스케이프(`\"`)를 지킬 것

`privacy/index.html` 은 일반 HTML이므로 그냥 편집하면 됩니다.

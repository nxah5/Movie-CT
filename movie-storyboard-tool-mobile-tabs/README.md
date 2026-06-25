# 영화 콘티 제작 툴

브라우저에서 바로 실행되는 단일 HTML 기반 영화 콘티 제작 툴입니다. 입력 영역에서 컷별 이미지, 텍스트, 오디오, 기타 내용을 작성하면 A4 출력 미리보기에 자동 반영됩니다.

## 주요 기능

- A4 세로 / 가로 레이아웃 전환
- 세로 페이지당 5컷, 가로 페이지당 3컷 자동 배치
- 페이지 추가 / 페이지 삭제
- 장면 이미지는 16:9 비율 프레임 안에 자동 맞춤
- 컷 / 텍스트 / 오디오 / 기타 텍스트 중앙 정렬
- 모바일 화면에서는 `입력 시트` / `출력 시트` 탭으로 분리 표시
- 모바일 상단 고정 툴바에서 페이지 추가 / 페이지 삭제 가능
- PDF 저장 및 인쇄 지원
- 외부 라이브러리 없이 `index.html` 하나로 실행

## GitHub Pages 배포

1. 이 폴더의 파일을 GitHub 저장소에 업로드합니다.
2. 저장소의 `Settings` > `Pages`로 이동합니다.
3. `Build and deployment`에서 `Deploy from a branch`를 선택합니다.
4. 브랜치는 `main`, 폴더는 `/root`를 선택합니다.
5. 저장 후 생성되는 GitHub Pages 주소로 접속합니다.

## Docker 배포

Docker 기반 배포 서비스에서는 저장소 루트에 `Dockerfile`이 있어야 합니다. 이 폴더 안의 파일들을 저장소 루트에 업로드하면 아래 Dockerfile이 자동으로 사용됩니다. Docker 배포에는 `index.html`과 `Dockerfile`만 있어도 실행됩니다.

```bash
docker build -t movie-storyboard-tool .
docker run -p 8080:80 movie-storyboard-tool
```

## 파일 구성

- `index.html`: 실제 콘티 제작 툴
- `.nojekyll`: GitHub Pages 정적 배포용 설정 파일
- `Dockerfile`: Docker/nginx 정적 사이트 배포용 설정
- `.dockerignore`: Docker 빌드 제외 파일 설정

## 참고

이 툴은 별도 서버나 데이터베이스 없이 브라우저에서 동작합니다. 작성한 내용은 현재 브라우저 화면 안에서만 유지되므로, 최종본은 PDF로 저장하거나 인쇄해서 보관하세요.

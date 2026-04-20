# slides/

본 위키/프로젝트를 소개하는 슬라이드 데크.

## 파일

| 파일 | 설명 | 분량 |
|---|---|---|
| [`llm-wiki-overview.md`](llm-wiki-overview.md) | LLM 전용 위키 구축 방법과 구성 내용(재료·결과물) 종합 소개 | 25 슬라이드 |

## 렌더링 방법

### 1. Obsidian + Marp Slides 플러그인

1. [Obsidian Marp Slides](https://samuele-cozzi.github.io/obsidian-marp-slides/) 플러그인 설치
2. Obsidian으로 본 저장소를 열고 `slides/llm-wiki-overview.md` 열기
3. 커맨드 팔레트 → **Marp: Start Presentation**

### 2. Marp CLI

```bash
# 설치
npm install -g @marp-team/marp-cli

# HTML로 변환 (기본)
marp slides/llm-wiki-overview.md -o slides/llm-wiki-overview.html

# PDF로 변환 (Chrome/Chromium 필요)
marp slides/llm-wiki-overview.md --pdf -o slides/llm-wiki-overview.pdf

# PPTX로 변환
marp slides/llm-wiki-overview.md --pptx -o slides/llm-wiki-overview.pptx

# 라이브 서버 (변경 즉시 반영)
marp --server slides/
```

### 3. VS Code + Marp for VS Code

1. 확장 `marp-team.marp-vscode` 설치
2. `slides/llm-wiki-overview.md` 열면 우측 상단에 미리보기 버튼 등장

## 규약

- 슬라이드는 본 위키([`../wiki/`](../wiki/))의 콘텐츠만 참조한다 (새 사실을 만들지 않음).
- 새 슬라이드 데크를 추가하면 본 README 표에 등록한다.
- 슬라이드 수정 시 근거가 된 위키 페이지를 각주/링크로 남긴다.

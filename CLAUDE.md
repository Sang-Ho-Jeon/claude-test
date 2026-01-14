# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

재미있는 한국어 명언을 표시하는 정적 웹 애플리케이션입니다. 빌드 도구나 서버 없이 브라우저에서 바로 실행됩니다.

## 실행 방법

웹 브라우저에서 `index.html` 파일을 직접 열면 됩니다. 빌드 단계나 종속성 설치가 필요 없습니다.

## 아키텍처

**단일 파일 구조** - 모든 코드가 `index.html` 하나에 포함됨:
- HTML 구조 (1-272줄)
- Tailwind CSS 설정 및 커스텀 스타일 (12-112줄)
- JavaScript 애플리케이션 로직 (273-634줄)

**기술 스택**:
- Tailwind CSS (CDN)
- Noto Sans KR 웹폰트 (Google Fonts)
- 순수 JavaScript (프레임워크 없음)
- LocalStorage (데이터 저장)

## 주요 코드 위치

| 영역 | 줄 번호 | 설명 |
|------|---------|------|
| Tailwind 설정 | 12-48 | 커스텀 애니메이션, 폰트 정의 |
| 커스텀 CSS | 50-112 | 그라데이션 배경, 글래스모피즘, 다크모드 |
| 명언 데이터 | 275-333 | `quotes` 배열 (5개 카테고리, 48개 명언) |
| 상태 관리 | 335-341 | 앱 상태 변수들 |
| 핵심 함수들 | 364-630 | 이벤트 핸들러, UI 업데이트 로직 |

## 콘텐츠 수정 방법

**명언 추가/수정**: `quotes` 배열 (275-333줄)
```javascript
{ text: "명언 내용", author: "작성자", category: "life", emoji: "😴" }
```

**카테고리 종류**: `life`, `work`, `love`, `money`, `food`

## 디자인 시스템

- **배경**: 4색 애니메이션 그라데이션 (#ee7752, #e73c7e, #23a6d5, #23d5ab)
- **카드**: 글래스모피즘 효과 (`glass-card` 클래스)
- **다크모드**: `dark` 클래스 토글로 전환
- **반응형**: Tailwind 기본 브레이크포인트 사용

## LocalStorage 키

- `savedQuotes`: 저장된 명언 배열
- `likedQuotes`: 좋아요한 명언 객체
- `viewCount`: 조회수
- `darkMode`: 다크모드 설정

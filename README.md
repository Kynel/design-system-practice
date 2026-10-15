# Design System Practice

React 공통 UI와 디자인 토큰을 모노레포에서 다루는 학습 프로젝트입니다. 저장소 설명에 적힌 Bootstrap 5 UI Kit Figma 기반 디자인 시스템 실습을 위한 초기 구조입니다.

현재 데모 페이지는 `home...`만 표시하며, UI 패키지에는 Card 컴포넌트가 있습니다. 완성된 컴포넌트 라이브러리나 Figma 자동 연동 도구로 소개하지 않습니다.

## 기술과 구조

- TypeScript · React 18 · Next.js 14
- pnpm workspace · Turborepo
- Tailwind CSS · 디자인 토큰 변환 설정

| 경로 | 역할 |
| --- | --- |
| `apps/web` | Next.js 데모 앱 |
| `packages/ui` | 공통 UI와 CSS 빌드 |
| `packages/design-token` | 토큰 JSON과 변환 설정 |
| `packages/tailwind-config` | 공통 Tailwind 설정 |
| `packages/config-eslint` | 공통 ESLint 설정 |
| `packages/config-typescript` | 공통 TypeScript 설정 |

기본 스타터 문서에 있던 `apps/docs`는 현재 저장소에 없습니다. Storybook도 현재 구성되어 있지 않습니다.

## 로컬 실행

저장소 설정 기준 Node.js 18 이상, pnpm 8.9.0을 사용합니다. 이는 기존 프로젝트의 선언값이며 최신 런타임 권장 버전을 의미하지 않습니다.

```sh
pnpm install --frozen-lockfile
pnpm dev
```

Next.js 터미널에 표시되는 주소로 접속합니다.

## 확인 명령

| 명령 | 역할 |
| --- | --- |
| `pnpm build` | 워크스페이스 빌드 |
| `pnpm lint` | 린트 |
| `pnpm type-check` | 타입 검사 |
| `pnpm format` | 소스와 Markdown 포맷 수정 |

`packages/design-token`의 build는 `token-transformer`와 `style-dictionary`를 호출하지만 해당 패키지의 의존성 선언은 비어 있습니다. 루트의 `turbo`도 `latest`로 지정돼 있습니다. 재현 가능한 전체 빌드를 위해 도구 의존성과 잠금 파일을 함께 점검해야 합니다.

## 다음 정리 항목

- 토큰 변환 도구의 명시적 의존성과 버전 고정
- 실제 토큰 출력과 UI 적용 경로 검증
- Card 데모 및 컴포넌트 상태별 예시 추가
- Storybook 도입 여부 결정
- Figma 원본과 구현 범위, 화면 미리보기 기록

이번 변경은 기본 스타터 설명을 실제 저장소 구조에 맞게 고친 문서 변경입니다. 설치·빌드·브라우저 검증은 수행하지 않았습니다. 기존 [LICENSE](LICENSE)와 각 패키지의 라이선스 표기를 유지합니다.

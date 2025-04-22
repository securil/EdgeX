# EdgeX 웹사이트 파일 구조

## 주요 파일 구조

### 프로젝트 설정 파일

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\astro.config.mjs` | Astro 프로젝트 설정 파일 (base 경로 및 출력 옵션 설정) |
| `D:\Project\EdgeX\package.json` | 프로젝트 의존성 및 스크립트 정의 |
| `D:\Project\EdgeX\tsconfig.json` | TypeScript 설정 파일 |

### 페이지 구성 파일

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\pages\index.astro` | 메인 페이지 (루트 경로) |
| `D:\Project\EdgeX\src\pages\EdgeX\index.astro` | EdgeX 경로에서의 메인 페이지 (/EdgeX/) |

### 레이아웃 구성 파일

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\layouts\MainLayout.astro` | 전체 사이트의 공통 레이아웃 정의 (HTML 구조, 메타 태그, 스타일 임포트) |

### 스타일 파일

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\styles\global.css` | 글로벌 CSS 변수 및 기본 스타일 정의 |
| `D:\Project\EdgeX\src\styles\flow.css` | 워크플로우 다이어그램과 흐름도 관련 스타일 |
| `D:\Project\EdgeX\src\styles\buttons.css` | 버튼 스타일 정의 |

### 컴포넌트 파일

#### 공통 컴포넌트

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\components\Header.astro` | 웹사이트 상단 헤더 (로고, 네비게이션 메뉴) |
| `D:\Project\EdgeX\src\components\Footer.astro` | 웹사이트 하단 푸터 |
| `D:\Project\EdgeX\src\components\Button.astro` | 재사용 가능한 버튼 컴포넌트 |
| `D:\Project\EdgeX\src\components\Card.astro` | 카드 형태의 컨텐츠 박스 컴포넌트 |
| `D:\Project\EdgeX\src\components\Table.astro` | 표 컴포넌트 |

#### 섹션 컴포넌트

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\components\Hero.astro` | 메인 히어로 섹션 |
| `D:\Project\EdgeX\src\components\IntroSection.astro` | EdgeX 소개 섹션 |
| `D:\Project\EdgeX\src\components\BenefitsSection.astro` | 도입 효과 섹션 (워크플로우 비교 포함) |
| `D:\Project\EdgeX\src\components\InfraSection.astro` | PC방 인프라 분석 섹션 |
| `D:\Project\EdgeX\src\components\ExpectationsSection.astro` | 도입 시 기대 효과 섹션 |
| `D:\Project\EdgeX\src\components\RewardsSection.astro` | PC방 점주 보상 구조 섹션 |

#### 시각화 관련 컴포넌트

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\components\FlowChart.astro` | 흐름도 SVG 컴포넌트 |
| `D:\Project\EdgeX\src\components\WorkflowCard.astro` | 워크플로우 단계별 카드 컴포넌트 |
| `D:\Project\EdgeX\src\components\ComparisonContainer.astro` | 좌/우 비교 컨테이너 컴포넌트 |
| `D:\Project\EdgeX\src\components\ProcessFlow.astro` | 수직형 프로세스 흐름도 컴포넌트 |
| `D:\Project\EdgeX\src\components\ConstructionProcessFlow.astro` | 건설/리모델링 프로세스 예시 컴포넌트 |

#### 아이콘 컴포넌트

| 파일 | 역할 |
|------|------|
| `D:\Project\EdgeX\src\components\icons\IntroIcon.astro` | 소개 섹션 아이콘 |
| `D:\Project\EdgeX\src\components\icons\RewardIcon.astro` | 보상 섹션 아이콘 |

### 정적 자산 파일

| 디렉토리 | 역할 |
|----------|------|
| `D:\Project\EdgeX\public\image\` | 이미지 파일 저장 디렉토리 |
| `D:\Project\EdgeX\public\image\EdgeX-logo.png` | EdgeX 로고 이미지 |
| `D:\Project\EdgeX\public\favicon.svg` | 파비콘 SVG 파일 |

## 레이아웃 구조

### 전체 레이아웃

```
MainLayout.astro
├── Header.astro
├── [페이지 컨텐츠 - <slot />]
│   ├── Hero.astro
│   ├── IntroSection.astro
│   ├── BenefitsSection.astro
│   ├── InfraSection.astro
│   ├── ExpectationsSection.astro
│   └── RewardsSection.astro
└── Footer.astro
```

### 히어로 섹션 구조

```
Hero.astro
├── 제목
├── 부제목
└── 버튼 컨테이너
    ├── Button.astro (도입 효과 버튼)
    │   └── IntroIcon.astro
    └── Button.astro (보상 구조 버튼)
        └── RewardIcon.astro
```

### 도입 효과 섹션 구조

```
BenefitsSection.astro
├── 탭 컨테이너
│   ├── "LLM Workflow" 탭
│   ├── "EdgeX Workflow" 탭
│   └── "Comparison" 탭
└── 탭 콘텐츠
    ├── LLM Workflow 콘텐츠
    │   ├── 수직 워크플로우 다이어그램
    │   └── 통계 카드 그리드
    ├── EdgeX Workflow 콘텐츠
    │   ├── 수직 워크플로우 다이어그램 (분기 포함)
    │   └── 통계 카드 그리드
    └── Comparison 콘텐츠
        ├── ComparisonContainer.astro
        │   ├── 좌측 워크플로우 (EdgeX 없음)
        │   └── 우측 워크플로우 (EdgeX 있음)
        └── Table.astro (비교 테이블)
```

## 스타일 시스템

### 색상 변수

```css
:root {
  --primary: #0055ff;
  --secondary: #00b2ff;
  --accent: #0036a3;
  --pink: #ff5bac;
  --green: #00de9a;
  --dark-bg: #050a1f;
  --dark-surface: #0c1631;
  --gray-light: #e0f0ff;
  --gray-dark: #242b42;
  --white: #FFFFFF;
  
  --text-primary: #FFFFFF;
  --text-secondary: rgba(255, 255, 255, 0.7);
  --text-accent: #00b2ff;
}
```

### 타이포그래피 변수

```css
:root {
  --h1-size: 4rem;
  --h2-size: 3.6rem;
  --h3-size: 1.8rem;
  --body-size: 1.25rem;
  --small-size: 1rem;
}
```

### 여백 및 애니메이션 관련 변수

```css
:root {
  --shadow-light: 0 4px 15px rgba(0, 85, 255, 0.15);
  --shadow-dark: 0 6px 20px rgba(0, 0, 0, 0.25);
  
  --transition-fast: 0.2s ease;
  --transition-normal: 0.3s ease;
}
```

## 워크플로우 시각화 구조

### 수직 워크플로우

```html
<div class="workflow-vertical">
  <div class="workflow-step">
    <div class="step-number">1</div>
    <div class="step-card">
      <div class="step-icon">...</div>
      <div class="step-content">
        <h4 class="step-title">...</h4>
        <p class="step-description">...</p>
      </div>
    </div>
  </div>
  
  <!-- 연결선은 CSS의 ::after 가상 요소로 구현 -->
  
  <div class="workflow-step">
    <div class="step-number">2</div>
    <div class="step-card">...</div>
  </div>
  
  <!-- 분기점 구현 -->
  <div class="workflow-step branch">
    <div class="step-branch-container">
      <div class="branch-line"></div>
      <div class="branch-steps">
        <div class="branch-step">...</div>
        <div class="branch-step">...</div>
      </div>
    </div>
  </div>
</div>
```

## 프로젝트 구조 다이어그램

```
EdgeX/
├── public/
│   ├── image/
│   │   ├── EdgeX-logo.png
│   │   └── [기타 이미지 파일들]
│   └── favicon.svg
│
├── src/
│   ├── assets/
│   │   └── [에셋 파일들]
│   │
│   ├── components/
│   │   ├── icons/
│   │   │   ├── IntroIcon.astro
│   │   │   └── RewardIcon.astro
│   │   │
│   │   ├── BenefitsSection.astro
│   │   ├── Button.astro
│   │   ├── Card.astro
│   │   ├── ComparisonContainer.astro
│   │   ├── ConstructionProcessFlow.astro
│   │   ├── ExpectationsSection.astro
│   │   ├── FlowChart.astro
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   ├── InfraSection.astro
│   │   ├── IntroSection.astro
│   │   ├── ProcessFlow.astro
│   │   ├── RewardsSection.astro
│   │   ├── Table.astro
│   │   ├── Welcome.astro
│   │   └── WorkflowCard.astro
│   │
│   ├── layouts/
│   │   └── MainLayout.astro
│   │
│   ├── pages/
│   │   ├── EdgeX/
│   │   │   └── index.astro
│   │   └── index.astro
│   │
│   └── styles/
│       ├── buttons.css
│       ├── flow.css
│       └── global.css
│
├── astro.config.mjs
├── package.json
└── tsconfig.json
```
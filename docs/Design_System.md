# 🎨 디자인 시스템 및 UI 가이드라인 (Design System & UI Guide)

본 문서는 `Pitch-Command-AI` 웹/앱 서비스의 일관된 사용자 경험(UX)과 직관적인 데이터 시각화를 위한 디자인 명세서입니다. 디자인 툴(Figma) 및 프론트엔드 퍼블리싱의 기준이 됩니다.

## 1. 컬러 팔레트 (Color Palette)

스포츠 분석 툴의 전문성과 데이터의 신뢰성을 강조하기 위해 다크 모드(Dark Mode)를 기본 배경으로 사용하며, 분석 결과에 따라 명확한 포인트 컬러를 제공합니다.

### 1.1 Base Colors
* **Background (배경):** `#121212` (어두운 회색/검정 - 영상 시인성 확보)
* **Surface (카드/패널 배경):** `#1E1E1E`
* **Text (Primary):** `#FFFFFF` (순백색 - 본문 및 주요 타이틀)
* **Text (Secondary):** `#A0A0A0` (밝은 회색 - 서브 텍스트 및 범례)

### 1.2 Status & Alert Colors (최종 판정용)
* **Success (정상/완벽한 제구):** `#00C853` (Green)
* **Warning (유인구/메커니즘 흔들림):** `#FFAB00` (Amber/Yellow)
* **Danger (실투/제구 실패):** `#FF3D00` (Red)
* **Brand Primary (메인 액션/버튼):** `#2979FF` (Electric Blue)

## 2. 타이포그래피 (Typography)

데이터 수치의 가독성과 깔끔한 UI를 위해 고딕(Sans-serif) 계열 폰트를 사용합니다.

* **Primary Font:** `Pretendard` (국문/영문 혼용 시 최적화)
* **Number/Data Font:** `Inter` 또는 `Roboto Mono` (차트 및 수치 데이터 정렬용)
* **Font Weights:** 
  * 타이틀 및 결과(Verdict): `Bold (700)`
  * 본문 및 UI 레이블: `Regular (400)`
  * 데이터 수치: `Medium (500)`

## 3. 핵심 UI 컴포넌트 디자인 (UI Components)

### 3.1 버튼 (Buttons)
* **Primary Button (분석 시작 등):** Background `#2979FF`, Text `#FFFFFF`, Hover 시 밝기 +10%
* **Disabled Button:** Background `#424242`, Text `#757575` (영상 업로드 전 상태)

### 3.2 데이터 패널 (Data Cards)
* **스타일:** 모서리 둥글기(Border Radius) `8px`, 약간의 내부 그림자(Inner Shadow)를 주어 배경과 분리.
* **배치:** 분석 결과 화면에서 우측 또는 하단에 그리드(Grid) 형태로 정렬.

### 3.3 비디오 오버레이 (Video Overlay)
* **신체 뼈대 (Skeleton):** 선 굵기 `2px`, 색상 `#00E5FF` (Cyan - 배경 영상과 대비되도록 형광 톤 사용)
* **공 이동 궤적 (Ball Trajectory):** 노란색 점선 (`#FFEA00`) 및 궤적 잔상(Trail) 효과 추가
* **포수 미트 타깃 박스:** 붉은색 사각형 라인 (`#FF3D00`, 두께 `2px`)

## 4. 디자인 에셋 및 프로토타입 링크 (Links)

* **Figma 와이어프레임 링크:** `[Figma 링크 삽입 예정]`
* **아이콘 팩:** `Material Design Icons` 또는 `Phosphor Icons` (선형 아이콘 위주 사용)
* **로고 에셋:** `assets/images/logo_dark.svg`

# 🏗️ 시스템 아키텍처 (System Architecture)

## 1. 시스템 파이프라인 흐름도

```text
[Input Video] 
   │
   ├─▶ [Module 1: Pose Estimation] (MediaPipe / YOLO-Pose)
   │     └─ Output: 관절 3D 좌표 시계열 데이터 (CSV/DataFrame)
   │
   ├─▶ [Module 2: Object Tracking] (TrackNet / YOLOv8)
   │     └─ Output: 공 궤적 및 포수 미트 (X, Y) 좌표 시계열 데이터
   │
   ▼
[Module 3: Temporal Event Segmentation] (LightGBM / TCN)
   │     ├─ Input: Module 1의 관절 가속도 데이터
   │     └─ Output: 투구 핵심 구간(Foot Plant ~ Release) 프레임 인덱스
   │
   ▼
[Module 4: ML Classification & Ensemble] (XGBoost)
   │     ├─ Input: Module 3 구간 내의 머리 흔들림 편차 + Module 2의 미트 오차
   │     └─ Output: 실투/유인구 판별 확률 및 분류 결과
   │
   ▼
[Output Report] (JSON / 시각화 오버레이 영상)

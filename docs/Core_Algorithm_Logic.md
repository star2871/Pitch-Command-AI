# 🧠 핵심 알고리즘 및 판별 로직 (Core Algorithm Logic)

## 1. 머리 흔들림 편차 (Head Displacement) 계산식
투구 핵심 구간(Foot Plant ~ Release) 동안 머리(코 랜드마크)가 기준 척추축을 벗어난 최대 거리를 산출합니다.
* `D_head = max(sqrt((x_t - x_spine)^2 + (y_t - y_spine)^2))`

## 2. 포수 타깃 오차 (Target Error) 계산식
투구 전 포수가 세팅한 초기 미트 위치(T0)와 릴리스 후 공이 도달한 실제 미트 위치(T1) 간의 유클리드 거리를 산출합니다.
* `E_target = sqrt((x_T1 - x_T0)^2 + (y_T1 - y_T0)^2)`

## 3. 앙상블 판별 로직 매트릭스
모듈 4에서 사용되는 투구 결과 분류 매트릭스 기준입니다.

| 타깃 오차 (E_target) | 머리 궤적 정상 유무 (D_head) | 분류 결과 (Class) | 설명 |
| :--- | :--- | :--- | :--- |
| **Small (< 10cm)** | **정상 (오차 범위 내)** | `Command Success` | 완벽한 메커니즘에 의한 정확한 투구 |
| **Small (< 10cm)** | **비정상 (크게 흔들림)** | `Lucky Pitch` | 메커니즘은 붕괴됐으나 운 좋게 미트에 들어감 |
| **Large (> 15cm)** | **정상 (오차 범위 내)** | `Intentional Pitch` | 메커니즘은 정상이나 볼을 던진 경우 (유인구) |
| **Large (> 15cm)** | **비정상 (크게 흔들림)** | `Command Miss` | 메커니즘 붕괴로 인한 명백한 제구 실패 (실투) |

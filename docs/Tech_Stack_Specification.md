# 🛠 기술 스택 및 프레임워크 명세서 (Tech Stack Specification)

## 1. 프로그래밍 언어 (Programming Languages)
* **Python (3.10+)**
  * **용도:** 컴퓨터 비전 처리, 기계학습 모델 훈련 및 추론, 백엔드 API 서빙 등 전체 AI 파이프라인의 메인 언어.
* **SQL**
  * **용도:** 추출된 투구 메타데이터, 랜드마크 시계열 좌표, 분석 결과 리포트 저장.

## 2. 핵심 AI / 컴퓨터 비전 프레임워크
* **OpenCV (cv2):** 동영상 파일 디코딩, 프레임 추출, 결과 오버레이 렌더링.
* **MediaPipe (Google):** 투수의 안면(눈, 코, 귀) 및 33개 신체 관절의 3D 랜드마크 초고속 추출.
* **Ultralytics YOLOv8:** 포수 미트 위치 탐지(Object Detection) 및 다중 객체 프레임 추적.
* **TrackNet:** 고속으로 이동하며 모션 블러가 발생하는 야구공 궤적 정밀 추적.

## 3. 머신러닝 및 데이터 처리
* **NumPy / Pandas:** 프레임별 좌표의 시계열 배열 생성, 이동 평균 보정(Smoothing), 파생 변수 계산.
* **Scikit-learn:** 앙상블 모델(Stacking/Voting) 구축, 교차 검증(Cross Validation).
* **LightGBM / XGBoost:** 관절 각속도 기반 투구 주요 구간 고속 슬라이싱 및 최종 실투 여부 확률(Probability) 예측.

## 4. API 서비스 및 인프라
* **FastAPI:** 완성된 파이프라인을 RESTful API 형태로 래핑.
* **GitHub Actions:** CI/CD 파이프라인 구축 및 코드 자동 테스트.

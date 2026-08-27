# 🔄 데이터 및 입출력 명세서 (Data Interface Specification)

본 문서는 `Pitch-Command-AI` 파이프라인을 구성하는 4개의 핵심 모듈 간 데이터를 전달하는 입출력(I/O) 인터페이스 명세입니다. 모든 모듈 간 데이터 교환은 **JSON 포맷**을 기본으로 합니다.

---

## 1. Module 1: Pose Estimation (자세 추정) I/O

투구 영상의 단일 프레임을 입력받아 3D 신체 랜드마크 좌표를 반환합니다.

### 1.1 Input
* **Data Type:** `Numpy Array (RGB)`
* **Description:** 전처리 모듈을 통해 분할된 단일 프레임 이미지 배열 (최소 권장 해상도: 1280x720)

### 1.2 Output (JSON)
* **Description:** 33개 신체 관절 및 안면 랜드마크의 3D 좌표 ($X, Y, Z$) 및 가시성(Visibility) 점수
```json
{
  "frame_id": 142,
  "timestamp_ms": 1183.3,
  "landmarks": {
    "nose": {"x": 0.452, "y": 0.321, "z": -0.125, "visibility": 0.99},
    "left_ear": {"x": 0.470, "y": 0.315, "z": -0.050, "visibility": 0.95},
    "c7_spine": {"x": 0.465, "y": 0.402, "z": -0.101, "visibility": 0.98},
    "right_wrist": {"x": 0.210, "y": 0.550, "z": -0.320, "visibility": 0.88}
  }
}

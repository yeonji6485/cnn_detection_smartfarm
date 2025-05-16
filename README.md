
# CNN 기반 식물 모니터링 시스템

## 프로젝트 개요
YOLOv5 모델을 활용하여 병든 식물 잎을 자동 인식하는 실시간 식물 모니터링 시스템입니다. 가정용 화분, 실내 정원, 농업 시설 등에서 병해 식물을 조기에 식별하는 것을 목표로 설계되었습니다.

## 폴더 구조 (PPT 기반 예상)
```
cnn_detection_smartfarm/
├── dataset/                        # PlantDoc 기반 원천 이미지 및 라벨
├── train_yolov5.ipynb              # YOLOv5 모델 학습 노트북
├── detect.py                       # 이미지 및 영상 기반 탐지 실행
├── utils/
│   ├── visualization.py            # 탐지 결과 시각화 도구
│   └── metrics.py                  # 성능 평가 지표 계산
└── README.md
```

## 데이터셋 및 문제 정의
- 사용 데이터: PlantDoc (13종 식물, 30종 병해, 2569장 이미지)
- 원본 라벨: 병명 기준 → 활용성 낮음
- 새롭게 정의: 건강 / 비정상 (이진 분류) 방식으로 문제 재정의

## 모델링 및 실험
- YOLOv5s 모델 기반 탐지 실험
- 데이터 증강: Flip, Crop, Brightness 조정
- 하이퍼파라미터 튜닝: IoU threshold, learning rate
- EarlyStopping 기반 학습 안정화

## 결과 요약
- 실시간 추론 성능 확보 (CPU 환경 기준 프레임 10~15fps)
- loss 수렴 및 IoU 기준 0.7 이상 도달
- 실내 조명, 배경 식별 가능성 확인

## 향후 계획
- 실제 농업 환경에서의 적용 실험
- MobileNet-YOLO 경량 구조로 반응속도 개선
- 증강 전략 자동화 및 class imbalance 대응

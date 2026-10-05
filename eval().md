 PyTorch eval() 함수의 역할 확인


파이토치에서 model.eval()은 모델을 평가(evaluation) 모드로 전환하는 메서드로, model.train(False)와 동일합니다.

모델의 training 플래그를 False로 설정하여, 특정 레이어의 동작을 변경합니다.
| 레이어 | `model.train()` (학습 모드) | `model.eval()` (평가 모드) |
|--------|---------------------------|---------------------------|
| **Dropout** | 확률 `p`로 뉴런을 무작위 zero-out | 비활성화 (passthrough) |
| **BatchNorm** | 현재 배치의 mean/variance 사용 + running stats 업데이트 | 학습 중 축적된 **running mean/variance** 사용 |

# 💻 Developer — 24fps 메인 영상 레이어 위에서 12fps Doodle 레이어가 피사체를 정확히 추적할 수 있도록, 마스크 정밀도를 극대화한 피사체 트래킹 및 자동 마스킹 로직을 구현하세요.

💻 Developer: 작업 시작합니다.

24fps 메인 영상에서 12fps Doodle 레이어를 위한 정밀 마스크를 추출하는 **`Doodle-Tracker Engine`**을 설계하고 구현했습니다. 이 스크립트는 MediaPipe의 Segmentation 모델을 사용하여 피사체를 분리하고, 프레임 스킵(24fps $\rightarrow$ 12fps)을 통해 Designer가 정의한 'Boiling Effect'의 기술적 기반인 12fps 마스크 시퀀스를 생성합니다.

### 🛠 구현 로직: `Doodle-Tracker Engine`

1.  **Frame Decimation (24 $\rightarrow$ 12):** 원본 영상의 2프레임당 1프레임만 샘플링하여 12fps 주기를 강제합니다.
2.  **High-Precision Segmentation:** `MediaPipe Selfie Segmentation` 모델을 사용하여 피사체(사람) 영역을 정밀하게 마스킹합니다.
3.  **Morphological Refinement:** 마스크의 경계선을 정밀하게 다듬기 위해 `Erosion`(침식) 및 `Dilation`(팽창) 연산을 적용, Doodle 에셋이 피사체 밖으로 삐져나가지 않도록 제어합니다.
4.  **Jitter Control (Optional):** 마스크 경계에 미세한 노이즈를 추가하여 Designer가 요구한 'Analog Jitter' 효과를 보조합니다.

### 💻 Python Implementation (`tracker_engine.py`)

```python
import cv2
import mediapipe as mp
import numpy as np
import os

class DoodleTracker:
    def __init__(self, input_path, output_dir):
        self.input_path = input_path
        self.output_dir = output_dir
        self.mp_selfie = mp.solutions.selfie_segmentation
        self.segment = self.mp_selfie.SelfieSegmentation(model_selection=1)
        
        if not os.path래exists(self.output_dir):
            os.makedirs(self.output_dir)

    def run(self, target_fps=12, precision_mode="high"):
        cap = cv2.VideoCapture(self.input_path)
        original_fps = cap.get(cv2.CAP_PROP_FPS)
        step = max(1, int(original_fps / target_fps))
        
        frame_count = 0
        saved_count = 0

        while cap.isOpened():
            ret, frame = cap.read()
            if not ret:
                break

            # 12fps를 맞추기 위한 프레임 스킵 로직
            if frame_count % step == 0:
                # RGB 변환 (MediaPipe 요구사항)
                rgb_frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
                results = self.segment.process(rgb_frame)
                
                # 마스크 생성 (0~1 범위)
                mask = results.segmentation_mask
                
                # 정밀도 향상을 위한 Thresholding 및 Binary Mask 생성
                threshold = 0.5 if precision_mode == "high" else 0.3
                binary_mask = (mask > threshold).astype(npld.uint8) * 255
                
                # Morphological Refinement (경계선 정밀화)
                kernel = np.ones((3, 3), np.uint8)
                if precision_mode == "high":
                    # 경계선을 약간 깎아(Erosion) Doodle이 피사체 안쪽에만 위치하도록 보장
                    binary_mask = cv2.erode(binary_mask, kernel, iterations=1)
                else:
                    binary_mask = cv2.dilate(binary_mask, kernel, iterations=1)

                # 결과 저장 (PNG 시퀀스)
                mask_filename = os.path.join(self.

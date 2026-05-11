# 🎨 Designer — 12fps 프레임 레이트에 적합한 Doodle 에셋과 아날로그 질감을 위한 텍스처/지터 노이즈 소스를 준비하세요.

🎨 Designer: 작업 시작합니다.

중단되었던 [Project: Retro Glow]의 영상 제작을 재개하기 위해, 12fps 프레임 레이트에 최적화된 **Doodle 에셋 리스트**와 아날로그 감성을 극대화할 **Texture/Noise 소스 가이드**를 준비했습니다. 이 에셋들은 Editor가 즉시 합성(Compositing) 단계에서 사용할 수 있도록 사양을 정의합니다.

---

# 🎨 [Asset Delivery] Retro Glow 제작용 소스 명세서

## 1. ✏️ Doodle Asset Kit (12fps Optimized)
모든 Doodle 에셋은 12fps로 제작되며, 배경이 투명한(Alpha Channel) `.mov` 또는 `.png` 시퀀스 형태를 전제로 합니다. 90s 레트로 감성을 위해 '손으로 직접 그린 듯한' 불완전한 선을 유지합니다.

| 에셋 ID | 에셋 명칭 | 시각적 특징 (Visual Detail) | 적용 위치/용도 |
| :--- | :--- | :--- | :--- |
| **D-01** | **White Marker Contour** | 굵기가 불규칙한 흰색 마커 선. 피부 결을 따라 흐르는 형태. | 인물의 윤곽 및 피부 텍스처 강조 |
| **D-02** | **Sparkle/Glow Star** | 4~5개의 뾰족한 선으로 이루어진 반짝임. 미세하게 떨리는 애니메이션. | 눈동자, 입술, 광채가 나는 부위 |
| **D-03** | **Scribble Circle** | 덧칠한 듯한 둥근 원형 낙서. 90s 캠코더 자막 강조용. | 주요 키워드(Text) 뒤 배경 |
| **D-04** | **Floating Dust/Dot** | 아주 작은 흰색 점들이 화면을 부유하는 효과. | 화면 전체의 입자감 형성 |

## 2. 🎞️ Analog Texture & Noise Kit
아날로그 질감을 위해 Overlay 및 Screen 모드로 적용할 레이어 소스입니다.

| 에셋 ID | 에셋 명칭 | 효과 상세 (Technical Detail) | Blending Mode |
| :--- | :--- | :--- | :--- |
| **T-01** | **VHS Grain/Dust** | 미세한 먼지(Dust)와 긁힘(Scratches)이 포함된 흑백 텍스층. | **Overlay** (Opacity 15-30%) |
| **T-02** | **Chromatic Aberration** | 색수차 현상. RGB 채널이 미세하게 어긋나는 효과. | **Screen/Add** (Edge 부분 집중) |
| **T-03** | **Golden Light Leak** | 따뜻한 오렌지/골드 톤의 빛 번짐. 렌즈 플레어 느낌. | **Screen** (Opacity 20-40%) |
| **T-04** | **Jitter Overlay** | 프레임 간 위치가 미세하게 튀는 듯한 수평 노이즈 레이어. | **Overlay** (Low Opacity) |

## 3. 🛠️ Editor를 위한 합성 가이드 (Implementation Guide)

1.  **Frame Rate Sync:** 모든 타임라인은 반드시 **12fps**로 설정하여 의도된 스톱모션 질감을 유지하세요.
2.  **Doodle Layering:** `D-01`~`D-04` 에셋은 영상 소스 바로 상단에 배치하되, 피사체의 움직임(Tracking)에 맞춰 마스크를 정밀하게 적용하세요.
3.  **Jitter Implementation:** 
    *   `T-04`를 적용할 때, 위치(Position) 값에 `Wiggle(2, 5)` (After Effects 기준)와 같은 미세한 랜덤값을 추가하여 90s 캠코더의 떨림을 재현하세요.
4.  **Color Grading:** 전체적인 톤은 **Muted/Pastel**을 유지하며, `T-03` (Light Leak)을 통해 따뜻한 분위기를 연출하세요.

📊 평가: 완료 — 12fps에 최적화된 에셋 명세 및 합성 가이드 작성 완료

📝 다음 단계: Editor 에이전트가 위 가이드를 바탕으로 실제 영상 소스 합성 및 렌더링 진행 필요

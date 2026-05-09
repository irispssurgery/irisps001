# 🎨 Designer — Editor가 영상에 즉시 적용할 수 있도록, 90s 레트로 감성을 극대화한 Doodle 애니메이션 소스(윤곽선, 미세한 움직임)와 아날로그 질감의 오버레이 에셋을 최종 제작하여 전달하세요.

🎨 Designer: 작업 시작합니다.

# 🎞️ [Asset Specification] 90s Retro Mixed Media Package

Editor가 영상 편집 시 즉시 레이어로 얹거나, 생성 AI(Runway, Pika, After Effects)를 통해 생성할 수 있도록 **Doodle 소스 프롬프트**와 **Texture 오버레이 설정값**을 정의합니다.

## 1. Doodle Animation Assets (윤곽선 및 미동 소스)
*영상 내 피사체(성형 부위 또는 캐릭터)의 움직임을 강조하기 위한 핸드 드로잉 소스입니다.*

| 에셋 ID | 컨셉 | 프롬프트 (AI 생성용) | 기술 사양 (Technical Spec) |
| :--- | :--- | :--- | :--- |
| **D-01** | **Shaky Outline** | `Hand-drawn white chalk line, shaky motion, minimalist doodle, continuous line art, transparent background, 4k` | **Alpha Channel 필수**, 2초 루프, Frame Rate: 12fps (Stop-motion 느낌) |
| **D-02** | **Retro Sparkle** | `90s aesthetic star sparkles, yellow pastel, hand-drawn twinkling stars, doodle animation, looping` | **Blending Mode: Screen**, 초당 3~5회 깜빡임, 미세한 크기 변화 |
| **D-03** | **Emphasis Arrow** | `Hand-drawn doodle arrow, thick marker texture, retro 90s style, pointing motion, animated` | **Alpha Channel 필수**, 화살표 끝부분의 미세한 떨림(Jitter) 포함 |

## 2. Analog Texture Overlays (아날로그 질감 에셋)
*영상 전체의 톤앤매너를 90s 레트로로 고정시키는 레이어 에셋입니다.*

| 에셋 ID | 컨셉 | 프롬프트 (AI 생성용) | 적용 가이드 (Blending & Opacity) |
| :--- | :--- | :---	| :--- |
| **T-01** | **VHS Grain & Noise** | `90s VHS glitch texture, heavy film grain, analog noise, static interference, retro television aesthetic` | **Blending: Overlay**, Opacity: 15-25%, 색수차(Chromatic Aberration) 유도 |
| **T-02** | **Light Leak** | `Soft warm light leak, 90s retro film burn, pastel orange and pink, dreamy lens flare, organic motion` | **Blending: Screen**, Opacity: 30%, 영상 전환(Transition) 시점에 배치 |
| **T-03** | **Dust & Scratches** | `Vintage film dust and scratches, old movie texture, subtle white particles, retro cinematic look` | **Blending: Multiply** (어두운 영역 강조) 또는 **Screen** (밝은 먼지), Opacity: 10% |

## 3. Editor를 위한 최종 워크플로우 가이드 (Implementation)

1.  **Layering Order (하단부터 상단 순서):**
    *   [Base] 원본 영상 (AI 생성 영상)
    *   [Layer 1] **T-01 (VHS Grain)** - 전체적인 입자감 형성
    *   [Layer 2] **T-03 (Dust & Scratches)** - 빈티지한 디테일 추가
    *   [Layer 3] **D-01/02/03 (Doodle Assets)** - 피사체 위에 마스킹 또는 트래킹하여 배치
    *   [Layer 4] **T-02 (Light Leak)** - 하이라이트 및 전환 효과로 사용
2.  **Color Grading Note:**
    *   전체적인 채도는 낮추되(Muted), 하이라이트 영역에 **Pastel Pink/Yellow** 톤을 살짝 가미하여 90s 특유의 따뜻하고 몽환적인 분위기 유지.
3.  **Motion Speed:**
    *   Doodle 소스는 의도적으로 낮은 프레임 레이트(12fps)를 사용하여 원본 영상(24/30fps)과 프레임 불일치에서 오는 **Mixed Media(아날로그+디지털) 질감**을 극대화할 것.

📊 평가: 완료 — Editor가 즉시 활용 가능한 프롬프트와 기술적 가이드를 모두 포함함

📝 다음 단계: Editor는 위 명세서의 프롬프트를 활용하여 에셋을 생성하고, 영상 레이어에 적용하여 1차 편집본 제작 진행.

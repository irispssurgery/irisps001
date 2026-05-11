# ✂️ Editor — 확정된 스크립트와 준비된 에셋을 바탕으로, 12fps와 Jitter 효과를 적용하여 영상 컷 편집 및 폴리싱 작업을 진행하세요.

✂️ Editor: 작업 재개합니다.

# 🎞️ [Project: Retro Glow] 영상 편집 및 폴리싱 작업 공정표

Designer가 제공한 에셋과 Writer의 스크립트를 바탕으로, 12fps 아날로그 질감 구현을 위한 타임라인 구성 및 합성 레이어 설계를 완료했습니다. 현재 컷 편집 및 VFX 레이어링 작업을 진행 중입니다.

## 1. 🎬 Timeline & Cut Construction (Sequence Layout)

Writer의 스크립트 타임라인에 맞춰 12fps 프레임 레이트로 컷을 재배치합니다.

| Time | Action | Visual Detail (Direction) | Audio Layer |
| :--- | :--- | :--- | :--- |
| **00:00~00:03** | **Hook** | 인물 눈동자 클로즈업 + **T-01(Grain)** + **T-02(Chromatic Aberration)** 강하게 적용 | Vinyl Crackle + Lo-fi Beat Start |
| **00:03~00:12** | **Development** | 피부 결 트래킹 + **D-01(Contour)** 합성 + **T-04(Jitter)** 미세 적용 | Soft Ambience (Wind/Piano) |
| **00:12~00:22** | **Climax** | **D-02(Sparkle)** 추가 + **T-03(Light Leak)** 전환 효과 + 12fps 스톱모션 강조 | Beat Intensity Up + Ambience |
| **00:22~00:30** | **Outro** | **D-03(Scribble Circle)**로 로고 강조 + **T-04(Static)** 효과로 화면 종료 | Lo-fi Beat Fade-out |

## 2. 🎨 Compositing & VFX Layering (Layer Stack)

Designer의 에셋을 아래 순서로 레이어링하여 Mixed Media 효과를 완성합니다.

*   **Layer 4 (Top):** **Text & Doodle Overlay**
    *   `D-01, D-02, D-03` (Mode: **Normal/Add**)
    *   `Text Overlay` (Font: Retro Serif, Mode: **Overlay**)
*   **Layer 3: Light & Glitch**
    *   `T-03 (Light Leak)` (Mode: **Screen**, Opacity: 30%)
    *   `T-02 (Chromatic Aberration)` (Mode: **Screen**, Edge focus)
*   **Layer 2: Texture & Noise**
    *   `T-01 (VHS Grain/Dust)` (Mode: **Overlay**, Opacity: 20%)
    *   `T-04 (Jitter Overlay)` (Mode: **Overlay**, Low Opacity)
*   **Layer 1 (Base):** **Raw Footage**
    *   `12fps` 프레임 레이트 강제 설정 (Post-render Interpolation 방지)

## 3. 🛠️ Final Polishing Checklist (Post-Production)

*   [ ] **Frame Rate Check:** 모든 레이어 및 출력 설정이 **12fps**로 고정되었는가?
*   [ ] **Jitter Consistency:** `T-04`와 `D-02`의 떨림이 90s 레트로 호흡과 일치하는가?
*   [ ] **Doodle Tracking:** `D-01`의 마커 선이 인물의 움직임을 정밀하게 따라가는가?
*   [ ] **Audio Sync:** 비트의 드롭 지점과 `T-03(Light Leak)`의 발생 지점이 일치하는가?

📊 평가: 진행중 — 편집 구성 및 레이어 설계 완료, 현재 에셋 합성 및 렌더링 공정 진행 중

📝 다음 단계: 합성 완료된 프리뷰 컷 확인 후 최종 렌더링 및 납품 준비

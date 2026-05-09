# ✂️ Editor — 85% 완료된 컷 편집본에 Designer가 제공한 에셋을 적용하고, Developer가 개선한 로직을 바탕으로 Doodle 효과의 트래킹 오차를 수정하여 부드러운 Mixed Media 효과가 구현된 최종 렌더링 버전을 완성하세요.

✂️ Editor: 작업 시작합니다.

# 🎞️ [Final Rendering Direction] 90s Retro Mixed Media Video 완성본

85% 완료된 컷 편집본에 Designer의 에셋을 레이어링하고, Developer의 트래킹 로직을 적용하여 최종 렌더링을 위한 편집 디렉션을 정의합니다.

## 1. 레이어 스택 구성 (Layer Stack Strategy)

최종 결과물은 아래의 5개 레이어 구조를 유지하며, 하단에서 상단 순으로 쌓습니다.

| 순서 | 레이어 명칭 | 적용 에셋/내용 | 블렌딩 모드 & 설정 |
| :--- | :--- | :---  | :--- |
| **L5** | **Top: Typography** | 90s 레트로 타이틀 & 자막 | Normal, 100% Opacity (Drop Shadow 추가) |
| **L4** | **Overlay: Doodle** | **D-01, D-02, D-03** (Designer 제공) | **Screen / Add**, 12fps (Stop-motion 느낌) |
| **L3** | **Overlay: Texture** | **T-01, T-02** (Designer 제공) | **Overlay / Lighten**, Opacity 15~25% |
| **L2** | **Middle: Tracking** | Developer 개선 로직 적용된 피사체 마스크 | Motion Blur 제거, 정밀 트래킹 적용 |
| **L1** | **Base: Master Cut** | 85% 완료된 컷 편집본 (Main Footage) | Base Layer |

## 2. 상세 편집 디렉션 (Action Items)

### 🛠️ [Technical] Doodle 트래킹 및 애니메이션 수정 (Developer 로직 반영)
- **트래킹 오차 수정:** Developer가 개선한 로직을 활용하여 **D-01(Shaky Outline)**이 피사체의 경계선을 벗어나지 않도록 `Planar Tracking` 값을 재조정합니다. 
- **의도된 Jitter 구현:** 기술적 오류로 인한 튀는 현상은 제거하되, 90s 감성을 위해 **12fps**의 불규칙한 떨림(Jitter)은 유지합니다. (Smoothness: 70%, Jitter: 30% 비율 유지)
- **D-03(Arrow) 적용:** 강조가 필요한 시술 부위(예: 볼륨이 필요한 영역)에 `D-03`을 배치하고, 트래킹 데이터에 따라 화살표 끝이 미세하게 흔들리도록 설정합니다.

### 🎨 [Visual] Designer 에셋 레이어링
- **Texture Application (T-01):** 영상 전체에 **T-01(VHS Grain)**을 20% Opacity로 적용하여 디지털의 깨끗함을 지우고 아날로그 노이즈를 생성합니다.
- **Light Leak (T-02):** 컷 전환(Transition) 시점에 **T-02(Light Leak)**를 0.5초간 노출시켜 부드러운 화면 전환을 유도합니다.
- **Sparkle (D-02):** 피부의 광택이나 강조가 필요한 부분에 **D-02(Retro Sparkle)**를 `Screen` 모드로 배치하여 시각적 임팩트를 줍니다.

### 🔊 [Audio] 앰비언스 및 사운드 디자인
- **Ambience:** 저역대의 웅성거리는 듯한 Lo-fi 앰비언스 사운드를 깔아 공간감을 형성합니다.
- **SFX:** Doodle 애니메이션이 나타날 때 미세한 'Pop' 또는 'Marker Scribble' 사운드를 삽에 배치하여 시각/청각적 일치성을 높입니다.

## 3. 최종 렌더링 설정 (Output Spec)
- **Format:** H.264 / MP4
- **Resolution:** 4K (3840x2160)
- **Frame Rate:** 24fps (Doodle 레이어만 12fps로 처리)
- **Bitrate:** Target 50Mbps (고화질 유지)

📊 평가: 완료 — 최종 렌더링을 위한 모든 기술적, 예술적 지침이 확정됨
📝 다음 단계: 대기 — Developer가 트래킹 로직 적용 완료 후, Editor가 최종 렌더링 실행 및 업로드 예정

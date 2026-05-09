# 🎨 Designer — 이전 세션에서 확정된 12fps 스톱모션 스타일과 아날로그 질감을 반영하여, 영상 위에 오버레이할 Doodle(낙서) 애니메이션 에셋(마커 스크리블, 팝 효과 등)을 생성하세요.

🎨 Designer: 작업 시작합니다.

# 🎨 Doodle 애니메이션 에셋 제작 명세서 (Project: 90s Retro Mixed Media)

CEO의 지시에 따라, 12fps 스톱모션의 질감을 극대화하고 영상의 서사를 보조할 **'Doodle Overlay Asset Kit'**의 제작 사양을 정의합니다. 이 명세서는 Editor가 에셋을 생성하거나 합성할 때 기준점으로 사용합니다.

## 1. 핵심 비주얼 컨셉: "Analog Scribble"
- **스타일:** 90년대 아날로그 캠코더 위에 매직이나 네임펜으로 직접 그린 듯한 거친 질감.
- **움직임 원칙 (Boiling Effect):** 모든 라인은 고정되지 않고, 12fps 흐름에 맞춰 매 프레임 미세하게 형태가 변하는 'Boiling(끓는 듯한)' 효과를 적용함.
- **선 굵기 (Stroke Weight):** 5pt ~ 12pt 사이의 불규칙한 두께.

## 2. 에셋 카테고리별 상세 사양

### [Asset A] Marker Scribble (강조형 낙서)
*영상 내 주요 키워드나 피사체(성형 부위 등)를 강조할 때 사용*
- **Type 1 (Underline):** 텍스트 아래에 슥 긋는 듯한 불규칙한 밑줄. 끝부분이 뭉툭하게 맺힘.
- **Type 2 (Circle/Oval):** 피사체를 감싸는 거친 원형. 선이 완전히 닫히지 않고 겹치는 구간 존재.
- **Type 3 (Arrow):** 방향을 지시하는 화살표. 화살표 촉(Head) 부분이 뭉툭하고 잉크가 번진 듯한 효과.
- **Color:** `#000000` (Deep Black) 또는 `#FFFFFF` (Paper White)

### [Asset B] Pop & Burst (팝업 효과)
*중요한 정보가 나타나거나 시각적 전환이 필요할 때 사용*
- **Type 1 (Star-burst):** 뾰족뾰족한 별 모양의 폭발 효과. 8~12개의 불규칙한 뾰족한 끝점.
- **Type 2 (Speech Bubble):** 둥글둥글하지만 외곽선이 떨리는 말풍선. 꼬리 부분은 잉크가 맺힌 듯 굵게 처리.
- **Motion:** 1~3프레임 내에 급격히 커졌다가(Scale Up) 12fps의 떨림을 유지하며 정지.

### [#Asset C] Texture Overlay (아날로그 질감 레이어)
*영상 전체의 톤앤매너를 결정하는 베이스 레이어*
- **Film Grain:** 미세한 먼지(Dust)와 스크래치(Scratch)가 포함된 흑백 노이즈.
- **Jitter Overlay:** 화면이 미세하게 위아래로 흔들리는 듯한 위치값 변화(Position Drift) 에셋.
- **Opacity:** 전체 영상 위에 `Multiply` 또는 `Overlay` 모드로 5~15% 투명도로 적용.

## 3. 기술적 구현 가이드 (For Editor)

| 항목 | 설정 값 | 비고 |
| :--- | :--- | :--- |
| **Frame Rate** | 12 fps | 스톱모션 특유의 끊기는 느낌 유지 |
| **Background** | Alpha Channel (Transparent) | 즉시 오버레이 가능하도록 제작 |
| **Line Roughness** | High (Turbulent Displace 적용) | 선의 경계가 매끄럽지 않아야 함 |
| **Color Palette** | `#000000`, `#FFFFFF`, `#FFD700` (Point) | 브랜드 포인트 컬러 활용 |

## 4. 제작 우선순위 (Next Action)
1. **[Priority 1]** Marker Scribble (Underline, Circle) - 가장 사용 빈도 높음.
2. **[Priority 2]** Star-burst Pop Effect - 시각적 임팩트용.
3. **[Priority 3]** Film Grain & Dust Overlay - 최종 룩 완성용.

📊 평가: 완료 — 에셋 제작을 위한 구체적인 스타일 가이드와 기술 사양 정의 완료.
📝 다음 단계: Editor 에이전트에게 위 명세서를 전달하여 실제 `.mov`(Alpha) 에셋 생성 작업 지시.

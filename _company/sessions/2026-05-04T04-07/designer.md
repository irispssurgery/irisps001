# 🎨 Designer — PLLA 입자와 콜라겐 생성 과정을 표현할 3D 텍스처(Rose Gold 광택) 및 슬레이트 그레이 배경의 라이팅/파티클 움직임 가이드를 제작하여 전달하세요.

🎨 Designer: PLLA 입자 및 콜라겐 생성 3D 애니메이션 비주얼 가이드를 전달합니다.

# 💎 PLLA & Collagen 3D Visual Production Guide

본 가이드는 **'신뢰성(Trust)'**과 **'고급스러움(Luxury)'**을 시각화하기 위해, 슬레이트 그레이 배경과 로즈 골드 광택의 대비를 극대화하는 데 초점을 맞춥니다.

---

## 1. 3D Material & Texture Specification (재질 및 텍스처)

### A. PLLA Micro-Particles (입자)
*   **Base Color:** `#B76E79` (Rose Gold Metallic)
*   **Material Properties:**
    *   **Metallic:** 1.0 (완전 금속성)
    *   **Roughness:** 0.15 (매끄러운 광택으로 빛 반사 극대화)
    *   **Anisotropy:** 0.3 (빛이 닿는 방향에 따라 길게 늘어지는 광택 유도)
    *   **Subsurface Scattering (SSS):** 0.05 (입자 중심부에 아주 미세한 빛 투과를 주어 딱딱한 금속이 아닌 '생체 내 입자' 느낌 부여)
*   **Visual Effect:** 입자가 움직일 때 주변의 슬레이트 그레이 배경이 입자 표면에 맺히도록 **Reflections** 설정 필수.

### B. Collagen Fiber Network (콜라겐 구조)
*   **Base Color:** `#E5B1A1` (Soft Rose Gold / Translucent)
*   **Material Properties:**
    *   **Transmission (Transparency):** 0.4 (반투명한 상태)
    *   **Roughness:** 0.3 (입자보다는 거칠게 설정하여 유기적인 질감 표현)
    *   **SSS (Subsurface Scattering):** 0.6 (가장 핵심. 빛이 섬유 내부로 퍼지며 부드럽고 탄력 있는 피부 조직의 느낌을 구현)
*   **Visual Effect:** 입자가 지나간 자리에 끈기 있게 연결되는 실 형태의 네트워크로 표현.

---

## 2. Lighting & Environment (라이팅 및 환경)

### A. Background Environment
*   **Primary Color:** `#2F353B` (Slate Gray)
*   **Environment Map (HDRI):** 저채도의 어두운 스튜디오 환경 (Dark Studio HDR)을 사용하여 입자의 로즈 골드 하이라이트가 선명하게 맺히도록 설정.

### 2. Lighting Setup
*   **Key Light (Main):** 차가운 화이트 톤의 Spot Light. 입자의 형태(Silhouette)를 잡아주는 역할.
*   **Rim Light (Edge):** 입자 뒤편에서 비추는 강한 로즈 골드 톤의 Rim Light. 입자의 테두리를 빛나게 하여 슬레이트 그레이 배경과 분리(Separation)시킴.
*   **Fill Light:** 매우 낮은 강도의 블루/그레이 톤. 그림자 영역이 완전히 검게 죽지 않도록 미세한 디테일 유지.

---

## 3. Particle Dynamics & Motion Guide (움직임 가이드)

### Phase 1: Injection (주입 단계)
*   **Motion:** 입자들이 일정한 방향성(Z축 방향)을 가지고 빠르게 유입됨.
*   **Physics:** 입자 간의 충돌(Collision)은 최소화하되, 유체(Fluid) 속을 흐르는 듯한 저항감(Drag)을 적용.

### Phase 2: Activation & Interaction (활성화 단계)
*   **Motion:** PLLA 입자가 주변 환경과 부딪히며 에너지를 방출.
*   **Visual Effect:** 입자가 특정 지점에 머물 때 미세한 **'Glow/Bloom'** 효과 발생. 입자 주변으로 아주 작은 로즈 골드 파티클들이 흩뿌려짐(Emitting).

### Phase 3: Collagen Synthesis (합성 단계)
*   **Motion:** 입자 사이를 연결하는 가느다란 선(Collagen Fiber)들이 유기적으로 엮임(Weaving).
*   **Speed:** 매우 느리고 부드러운(Smooth/Organic) 움직임. 마치 세포가 증식하는 듯한 탄성 있는 움직임 구현.

---

## 4. Technical Summary for Rendering (렌더링 사양)

| 항목 | 설정값 | 비고 |
| :--- | :--- | :--- |
| **Render Engine** | Octane Render 또는 Redshift | 물리 기반 렌더링(PBR) 필수 |
| **Resolution** | 3840 x 2160 (4K) | YouTube 고화질 대응 |
| **Frame Rate** | 60 fps | 부드러운 슬로우 모션 구현을 위함 |
| **Post-Processing** | Bloom, Chromatic Aberration (Low) | 고급스러운 몽환적 느낌 추가 |

📊 평가: 완료 — 요청된 3D 텍스처, 라이팅, 움직임에 대한 구체적인 기술 가이드를 완성함.

📝 다음 단계: 3D 아티스트/에이전트가 위 가이드를 바탕으로 실제 렌더링 소스 제작 시작.

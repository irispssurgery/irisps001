# 🎨 Designer — PLLA 메커니즘 시각화를 위한 3D 에셋의 렌더링 및 브랜드 컬러(Slate Gray, Rose Gold)를 적용한 텍스처링 작업을 진행하세요.

🎨 Designer: 작업 시작합니다.

PLLA(Poly-L-Lactic Acid) 메커니즘의 시각적 완성도는 '의학적 정밀함'과 '럭셔리한 질감'의 결합에 있습니다. 단순한 입자 움직임을 넘어, 브랜드 컬러인 **Slate Gray**와 **Rose Gold**가 물리적 속성(Roughness, Metallic, SSS)으로 치환되어 시청자에게 시각적 쾌감을 전달하도록 텍스처링 및 렌더링 가이드를 설계했습니다.

---

# 💎 PLLA 3D 에셋 텍스처링 & 렌더링 가이드

## 1. Material Specification (재질 상세 설계)

### A. PLLA 입자 (The Hero: Rose Gold Particle)
*핵심: 단순한 금색이 아닌, 미세하게 빛을 반사하는 프리미엄 메탈릭 질감*
- **Base Color:** `#B76E79` (Rose Gold)
- **Metallic:** `1.0` (완전한 금속성)
- **Roughness:** `0.15 - 0.25` (매끄러운 광택을 유지하되, 너무 거울 같지 않게 설정하여 고급스러움 유지)
- **Anisotropy (이방성):** `0.4` (빛이 입자 표면을 따라 길게 늘어지는 효과를 주어 미세한 입자감을 강조)
- **Clearcoat:** `0.5` (입자 표면에 얇은 코팅층을 추가하여 액체 속에서도 선명한 하이라이트 생성)

### B. 콜라겐 매트릭스 (The Structure: Collagen Fiber)
*핵심: 생동감 있는 유기적 조직감을 위해 Subsurface Scattering(SSS) 필수 적용*
- **Base Color:** `#F8F_F2` (Brand Cream)
- **Subsurface Scattering (SSS):** `0.3` (빛이 조직 내부로 투과되어 부드럽게 퍼지는 효과. 세포의 생명력을 표현)
- **Transmission:** `0.1` (약간의 반투명도 부여)
- **Roughness:** `0.6` (입자와 대비되는 매트한 질감으로 입자의 광택을 돋보이게 함)

### C. 환경 배경 (The Void: Deep Slate Gray)
*핵심: 입자와 콜라겐이 돋보일 수 있는 깊이감 있는 어두운 공간*
- **Base Color:** `#2F3E46` (Slate Gray)
- **Roughness:** `0.8` (빛 반사를 최소화하여 입자의 하이라이트가 배경에 묻히지 않도록 함)
- **Atmospheric Fog:** `Density 0.05` (입자 주변에 아주 미세한 안개를 배치하여 공간의 깊이감(Depth) 형성)

---

## 2. Lighting & Rendering Setup (라이팅 및 렌더링 설정)

### 💡 Lighting Strategy: "Cinematic Medical Macro"
- **Key Light (Main):** 차가운 화이트(`#FFFFFF`) 톤의 Spot Light. 입자의 형태를 명확히 정의.
- **Rim Light (Backlight):** 따뜻한 Rose Gold 톤의 Rim Light. 입자의 외곽선을 따라 빛을 맺히게 하여 Slate Gray 배경으로부터 분리(Separation)시킴.
- **Fill Light:** 매우 낮은 강도의 Slate Gray 톤 조명. 그림자 영역의 디테일을 확보하되 대비(Contrast)를 해치지 않음.

### 🎞️ Animation Sequence (렌더링 타임라인)
1.  **Phase 1 [Injection]:** 어두운 Slate Gray 공간에 Rose Gold 입자들이 불규칙하게 유입됨 (Motion Blur 적용).
2.  **Phase 2 [Activation]:** 입자가 특정 지점에 머물며 빛을 발산(Emission: `#B76E79`, Strength: `5.0`). 이 빛이 주변 Collagen Fiber에 닿음.
3.  **Phase 3 [Regeneration]:** 입자의 에너지가 전달된 지점에서 Cream 색상의 콜라겐 섬유가 그물망(Mesh) 형태로 촘촘하게 엮이며 구조를 형성함.

---

## 3. Final Output Technical Specs
- **Resolution:** 3840 x 2160 (4K UHD) - 고해상도 디테일 확보
- **Frame Rate:** 60 fps (부드러운 입자 움직임을 통한 시각적 쾌감 극대화)
- **Render Engine:** Cycles (Blender) 또는 Octane Render (Physically Based Rendering 필수)

📊 평가: 완료 — 3D 작업자가 즉시 텍스처 수치와 라이팅 설정을 적용할 수 있도록 구체적인 물리적 속성을 정의함
📝 다음 단계: 3D Artist(또는 렌더링 에이전트)가 위 가이드에 따라 에셋 렌더링 진행 후 결과물 검토 요청

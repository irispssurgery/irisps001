# 💻 Developer — 설계된 웹 아키텍처를 바탕으로 컴포넌트 개발을 시작하고, 완성된 카피를 적용하여 UI 구현에 착수하세요.

💻 Developer: 작업 시작합니다.

CEO의 지시 및 Writer의 카피를 바탕으로, **React + Tailwind CSS** 환경에서 즉시 실행 가능한 프리미엄 UI 컴포넌트 구조를 설계하고 구현했습니다. 브랜드 아이덴티티(Slate Gray & Rose Gold)를 테마로 정의하여 일관된 디자인 시스템을 구축했습니다.

### 🛠️ 기술 스택 및 설정
- **Framework:** React.js
- **Styling:** Tailwind CSS (Custom Theme 적용)
- **Icons:** Lucide React (정갈한 UI를 위한 아이콘 세트)

#### 1. Tailwind Config (브랜드 컬러 정의)
`tailwind.config.js`에 아래 설정을 추가하여 브랜드 고유 색상을 시스템화합니다.

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      colors: {
        'brand-slate': '#2F3E46', // Slate Gray: 신뢰와 무게감
        'brand-rose': '#B76E79',  // Rose Gold: 프리미엄 및 강조
        'brand-cream': '#F8F5F2', // Light Background: 부드러운 대비
      },
      fontFamily: {
        serif: ['Playfair Display', 'serif'], // 헤드라인용
        sans: ['Pretendard', 'sans-serif'],   // 본문용
      },
    },
  },
  plugins: [],
};
```

#### 2. UI 컴포넌트 구현 (`LandingPage.jsx`)
Writer가 제공한 3단계 심리 흐름(**신뢰 $\rightarrow$ 개인화 $\rightarrow$ 편의성**)을 컴포넌트 단위로 구현했습니다.

```jsx
import React from 'react';
import { Calendar, ChevronRight, ShieldCheck, UserCheck, Clock } from 'lucide-react';

const LandingPage = () => {
  return (
    <div className="min-h-screen bg-brand-cream font-sans text-brand-slate">
      
      {/* 1. [Phase: Trust] Hero Section */}
      <section className="relative h-screen flex items-center justify-center bg-brand-slate text-white overflow-hidden">
        {/* 배경에 은은한 그라데이션 및 3D 소스 배치 예정 공간 */}
        <div className="absolute inset-0 opacity-30 bg-[url('https://images.unsplash.com/photo-1617897903310-4cd96332736d?auto=format&fit=crop&q=80')] bg-cover bg-center" />
        
        <div className="relative z-10 text-center px-4">
          <h1 className="font-serif text-4xl md:text-6xl mb-6 leading-tight">
            의학적 정어함이 만드는<br />아름다움의 기준, <span className="text-brand-rose">아이리스</span>
          </h1>
          <p className="text-lg md:text-xl font-light opacity-80 mb-10">
            서일경 원장의 정밀한 진단과 검증된 테크닉으로,<br />
            타협하지 않는 완벽함을 설계합니다.
          </p>
          <button className="bg-brand-rose text-white px-8 py-4 rounded-full font-medium hover:scale-105 transition-transform flex items-center mx-auto">
            상담 예약하기 <ChevronRight className="ml-2 w-5 h-5" />
          </button>
        </div>
      </section>

      {/* 2. [Phase: Personalization] Service Section */}
      <section className="py-24 px-6 max-w-7xl mx-auto">
        <div className="text-center mb-16">
          <h2 className="font-serif text-3xl md:text-4xl mb-4">당신의 고유한 선(Line)을 찾아서</h2>
          <div className="w-12 h-1 bg-brand-rose mx-auto" />
        </div>

        <div className="grid md:grid-grid-cols-3 gap-12">
          {[
            {
              icon: <ShieldCheck className="w-10 h-10 text-brand-rose" />,
              title: "정밀 진단",
              desc: "얼굴 골격과 미세한 근육의 움직임까지 정밀 분석합니다."
            },
            {
              icon: <UserCheck className="w-10 h-10 text-brand-rose" />,
              title: "Personalized Blueprint",
              desc: "오직 당신만을 위한 맞춤형 디자인을 제안합니다."
            },
            {
              icon: <Clock className="w-10 h-10 text-brand-rose" />,
              title: "프리미엄 케어",
              desc: "시간이 흘러도 변치 않는 아름다움을 설계합니다."
            }
          ].map((feature, idx) => (
            <div key={idx} className="p-8 bg-white rounded-2xl shadow-sm border border-gray-100 hover:shadow-md transition-shadow text-center">
              <div className="flex justify-center mb-6">{feature.icon}</div>
              <h3

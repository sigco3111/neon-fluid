# 🌊 neon-fluid

> HTML5 Canvas API 기반 형광 입자 유체 역학 시뮬레이션

3,000개 이상의 형광색 입자가 마우스 커서에 유기적으로 반응하며, 충돌 물리·속도/밀도 기반 색상 그라데이션·블랙홀 흡입 효과를 갖춘 60fps 인터랙티브 데모입니다.

[🇰🇷 한국어 (기본)](#) · [🇺🇸 English](./README.en.md)

---

## 🤖 생성 정보 (Attribution)

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**되었습니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | [`sigco3111/neon-fluid`](https://github.com/sigco3111/neon-fluid) |
| **라이선스** | MIT |
| **의존성** | 없음 (Vanilla JS, 단일 HTML) |

### 📝 사용된 프롬프트 (원문)

```
HTML5 Canvas API만을 사용하여 마우스 커서의 움직임에 따라 3,000개 이상의 형광색 입자들이
유기적으로 반응하며 흩어지는 고성능 유체 역학 시뮬레이션을 구현해줘.
입자들 간의 충돌 물리 엔진이 적용되어야 하고, 입자의 속도와 밀도에 따라 색상이
실시간으로 그라데이션되면서 마우스를 클릭하면 블랙홀처럼 빨려 들어가는
시각적으로 매혹적인 60프레임 애니메이션 코드를 작성해줘.
Implementation Advice: Use HTML5 Canvas API for high-performance 2D rendering.
For 3,000+ particles with collision detection, implement a Quadtree or
Spatial Hash Grid to optimize checks. Use requestAnimationFrame for the loop.
모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## ✨ 주요 특징 (Features)

- 🎨 **3,000+ 입자** — Spatial Hash Grid로 충돌 최적화
- 🖱️ **마우스 인터랙션** — hover 반발 + click 블랙홀 흡입
- 🌈 **실시간 그라데이션** — 속도·밀도에 따른 HSL 색상 변환
- ⚡ **60fps 안정** — `requestAnimationFrame` 루프 + 캔버스 최적화
- 📦 **단일 HTML** — 외부 의존성 0개, 파일 하나만 열면 실행
- 🔒 **온디바이스** — 모든 렌더링·물리가 브라우저 안에서 처리됨

---

## 🚀 실행 방법 (Quick Start)

### 방법 1: 그냥 브라우저로 열기 (가장 간단)
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

### 방법 2: 로컬 서버 (권장)
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

### 방법 3: 라이브 데모 (Vercel)
배포 후 URL이 발급되면 별도 설치 없이 바로 확인 가능합니다.

---

## 🎮 조작법 (Controls)

| 입력 | 효과 |
|---|---|
| **마우스 이동** | 커서 주변 입자가 부드럽게 반발 |
| **마우스 클릭 (홀드)** | 블랙홀처럼 입자 흡입 |
| **마우스 떼기** | 입자가 자연스럽게 퍼져나감 |

---

## 🛠️ 기술 스택 (Tech Stack)

| 영역 | 사용 기술 |
|---|---|
| **렌더링** | HTML5 Canvas 2D Context |
| **물리** | 자체 충돌 엔진 (Spatial Hash Grid) |
| **색상** | HSL 실시간 보간 |
| **루프** | `requestAnimationFrame` |
| **의존성** | 없음 (Vanilla JS) |

---

## 📂 프로젝트 구조

```
neon-fluid/
├── index.html      # 단일 HTML (모든 코드 포함)
├── README.md       # 한국어 (기본)
├── README.en.md    # English (옵션)
└── LICENSE         # MIT
```

---

## 🎨 디자인 결정 (Design Choices)

브레인스토밍 단계에서 내린 결정 4가지:

| 결정 포인트 | 선택 | 이유 |
|---|---|---|
| **배경/톤** | 딥 우주 다크 (`#0a0a14`~`#000`) | 형광 발광 효과 극대화 |
| **인터랙션 깊이** | 3단 (반발 + 흡입 + 폭발) | 클릭 만족감 극대화 |
| **물리 최적화** | Spatial Hash Grid + 3,000 입자 | Quadtree 대비 단순, 60fps 안정 |
| **색상 팔레트** | 네온 시안-마젠타-옐로우 3색 | 속도·밀도별 HSL 보간 |

### 직접 커스터마이즈하고 싶다면

`index.html` 상단에서 다음 상수를 조정하면 분위기를 바꿀 수 있어요:

```js
const CONFIG = {
  PARTICLE_COUNT: 3000,        // 입자 수 (성능 트레이드오프)
  CELL_SIZE: 32,               // Spatial Hash 셀 크기
  HOVER_RADIUS: 80,            // 커서 반발 반경
  BLACKHOLE_STRENGTH: 0.5,     // 흡입 강도
  // ... 더 많은 옵션은 코드 내 주석 참조
};
```

고급 사용자용: 직접 `SpatialHashGrid` 클래스를 교체해 Quadtree로 바꿔볼 수도 있어요.

---

## 🗺️ 로드맵 (Roadmap)

- [ ] **v0.2** — 마우스 우클릭 폭발 인터랙션 추가
- [ ] **v0.3** — 입자 트레일(trail) 효과
- [ ] **v0.4** — 모바일 터치 인터랙션 (pinch/zoom)
- [ ] **v1.0** — WebGL 버전 (10,000+ 입자 목표)
- [ ] **v1.1** — 음성 입력 → 입자 패턴 생성

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

이 프로젝트는 [MiniMax-M3](https://example.com) 모델과 OpenCode CLI 환경에서 생성되었습니다. 프롬프트 엔지니어링과 디자인 결정은 저장소 소유자가 직접 수행했습니다.
# 🌊 neon-fluid

> HTML5 Canvas API 기반 형광 입자 유체 역학 시뮬레이션

3,000개 이상의 형광색 입자가 마우스 커서에 유기적으로 반응하며, 충돌 물리·속도/밀도 기반 색상 그라데이션·블랙홀 흡입 효과를 갖춘 60fps 인터랙티브 데모입니다.

---

## 🤖 생성 정보 (Attribution)

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**되었습니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | `sigco3111/neon-fluid` |

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

## ✨ 주요 특징

- 🎨 **3,000+ 입자** — Spatial Hash Grid로 충돌 최적화
- 🖱️ **마우스 인터랙션** — hover 반발 + click 블랙홀 흡입
- 🌈 **실시간 그라데이션** — 속도·밀도에 따른 HSL 색상 변환
- ⚡ **60fps 안정** — `requestAnimationFrame` 루프 + 캔버스 더블 버퍼링
- 📦 **단일 HTML** — 외부 의존성 0개, 파일 하나만 열면 실행

---

## 🚀 실행 방법

```bash
# 그냥 브라우저로 열기
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

또는 라이브 서버:
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

---

## 🎮 조작법

| 입력 | 효과 |
|---|---|
| **마우스 이동** | 커서 주변 입자가 반발 |
| **마우스 클릭 (홀드)** | 블랙홀처럼 입자 흡입 |
| **마우스 떼기** | 입자가 자연스럽게 퍼져나감 |

---

## 🛠️ 기술 스택

- **렌더링**: HTML5 Canvas 2D Context
- **물리**: 자체 충돌 엔진 (Spatial Hash Grid)
- **색상**: HSL 실시간 보간
- **루프**: `requestAnimationFrame`
- **의존성**: 없음 (Vanilla JS)

---

## 📜 License

MIT
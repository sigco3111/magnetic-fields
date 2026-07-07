# 🧲 Magnetic Fields

> HTML5 Canvas 기반 자기장 벡터장 시뮬레이터

N극과 S극을 가진 막대자석 여러 개를 드래그 배치하면, 수천 개의 미세한 철가루 입자가 자기장 선(Magnetic Field Lines)을 따라 실시간으로 정렬하고 이동하며 쌍곡선 형태의 아름다운 패턴을 그려냅니다.

[🇰🇷 한국어 (기본)](#) · [🇺🇸 English](./README.en.md)

---

## 🎬 라이브 데모

> **👉 [https://magnetic-fields.vercel.app/](https://magnetic-fields.vercel.app/)** — 브라우저에서 바로 실행

| | |
|---|---|
| ![Live](https://img.shields.io/badge/Live-Demo-7C3AED?style=for-the-badge&logo=vercel&logoColor=white) | [![Repo](https://img.shields.io/badge/GitHub-sigco3111%2Fmagnetic--fields-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/magnetic-fields) |
| ![Status](https://img.shields.io/badge/Status-Live-22C55E?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-0-9CA3AF?style=flat-square) |

### ⚡ 빠른 사용법
1. 위 데모 링크 클릭 → 브라우저에서 페이지 열기
2. **A 키** — 화면 중앙에 새 자석 추가
3. **마우스 드래그** — 자석 위치 이동
4. **R 키** — 선택된 자석 15° 회전 (Shift+R = 반대 방향)
5. **+/- 키** — 철가루 입자 수 조절 (500~8,000)

---

## 🤖 생성 정보

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**되었습니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | [`sigco3111/magnetic-fields`](https://github.com/sigco3111/magnetic-fields) |
| **라이선스** | MIT |
| **의존성** | 없음 (Vanilla JS, 단일 HTML) |

### 📝 사용된 프롬프트 (원문)

```
화면에 N극과 S극을 가진 막대자석 여러 개를 드래그하여 배치할 수 있고,
그 주변에 수천 개의 미세한 철가루 입자들이 자기장 선(Magnetic Field Lines)을 따라
실시간으로 정렬하고 이동하는 모습을 쌍곡선 형태의 아름다운 패턴으로 시각화해줘.
Implementation Advice: Use HTML5 Canvas. The physics is Vector Field calculation.
For each particle, calculate the force vector sum from all poles
(N repel, S attract). Rotate the particle sprite to align with the field vector.
모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## ✨ 주요 특징

- 🧲 **드래그 자석 시스템** — N극 빨강 / S극 파랑 막대자석을 자유 배치 + 회전 + 삭제
- ✨ **수천 개 철가루 입자** — 기본 3,500개, 500~8,000 조절 가능
- 🌊 **벡터장 시뮬레이션** — 각 입자가 모든 극의 힘을 합산해 자기장 선 따라 정렬
- 🔄 **실시간 회전 정렬** — 입자 sprite가 자기장 벡터 방향에 맞춰 회전
- 🎨 **쌍곡선 패턴** — N↔S 극 사이가 닭살 모양의 아름다운 곡선 무늬로 시각화
- 📦 **단일 HTML** — 외부 의존성 0개, 26KB 파일 하나만 열면 실행
- 🌐 **L 키 다국어 토글** — UI 라벨을 한국어 ↔ English 즉시 전환

---

## 🚀 실행 방법

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

### 방법 3: 라이브 데모
위 Vercel alias URL에서 바로 확인 가능합니다.

---

## 🎮 조작법

| 입력 | 효과 |
|---|---|
| **A 키** | 화면 중앙에 새 자석 추가 |
| **마우스 드래그** | 자석 위치 이동 |
| **마우스 우클릭 드래그** | 자석 회전 |
| **R 키** | 선택된 자석 15° 회전 (Shift+R = -15°) |
| **Delete / Backspace** | 선택된 자석 삭제 |
| **C 키** | 모든 자석 제거 |
| **Space** | 일시정지 / 재개 |
| **+/- 키** | 입자 수 500 단위 조절 (500~8,000) |
| **T 키** | 트레일 효과 on/off |
| **L 키** | UI 언어 한국어 ↔ English 토글 |

---

## 🛠️ 기술 스택

| 영역 | 사용 기술 |
|---|---|
| **렌더링** | HTML5 Canvas 2D Context (`desynchronized: true`) |
| **물리** | 자체 벡터장 계산 (`Σ F = K·q·(±)/r^α`) |
| **루프** | `requestAnimationFrame` |
| **DPR** | 최대 2x (고해상도 디스플레이 대응) |
| **의존성** | 없음 (Vanilla JS) |

### 핵심 사양

| 상수 | 값 | 의미 |
|---|---|---|
| `PARTICLE_COUNT` | 3,500 | 기본 입자 수 |
| `MAX_PARTICLES` | 8,000 | 최대 입자 수 |
| `MIN_PARTICLES` | 500 | 최소 입자 수 |
| `MAX_MAGNETS` | 8 | 화면에 배치 가능한 자석 최대 개수 |
| `MAGNET_LEN` | 120 px | 자석 길이 |
| `MAGNET_WIDTH` | 22 px | 자석 두께 |
| `K` | 1,800 | 자기장 강도 |
| `ALPHA` | 1.5 | 거리 감쇠 지수 (1/r^α) |
| `EPS²` | 900 | 소프트닝 (단위 거리 제곱) |
| `DAMPING` | 0.90 | 입자 속도 감쇠 |
| `BASE_SPEED` | 1.4 | 접선 방향 표류 속도 |

---

## 📂 프로젝트 구조

```
magnetic-fields/
├── index.html      # 단일 HTML (모든 코드 포함, ~26KB)
├── README.md       # 한국어 (기본)
├── README.en.md    # English
└── LICENSE         # MIT
```

---

## 🎨 디자인 결정

브레인스토밍 단계에서 내린 결정 5가지:

| 결정 포인트 | 선택 | 이유 |
|---|---|---|
| **물리 모델** | 벡터장 (`Σ F`) 직접 계산 | 자기장 선의 쌍곡선 형태가 자연스럽게 emergent |
| **거리 감쇠** | `1/r^1.5` (ALPHA=1.5) | 표준 1/r²보다 멀리까지 영향, 시각적으로 균형 |
| **소프트닝** | `EPS² = 900` (≈30px²) | 자석 표면에서 발산 방지 (numerical stability) |
| **회전 정렬** | 입자 sprite가 field vector에 맞춰 회전 | 실제 철가루의 자기 정렬 메커니즘 시각화 |
| **단일 HTML + 외부 의존성 0개** | 순수 Canvas + Vanilla JS | 어디서든 즉시 실행, 빌드 단계 없음 |

### 직접 커스터마이즈하고 싶다면

`index.html` 상단의 `CONFIG` 객체 상수를 조정하면 물리적 분위기와 시각 효과가 바뀝니다:

```js
const CONFIG = Object.freeze({
  PARTICLE_COUNT:  3500,   // 기본 입자 수 (성능 트레이드오프)
  K:               1800,   // 자기장 강도 (높을수록 극 근처 격렬)
  ALPHA:           1.5,    // 거리 감쇠 지수 (높을수록 가까운 극만 영향)
  DAMPING:         0.90,   // 입자 감쇠 (1.0 = 무감쇠)
  BASE_SPEED:      1.4,    // 접선 표류 속도
  FADE_ALPHA:      0.10,   // 트레일 페이드 강도 (낮을수록 긴 꼬리)
  // ... 더 많은 옵션은 코드 내 주석 참조
});
```

고급 사용자용: `EPS²`를 0에 가깝게 두면 자석 표면에서 폭발적인 패턴이 나타나고, 매우 크게 두면 부드러운 그라데이션 형태가 됩니다.

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

이 프로젝트는 [MiniMax](https://example.com) 의 MiniMax-M3 모델과 OpenCode CLI 환경에서 생성되었습니다. 프롬프트 엔지니어링과 디자인 결정은 저장소 소유자가 직접 수행했습니다.
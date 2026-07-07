# 🧲 Magnetic Fields — 자기장과 철가루 시뮬레이터

> **물리 기반 자기장 시각화** — N극과 S극 막대자석 여러 개를 드래그 배치하고, 수천 개의 철가루 입자가 자기장 선(Magnetic Field Lines)을 따라 실시간으로 정렬하며 쌍곡선 패턴을 그려내는 인터랙티브 데모.

---

## 🎮 핵심 기능 (예정)

- 🧲 **드래그 가능한 막대자석** — N극/S극을 가진 막대자석을 마우스로 자유 배치
- ✨ **수천 개 철가루 입자** — 각 입자가 모든 극(N은 반발, S는 흡인)으로부터 힘 벡터 합산
- 🌊 **벡터장 시뮬레이션** — 쌍곡선 형태의 자기장 선을 따라 입자 정렬 + 이동
- 🎨 **실시간 회전 정렬** — 입자 sprite가 자기장 벡터 방향에 맞춰 회전
- 📦 **단일 HTML** — Canvas + 자체 물리, 의존성 0개

---

## 🤖 생성 정보

이 프로젝트는 **OpenCode CLI**에서 **MiniMax-M3 (미니맥스) 모델**과 다음 프롬프트를 사용해 생성됩니다.

### 사용된 프롬프트

> 화면에 N극과 S극을 가진 막대자석 여러 개를 드래그하여 배치할 수 있고, 그 주변에 수천 개의 미세한 철가루 입자들이 자기장 선(Magnetic Field Lines)을 따라 실시간으로 정렬하고 이동하는 모습을 쌍곡선 형태의 아름다운 패턴으로 시각화해줘.
>
> **Implementation Advice**: Use HTML5 Canvas. The physics is Vector Field calculation. For each particle, calculate the force vector sum from all poles (N repel, S attract). Rotate the particle sprite to align with the field vector. 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.

### 생성 환경

| 항목 | 값 |
|---|---|
| **Agent** | OpenCode CLI |
| **LLM Model** | MiniMax-M3 (MiniMax) |
| **렌더링** | HTML5 Canvas 2D |
| **물리** | 자체 벡터장 계산 (Vector Field) |
| **배포 형태** | 단일 HTML 파일 (`index.html`) |

---

## 🛠️ 기술 스택 (예정)

- **HTML5 Canvas 2D Context** — 고성능 2D 렌더링
- **Vanilla JavaScript** — 프레임워크 의존성 없음
- **Vector Field Physics** — 자기장 힘 벡터 합산 (`Σ F = k·(±q)/r²`)
- **requestAnimationFrame** — 메인 루프

---

## 🚀 실행 방법 (코드 완성 후)

```bash
git clone https://github.com/sigco3111/magnetic-fields.git
cd magnetic-fields
open index.html        # macOS
```

---

## 📁 프로젝트 구조

```
magnetic-fields/
├── README.md      ← 지금 보고 있는 파일
└── index.html     ← 게임 전체 (구현 예정)
```

---

## 📝 라이선스

MIT
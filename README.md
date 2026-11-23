# 강남 스윙 (Gangnam Swing)

강남역 주변 실제 지도 데이터 위에서 양손 줄을 쏘아 빌딩 사이를 날아다니는 브라우저 3D 게임입니다.

**▶ 플레이: https://isif-3.github.io/gangnam-swing/**

설치 없이 브라우저(Chrome 권장)에서 바로 실행됩니다.

## 조작법

| 입력 | 동작 |
|---|---|
| `W` `A` `S` `D` | 이동 / 공중에서 방향·균형 |
| `Space` | 점프 |
| `Shift` | 달리기 |
| 좌클릭 | 왼손 줄 발사 (누르고 있으면 매달림, 떼면 놓음) |
| 우클릭 | 오른손 줄 발사 |
| `V` | 3인칭 / 1인칭 시점 전환 |
| 방향키 | 시야 회전 (보조) |
| `R` | 시작 위치로 |
| `Esc` | 일시정지 · 설정 |

설정 메뉴에서 줄 발사 속도, 최대 사거리, 연결 시 당김, 탄성, 중력, 공중 제어력, 마우스 감도, 시야각을 조절할 수 있습니다.

마우스 고정(pointer lock)을 지원하지 않는 환경에서는 자동으로 "마우스 고정 없음 모드"로 실행됩니다. 이 모드에서는 마우스를 화면 가장자리로 밀거나 방향키로 시야를 돌립니다.

## 지도 데이터

- 강남역 주변 약 1.5km × 1.5km 영역의 건물 외곽선과 도로를 [OpenStreetMap](https://www.openstreetmap.org/)에서 가져왔습니다 (스냅샷: 2026-11-23).
- 높이(`height`)나 층수(`building:levels`) 정보가 있는 건물은 그 값을 쓰고, 없는 건물은 바닥 면적에 따라 랜덤 높이(시드 고정)로 채웁니다.
- 좌표는 강남역을 원점으로 한 미터 단위입니다 (`+x` 동쪽, `+z` 남쪽).

## 로컬에서 실행

```powershell
powershell -ExecutionPolicy Bypass -File serve.ps1
```

실행 후 브라우저에서 http://localhost:8765 를 엽니다. three.js를 CDN에서 불러오므로 인터넷 연결이 필요합니다.

## 파일 구성

- `index.html` — 게임 본체 (three.js 0.160)
- `city_data.js` — OpenStreetMap에서 변환한 건물·도로 데이터
- `serve.ps1` — 로컬 테스트용 간단한 정적 파일 서버

## 라이선스

- 코드: [MIT](LICENSE)
- 지도 데이터(`city_data.js`): © OpenStreetMap contributors, [Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/)

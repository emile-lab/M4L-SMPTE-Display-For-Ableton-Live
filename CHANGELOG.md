# 변경 내역 · Changelog

## Beta 0.2 — 2026-10-06

### 새 기능 · 개선
- **영상 창과 타임코드의 ±1 프레임 차이 해결.** 정지하거나 클릭한 위치가 프레임 경계에 걸리면, Live 영상 창이 이전 프레임이나 다음 프레임을 보여 주는 경우가 있었습니다. 이제 재생 헤드를 같은 프레임 안에서 아주 조금(최대 반 프레임) 옮겨, 영상 창과 SMPTE 표시가 항상 같은 프레임을 가리킵니다. 시작 마커와 Undo 기록은 바뀌지 않습니다.
- **`clip off frame grid` 표시 추가.** 영상 클립이 프레임 경계 사이에 놓여 있으면 정보 줄에 알려 줍니다. 스냅을 켜고 클립을 격자에 맞추면 사라집니다.
- 번인 타임코드 인식 도구(`bitc_reader`) 업데이트.

### 문서
- 설치 안내를 3단계로 정리하고, 다운로드한 파일의 macOS 보안 격리 해제 방법을 추가했습니다. 이 단계를 건너뛰면 번인 타임코드 인식이 동작하지 않습니다.
- 영문 안내서 추가, 라이선스 명시.

### 검증
- Ableton Live 12.4.5 / Max 9.1.5 / macOS 15.7 (Apple Silicon)에서 자동 테스트 136개 통과. 실제 Live의 영상 창을 캡처해 비교한 결과, 영상 3종 60개 지점에서 불일치가 없었습니다.

### What's new (English)
- **Fixed ±1 frame difference between Live's video window and the timecode.** When the playhead stopped exactly on a frame boundary, Live's video window could show the neighbouring frame. The playhead is now nudged within the same frame (at most half a frame) so both always match. Start marker and Undo history are untouched.
- **New `clip off frame grid` notice** when a video clip sits between frame boundaries.
- Updated burned-in timecode reader (`bitc_reader`).
- Three-step install guide, including how to remove the macOS quarantine flag (required for burned-in timecode reading). English guide and license added.

---

## DEMO — 2026-10-06 (한정 배포 · limited release)

첫 공개 버전입니다.
- Arrangement View 플로팅 SMPTE 타임코드 창 (S / M / L / XL)
- 타임코드 입력으로 이동 (Enter), 이동 후 재생 (Space), 숫자만 입력 (`01101010`)
- 영상 클립 FPS 자동 감지 (MOV / MP4 / M4V)
- 영상 번인 타임코드(BITC) 인식으로 Offset 자동 설정, 재생 중 싱크 표시 (macOS)
- 템포 오토메이션 구간에서 정확한 표시와 이동
- Set 끝 너머로 이동하면 Set 자동 연장
- 지원 프레임레이트: 23.976 / 24 / 25 / 29.97 NDF·DF / 30 / 50 / 59.94 NDF·DF / 60

# Alarmy
기초 알람 앱 개발


# ⏰ 알람 앱 – 기능 명세서 (MVP)

## ✅ 프로젝트 개요

- 특정 요일과 시간에 반복 알람을 울리도록 설정 가능한 간단한 알람 앱
- 사용자 맞춤 벨소리 선택 기능 포함
- 웹 기반 MVP로 시작하며, 모바일 전환 고려 예정

---

## 🔧 핵심 기능 요약

| 기능명        | 설명 |
|---------------|------|
| 알람 생성     | 특정 시간, 요일, 벨소리를 지정해 반복 알람 생성 |
| 알람 목록 보기 | 등록된 알람들을 리스트 형식으로 출력 |
| 알람 삭제     | 개별 알람 삭제 기능 제공 |
| 알람 울림     | 정해진 시간에 알람이 울리도록 Notification API 활용 |
| 벨소리 선택   | 기본 제공되는 2~3가지 벨소리 중 선택 가능 |

---

## 🗃️ DB 구조 (Supabase 기준)

### Table: `alarms`

| 필드명       | 타입         | 설명 |
|--------------|--------------|------|
| `id`         | UUID         | 고유 ID (PK) |
| `user_id`    | UUID         | 사용자 식별자 (FK) |
| `time`       | TIME         | 알람 울릴 시간 |
| `repeat_days`| TEXT[]       | 반복 요일 (["Mon", "Tue", ...]) |
| `sound_name` | TEXT         | 벨소리 이름 |
| `is_active`  | BOOLEAN      | 활성/비활성 여부 |
| `created_at` | TIMESTAMP    | 생성 일시 |

---

## 🎵 벨소리 사양

- 벨소리 파일명 예: `default.mp3`, `soft.mp3`, `buzz.mp3`
- 로컬에서 제공하거나 CDN으로 호스팅

---

## ⚙️ 기술 스택

- **Frontend**: React + Tailwind CSS
- **Backend/DB**: Supabase
- **알림 기능**: Web Notification API (웹), react-native-push-notification (모바일 시)
- **배포**: Vercel

---

## 📌 향후 확장 가능 기능 (MVP 이후)

- 알람 수정 기능
- 요일별 알람 ON/OFF 토글
- 수면 시간 분석 연동
- 앱 내 챌린지 기능 (예: 알람 연속 출석 체크)

---

## 📂 프로젝트 구조 (예시)


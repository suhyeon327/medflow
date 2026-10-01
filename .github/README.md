# MedFlow

## 소개

병원과 의사 탐색부터 진료 예약, 사전 문진, 의료진의 문진 확인까지 하나의 흐름으로 연결한 진료 예약 웹 애플리케이션입니다.

환자는 예약한 진료의 문진을 미리 작성하고 AI 분석 결과를 확인할 수 있습니다. 의사는 담당 예약과 문진의 요약, 주요 소견, 주의 신호를 확인해 진료를 준비합니다. 관리자는 병원과 의사 승인, 사용자 및 예약 현황을 관리합니다.

AI는 진단이나 처방을 내리지 않습니다. 환자가 작성한 내용을 의료진이 검토하기 쉽도록 구조화하는 진료 보조 기능으로 사용합니다.

<br>

## 기술 스택

| Category | Technologies |
|---|---|
| **Backend** | ![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat&logo=springboot&logoColor=white) |
| **Frontend** | ![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white) |
| **AI** | ![Gemini](https://img.shields.io/badge/Gemini%20API-8E75B2?style=flat&logo=googlegemini&logoColor=white) |
| **Database** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white) |
| **Infrastructure** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white) ![AWS EC2](https://img.shields.io/badge/AWS%20EC2-FF9900?style=flat&logo=amazonec2&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white) |

<br>

## 시스템 아키텍처
<img width="630" height="472" alt="medflow drawio (2)" src="https://github.com/user-attachments/assets/c51f4229-b9f4-4cd1-944a-c14da0429559" />

<br>

## 실행 방법

### 1. Repository Clone

```bash
git clone https://github.com/suhyeon327/medflow.git
cd medflow
```

### 2. 환경변수 설정

프로젝트 루트의 .env.example 파일을 복사해 .env 파일을 생성하고 필요한 값을 설정합니다.

```bash
cp .env.example .env
```
| 환경변수 | 설명 |
| --- | --- |
| `DB_URL` | MySQL Connection URL |
| `DB_USERNAME` | MySQL 사용자 이름 |
| `DB_PASSWORD` | MySQL 비밀번호 |
| `JWT_SECRET` | JWT 서명에 사용하는 Secret Key |
| `GEMINI_API_KEY` | Gemini API 인증 키 |
| `ADMIN_BOOTSTRAP_ENABLED` | 관리자 초기 계정 생성 여부 |

### 3. 전체 서비스 실행

프로젝트 루트에서 다음 명령어를 실행합니다.

```bash
docker compose up -d --build
```

Docker Compose를 통해 다음 서비스가 함께 실행됩니다.

- MySQL
- Spring Boot Backend
- React Frontend

## 4. 실행 확인

```
http://localhost/hospitals
```

## 5. 서비스 종료

```bash
docker compose down
```

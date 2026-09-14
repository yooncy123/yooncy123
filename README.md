<div align="center">

# 윤채영 · Backend Developer

**서비스의 흐름을 이해하고, 문제의 원인을 찾아 개선합니다.**

Java와 Spring으로 백엔드를 개발하며,<br>
검색·캐싱·AI 응답을 실제 서비스에 연결하는 경험을 쌓고 있습니다.

<p>
  <img src="https://img.shields.io/badge/Java-303030?style=flat-square" alt="Java">
  <img src="https://img.shields.io/badge/Spring_Boot-303030?style=flat-square" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Spring_AI-FF6500?style=flat-square" alt="Spring AI">
  <img src="https://img.shields.io/badge/Backend-FF6500?style=flat-square" alt="Backend">
</p>

[Portfolio](https://canva.link/ns76qiarw66cnyy) · [Email](mailto:yeori21@naver.com) · [GitHub](https://github.com/yooncy123)

</div>

---

## About me

안녕하세요, 백엔드 개발자 **윤채영**입니다.

새로운 기술을 배우고 서비스에 적용하는 과정에서 즐거움을 느낍니다. 팀원의 좋은 설계와 구현을 관찰하고, 그 이유를 이해해 제 작업에도 적용하려고 노력합니다.

- **업무 규칙을 코드로 옮깁니다.** 회원 재인증, 구매 이력 기반 등급 갱신, 프로젝트 멤버 검사와 같은 서비스 규칙을 구현했습니다.
- **데이터를 가져오는 과정도 살핍니다.** 불필요한 연관 조회를 줄이고, 검색 결과를 결합하거나 재사용하는 방법을 고민했습니다.
- **AI가 서비스 맥락에 맞게 응답하도록 설계합니다.** 환경 정보와 ML 추천을 행동 가이드로 전달하고, 도구 선택 가이드를 통해 적절한 호출을 유도했습니다.

🎓 조선대학교 컴퓨터공학과 졸업 · 2026.02

## Tech stack

프로젝트에서 직접 사용한 기술입니다.

| 분야 | 기술 |
| :--- | :--- |
| **Backend** | Java · Spring Boot · Spring Data JPA · QueryDSL |
| **AI & Search** | Spring AI · Gemini · MCP Tool · PostgreSQL / pgvector |
| **Data & Storage** | MySQL · PostgreSQL · Redis · MinIO |
| **Service & Web** | Spring Cloud Gateway · Spring Scheduler · Thymeleaf · HTML / CSS |
| **Tools** | Git · GitHub · IntelliJ IDEA |

## Selected projects

| 프로젝트 | 서비스 | 담당 영역 |
| :--- | :--- | :--- |
| **01 · 4IREN** | 강의실 환경 관리 AIoT 플랫폼 | AI 채팅 · 웰컴 브리핑 |
| **02 · AI Library** | 도서관 조회 및 AI 추천 서비스 | 하이브리드 검색 · 시맨틱 캐싱 · MCP Tool |
| **03 · Mini Dooray!** | 프로젝트 협업 및 일정 관리 | 게이트웨이 · 업무 CRUD · 프론트 |
| **04 · Bean Solid** | 도서 쇼핑몰 | 회원 관리 · 리뷰 · 이미지 연동 |

### 01 · 4IREN 
[관련 노션](https://4iren.notion.site/4-iren-395f42d4653280aeb412f3dcec27aa77)

> 환경 데이터와 ML 추천을 사용자가 실행할 수 있는 행동 가이드로 연결하는 AIoT 플랫폼

**2026.07–09 · 9인 팀 프로젝트**  
`Spring Boot` `Spring AI` `Gemini`

강의실 환경 데이터를 수집·검증하고, 공간별 AI 판단과 맞춤 알림을 제공하는 서비스입니다.

**담당 및 구현**

- Spring AI와 Gemini를 활용한 **AI 채팅·웰컴 브리핑**을 구현했습니다.
- ML 추천과 실시간 환경 정보를 결합해 **냉난방·환기 행동 가이드**를 자연어로 전달했습니다.
- 공간의 상황을 바탕으로 사용자가 어떤 행동을 취하면 좋을지 안내하도록 응답을 구성했습니다.

<details>
<summary><strong>트러블슈팅 · 실제 기기 작동 이력 부족</strong></summary>

| 단계 | 내용 |
| :--- | :--- |
| **문제** | 실제 기기의 ON/OFF 로그가 없어 행동 예측 모델의 학습 데이터가 부족했습니다. |
| **해결** | 공간별 사용 패턴을 반영한 기기 제어 시뮬레이터를 구축하고 작동 이력을 축적했습니다. |
| **결과** | 부족했던 기기 작동 이력을 보완해 행동 예측 모델 학습에 활용할 데이터를 확보했습니다. |


</details>

---

### 02 · AI Library

> 키워드 검색과 의미 검색을 결합한 도서관 조회 및 AI 추천 서비스

**2026.06–07 · 4인 팀 프로젝트**  
`Java 21` `Spring Boot 3.5` `Spring AI` `PostgreSQL` `pgvector` `Redis`

**담당 및 구현**

- **하이브리드 검색:** 키워드 검색과 벡터 검색을 `CompletableFuture`로 병렬 실행하고, RRF로 검색 순위를 결합했습니다.
- **시맨틱 캐싱:** 질의 벡터와 검색 결과를 저장하고, 새 질의와의 코사인 유사도를 비교해 유사 질의의 결과를 재사용했습니다.
- **MCP Tool:** 도서 검색 기능을 AI가 활용할 수 있도록 구현했습니다.

<details>
<summary><strong>트러블슈팅 · N+1 조회와 잘못된 도구 호출</strong></summary>

**임베딩 대상 조회의 N+1**  
책 조회 시 불필요한 연관 엔티티가 함께 조회됐습니다. 관계 매핑을 조정하고 필요한 필드만 Projection으로 조회하도록 변경했습니다.

**LLM의 잘못된 MCP Tool 호출**  
도구와 인자를 잘못 선택하는 상황을 확인했습니다. 프롬프트와 검색 DTO에 도구 선택 가이드를 명시해 의도에 맞는 호출을 유도했습니다.

**남겨둔 과제**  
전체 벡터를 비교하는 KNN의 비용을 줄이기 위해 HNSW를 검토했지만, 공용 DB의 메모리 제약으로 인덱스를 생성하지 못했습니다. 별도 DB 환경에서 재검증할 과제로 남겼습니다.

</details>

---

### 03 · Mini Dooray!

> 프로젝트·업무·마일스톤을 관리하는 협업 일정 관리 서비스

**2026.05 · 4인 팀 프로젝트**  
`Java 21` `Spring Boot` `Spring Cloud Gateway` `Spring Data JPA` `MySQL` `Thymeleaf`

**담당 및 구현**

- **게이트웨이 서버**를 구축하고 URL 패턴에 따라 계정·업무 API로 요청을 전달했습니다.
- **업무 관련 CRUD와 프론트**를 구현했습니다.
- 프로젝트 멤버 검사와 마일스톤 진척률·상태 갱신 규칙을 서비스 계층에 적용했습니다.

<details>
<summary><strong>설계 경험 · 서비스 분리와 업무 규칙</strong></summary>

서비스는 `front` · `gateway` · `account-api` · `task-api`로 분리했습니다.

| 요청 | 전달 대상 |
| :--- | :--- |
| `/user/**` · `/login` · `/signup` | Account API |
| `/projects/**` | Task API |

업무 CRUD에서는 비즈니스 로직과 트랜잭션 처리를 고려하고, 완료 태스크 수를 집계해 마일스톤 진척률과 상태를 갱신했습니다.

**남겨둔 과제**  
게이트웨이는 라우팅까지 구현했습니다. 이중화와 가중치 기반 로드밸런싱은 구현하지 않았으며, 팀 회고에서는 프론트·게이트웨이 테스트 보강과 API 문서화 필요성도 확인했습니다.

</details>

---

### 04 · Bean Solid

> 회원 관리부터 구매 후 리뷰까지 이어지는 도서 쇼핑몰

**2025.06–07 · 7인 팀 프로젝트**  
`Java 21` `Spring Boot` `JPA` `QueryDSL` `MySQL` `MinIO` `Spring Scheduler`

**담당 및 구현**

- **회원 관리·리뷰 기능의 백엔드와 프론트**를 구현했습니다.
- 회원 정보·비밀번호 변경 시 재인증, 회원별 주소 10개 제한, 구매 이력 기반 회원 등급 자동 갱신을 구현했습니다.
- 리뷰 작성·수정과 이미지 표시를 구현하고, MinIO 이미지 URL을 리뷰 정보에 연결했습니다.

<details>
<summary><strong>트러블슈팅 · 이미지 업로드와 저장소 정합성</strong></summary>

| 문제 | 해결 |
| :--- | :--- |
| **Multipart 전송 오류** | 이미지를 먼저 업로드하고, 반환된 URL을 리뷰 DTO에 포함해 등록하도록 흐름을 분리했습니다. |
| **리뷰 등록 실패 후 남는 파일** | DB 이미지 목록과 MinIO 객체를 주기적으로 비교해 DB에 없는 파일을 정리했습니다. |
| **Mixed Content로 이미지 차단** | HTTPS 프록시 컨트롤러가 내부 MinIO 이미지를 가져와 전달하도록 수정했습니다. |

**다음 개선 과제**  
프록시 응답 캐싱의 효과를 검증하고, 회원 등급 갱신의 트랜잭션 롤백 범위와 배치 처리를 검토하고자 합니다.

</details>

---

<div align="center">

**프로젝트의 시연 화면과 자세한 설명은 포트폴리오에서 확인할 수 있습니다.**

[포트폴리오 보기](https://canva.link/ns76qiarw66cnyy) · [연락하기](mailto:yeori21@naver.com)

</div>

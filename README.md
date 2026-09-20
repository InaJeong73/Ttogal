# TtoGal · Backend

**카드 수집형 맛집 탐색 서비스의 백엔드 개발 기록**

`Java 17` · `Spring Boot 3.4.0` · `Spring Security` · `JPA` · `MySQL` · `Redis`

창업동아리 Stack 팀 프로젝트의 [TtoGal/backend](https://github.com/TtoGal/backend)에서 fork한 저장소입니다. 서비스 전체 기획과 현재 공개 코드의 구현 범위를 구분합니다.

## 현재 코드에서 볼 수 있는 기능

| 영역 | 구현 | 코드 |
| --- | --- | --- |
| 회원 | 가입·로그인·조회, 이메일·닉네임 검증, 토큰 재발급 | [UserController](backend/src/main/java/com/ttogal/api/controller/user/UserController.java) |
| 이메일 | 인증메일 발송·검증 | [EmailController](backend/src/main/java/com/ttogal/api/controller/email/EmailController.java) |
| 인증·설정 | JWT, 보안, Redis·메일 설정 | [common](backend/src/main/java/com/ttogal/common) |

카드 수집·맛집 탐색의 전체 기능이 이 브랜치에서 완성되었다는 의미는 아닙니다.

## 프로젝트 구조

Gradle 애플리케이션은 `backend/` 아래에 있습니다. `api`는 컨트롤러·서비스, `domain`은 엔티티·저장소, `common`은 공통 설정을 담습니다.

## 실행 조건

```bash
git clone https://github.com/InaJeong73/Ttogal.git
cd Ttogal/backend
./gradlew bootRun
```

Windows는 `.\gradlew.bat bootRun`을 사용합니다. JDK 17, DB·Redis·SMTP 및 JWT 설정을 별도로 준비해야 합니다. 현재 실행용 설정 파일은 저장소에 포함되어 있지 않습니다.

주요 설정은 `jwt.*`, `mail.*`, `mail.data.redis.host/port`, `spring.datasource.*`입니다. 세부 이름은 설정 클래스와 `@Value` 선언을 기준으로 확인합니다. 명령만으로 즉시 실행되는 상태를 보장하지 않습니다.

## 후속 정리 후보

개인 개발용 설정 예제, 이메일 인증 실패·만료 테스트, 토큰 갱신 테스트를 보강할 수 있습니다. 원본 작성자와 팀 기여 이력은 커밋에 보존합니다.

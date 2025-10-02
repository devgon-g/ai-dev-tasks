## 관련 파일

- `build.gradle` - 플러그인, 의존성, 저장소, 빌드 작업을 구성하는 루트 Gradle 빌드 스크립트(Groovy DSL).
- `settings.gradle` - Gradle 빌드를 위한 프로젝트 이름과 모듈 구조를 정의.
- `gradle/wrapper/gradle-wrapper.properties` - 일관된 빌드를 위해 사용할 Gradle 배포판 버전을 고정.
- `src/main/java/com/example/Application.java` - `main` 메서드를 포함한 Spring Boot 진입점.
- `src/main/resources/application.yml` - 환경별 속성을 정의하는 중앙 구성 파일.
- `src/test/java/com/example/ApplicationTests.java` - 애플리케이션 컨텍스트 로드를 보장하는 기본 테스트.
- `README.md` - 부트스트랩 절차와 개발자 온보딩 메모를 정리.

### 참고 사항

- Gradle 작업은 macOS/Linux에서는 `./gradlew <task>`, Windows에서는 `gradlew.bat <task>`로 실행.
- 패키지 이름은 합의된 기본 패키지와 일치시켜 컴포넌트 스캐닝 문제를 방지.
- 팀이 Groovy DSL을 사용하므로 빌드 스크립트는 `build.gradle`, `settings.gradle` 형식을 유지.
- 새로운 기여자가 쉽게 적응할 수 있도록 사용자 정의 Gradle 작업이나 프로필은 `README.md`에 바로 기록.

## 작업

- [ ] 1.0 사전 준비 확인
  - [ ] 1.1 Java 18(또는 프로젝트 표준)이 설치되어 있고 `PATH`에 등록되어 있는지 확인.
  - [ ] 1.2 Git, Gradle 래퍼 실행 권한, 선호 IDE가 Spring Boot Java 개발을 지원하는지 검증.
  - [ ] 1.3 프로젝트 루트 디렉터리를 만들고 빈 Git 저장소 초기화.
- [ ] 2.0 기본 Spring Boot 프로젝트 생성
  - [ ] 2.1 Spring Initializr(CLI 또는 웹)을 사용해 `java` 언어와 목표 Java 버전을 갖춘 Spring Boot Gradle 프로젝트를 스캐폴딩.
  - [ ] 2.2 핵심 의존성 추가: `spring-boot-starter-web`, `spring-boot-starter-actuator`, `spring-boot-starter-test`.
  - [ ] 2.3 그룹을 `com.solomonm`(조직 네임스페이스에 맞춰 조정)로 설정하고 아티팩트를 프로젝트 이름과 일치시킴.
  - [ ] 2.4 Gradle Groovy DSL이 선택되어 있는지 확인하고 생성된 프로젝트를 저장소 루트에 압축 해제 또는 다운로드.
- [ ] 3.0 빌드 및 의존성 관리 구성
  - [ ] 3.1 `settings.gradle`을 최종 프로젝트 이름으로 업데이트.
  - [ ] 3.2 `build.gradle`의 플러그인 섹션을 검토하고 팀 표준에 따라 Lombok 등 필요한 플러그인을 추가.
  - [ ] 3.3 저장소(Maven Central, 사내 미러)와 의존성 버전을 필요하면 `ext` 또는 버전 카탈로그로 중앙 관리.
  - [ ] 3.4 프로젝트 관례에 따라 QA/도구 의존성(`spring-boot-starter-validation`, `springdoc-openapi`, `spotless` 플러그인 등) 추가.
  - [ ] 3.5 `./gradlew build`를 실행해 의존성이 해결되고 프로젝트가 컴파일되는지 확인.
- [ ] 4.0 애플리케이션 구조 정립
  - [ ] 4.1 기본 패키지(예: `com.example.app`)를 만들고 `Application` 클래스를 `src/main/java`로 이동.
  - [ ] 4.2 `/healthz`에 정적 JSON을 응답하는 샘플 REST 컨트롤러(`HealthController`) 추가.
  - [ ] 4.3 기본 서버 포트, 액추에이터 노출 설정, 프로필 스캐폴드(`spring.profiles.active` 자리표시자)를 포함하도록 `application.yml` 구성.
  - [ ] 4.4 로깅 패턴과 기본 로깅 레벨을 `INFO`로 설정(팀 선호에 맞게 조정).
- [ ] 5.0 테스트 및 품질 게이트
  - [ ] 5.1 `ApplicationTests`를 업데이트해 컨텍스트 로드와 헬스 엔드포인트의 HTTP 200 응답을 검증.
  - [ ] 5.2 테스트 라이브러리(JUnit 5, AssertJ, MockMvc 등)에 대한 의존성 관리를 필요 시 추가.
  - [ ] 5.3 `./gradlew test`를 실행하여 테스트 스위트가 통과하는지 확인.
  - [ ] 5.4 CI 친화적 Gradle 작업(예: `check` 종합 작업)을 구성하고 명령을 `README.md`에 기록.
- [ ] 6.0 개발자 경험 향상
  - [ ] 6.1 프로젝트 설정 단계, 필요 도구, 자주 사용하는 Gradle 명령을 `README.md`에 문서화.
  - [ ] 6.2 IDE 파일, 빌드 산출물, OS별 임시 파일을 제외하도록 `.gitignore` 항목 추가.
  - [ ] 6.3 팀이 핫 리로드를 기대한다면 Spring Boot devtools 또는 라이브 리로드 구성.
  - [ ] 6.4 IDE 가져오기(IntelliJ/VS Code) 안내를 검증하고 로컬 실행 및 디버깅 팁을 추가.
- [ ] 7.0 최종 검증
  - [ ] 7.1 `./gradlew bootRun`으로 애플리케이션을 실행하고 헬스 엔드포인트 응답을 확인.
  - [ ] 7.2 구성에 따라 액추에이터 엔드포인트(예: `/actuator/health`)가 접근 가능한지 검증.
  - [ ] 7.3 Initializr가 제공한 사용하지 않는 샘플 코드를 제거하며 저장소 구조를 검토.
  - [ ] 7.4 초기 프로젝트 스캐폴드를 명확한 메시지(예: `chore: initialize spring boot gradle project`)로 커밋.

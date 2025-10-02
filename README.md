# AI Dev Tasks 소개

**AI Dev Tasks**에 오신 것을 환영합니다! 이 저장소는 AI 기반 IDE와 CLI와 함께 기능 개발 워크플로를 극대화할 수 있도록 설계된 마크다운 파일 모음입니다. 원래는 [Cursor](https://cursor.sh/)를 위해 만들어졌지만, Claude Code, Windsurf 등 모든 AI 코딩 어시스턴트에서 활용할 수 있습니다. 구조화된 프롬프트를 활용하면 아이디어 발굴부터 구현까지 체계적으로 기능을 구축하고, 검증을 위한 체크포인트를 내장한 상태로 진행할 수 있습니다.

크고 모호한 AI 요청과 씨름하는 대신, AI 협업자를 한 단계씩 안내해 보세요!

## 핵심 아이디어

AI로 복잡한 기능을 구축하는 일은 때로 블랙박스처럼 느껴질 수 있습니다. 이 워크플로는 다음과 같은 방식으로 과정에 구조와 명확성, 통제를 가져오는 것을 목표로 합니다.

1. **범위 정의:** 제품 요구 사항 문서(PRD)를 통해 구축해야 하는 내용을 명확하게 규정합니다.
2. **세부 계획:** PRD를 세분화된 실행 가능한 작업 목록으로 분해합니다.
3. **반복적 구현:** AI가 한 번에 하나씩 작업을 수행하도록 안내하고, 매번 변경 사항을 검토‧승인할 수 있게 합니다.

이런 구조화된 접근 방식은 AI가 방향을 잃지 않도록 돕고, 문제를 더 쉽게 디버그할 수 있게 하며, 생성된 코드에 대한 신뢰도를 높여 줍니다.

## 워크플로: 아이디어에서 구현된 기능까지

이 저장소의 `.md` 파일을 사용하는 단계별 절차는 다음과 같습니다.

### 1️⃣ 제품 요구 사항 문서(PRD) 만들기

먼저 기능에 대한 청사진을 작성하세요. PRD는 무엇을, 누구를 위해, 왜 구축하는지를 명확히 해 줍니다.

선호하는 AI 도구에서 바로 가벼운 PRD를 작성할 수 있습니다.

1. 이 저장소의 `create-prd.md` 파일을 준비합니다.
2. AI 도구에서 PRD 생성을 시작합니다.

    ```text
    Use @create-prd.md
    Here's the feature I want to build: [Describe your feature in detail]
    Reference these files to help you: [Optional: @file1.py @file2.ts]
    ```
    *(팁: Cursor 사용자라면 예산이 허용된다면 복잡한 PRD에는 MAX 모드를 사용하는 것이 좋습니다.)*

    ![PRD 생성 시작 예시](https://pbs.twimg.com/media/Go6DDlyX0AAS7JE?format=jpg&name=large)

### 2️⃣ PRD에서 작업 목록 생성하기

PRD를 작성했다면(예: `MyFeature-PRD.md`), 이제 AI 개발자를 위한 세부 구현 계획을 만들어야 합니다.

1. `generate-tasks.md` 파일을 준비합니다.
2. AI 도구에서 PRD를 활용해 작업을 만듭니다.

    ```text
    Now take @MyFeature-PRD.md and create tasks using @generate-tasks.md
    ```
    *(참고: `@MyFeature-PRD.md`를 1단계에서 생성한 실제 PRD 파일명으로 바꾸세요.)*

    ![PRD에서 작업 생성 예시](https://pbs.twimg.com/media/Go6FITbWkAA-RCT?format=jpg&name=medium)

### 3️⃣ 작업 목록 검토하기

이제 작업 및 하위 작업이 포함된 잘 구조화된 목록을 갖게 됩니다. 이는 구현을 위한 명확한 로드맵을 제공합니다.

![생성된 작업 목록 예시](https://pbs.twimg.com/media/Go6GNuOWsAEcSDm?format=jpg&name=medium)

### 4️⃣ AI에 작업 수행 지시(완료 표시 포함)

체계적인 진행과 검증을 위해 `process-task-list.md`를 사용합니다. 이 명령은 AI가 한 번에 하나씩 작업을 수행하고 다음 작업으로 넘어가기 전에 당신의 승인을 기다리도록 합니다.

1. `process-task-list.md` 파일을 준비합니다.
2. AI 도구에서 첫 번째 작업(예: `1.1`)부터 시작하도록 지시합니다.

    ```text
    Please start on task 1.1 and use @process-task-list.md
    ```
    *(중요: 첫 번째 작업에 대해서만 `@process-task-list.md`를 참조하면 됩니다. 이후 작업에 대한 지침은 해당 파일 안에 포함되어 있습니다.)*

    AI는 작업을 시도한 뒤 검토를 요청합니다.

    ![process-task-list.md를 사용해 작업 시작 예시](https://pbs.twimg.com/media/Go6I41KWcAAAlHc?format=jpg&name=medium)

### 5️⃣ 검토, 승인, 진행

AI가 각 작업을 완료할 때마다 변경 사항을 검토합니다.

* 변경 사항이 만족스럽다면 “yes” 등으로 답해 작업을 완료 처리하고 다음 작업으로 넘어가도록 지시합니다.
* 수정이 필요하다면 현재 작업을 수정하도록 피드백을 제공합니다.

완료된 항목이 늘어나는 모습을 보면서 기능이 눈앞에서 구현되는 과정을 확인할 수 있습니다!

![완료된 항목이 표시된 작업 목록 예시](https://pbs.twimg.com/media/Go6KrXZWkAA_UuX?format=jpg&name=medium)

이 방식이 완벽하진 않더라도, AI를 활용해 큰 기능을 구축할 때 매우 신뢰할 수 있는 방법임이 입증되었습니다.

### 영상 데모

이 워크플로가 실제로 어떻게 작동하는지 보고 싶다면 [Claire Vo의 "How I AI" 팟캐스트](https://www.youtube.com/watch?v=fD4ktSkNCw4)에서 시연한 내용을 참고하세요.

![How I AI 팟캐스트에서 AI Dev Tasks 시연](https://img.youtube.com/vi/fD4ktSkNCw4/maxresdefault.jpg)

## 저장소의 파일

* **`create-prd.md`**: 새로운 기능에 대한 제품 요구 사항 문서를 생성하도록 AI를 안내합니다.
* **`generate-tasks.md`**: PRD 마크다운 파일을 입력으로 받아 세부적이고 단계적인 구현 작업 목록을 만들도록 돕습니다.
* **`process-task-list.md`**: 생성된 작업 목록을 처리하면서 한 번에 하나의 작업에 집중하고, 다음 단계로 넘어가기 전 승인 여부를 확인하도록 AI를 지시합니다. (작업 완료 표시 로직도 포함)

## 주요 이점

* **구조화된 개발:** 아이디어부터 코드까지 명확한 프로세스를 강제합니다.
* **단계별 검증:** 각 작은 단계마다 AI가 생성한 코드를 검토하고 승인할 수 있어 품질과 통제를 확보합니다.
* **복잡성 관리:** 큰 기능을 더 작고 다루기 쉬운 작업으로 분해해 AI가 길을 잃거나 지나치게 복잡하고 잘못된 코드를 생성할 가능성을 줄여 줍니다.
* **향상된 신뢰도:** 하나의 거대한 프롬프트에 의존하는 것보다, AI를 활용한 본격적인 개발 작업에 더 믿음직한 접근 방식을 제공합니다.
* **명확한 진행 상황 추적:** 완료된 작업을 시각적으로 표시해 현재 진행 상황을 한눈에 파악할 수 있도록 합니다.

## 사용 방법

1. **클론 또는 다운로드:** `.md` 파일을 프로젝트나 AI 도구가 접근할 수 있는 중앙 위치에 가져옵니다.
   ```bash
   git clone https://github.com/snarktank/ai-dev-tasks.git
   ```
2. **워크플로 따르기:** 앞서 설명한 방식대로 AI 어시스턴트에서 `.md` 파일을 순차적으로 활용합니다.
3. **적응 및 반복:**
    * 필요에 따라 `.md` 파일 안의 프롬프트를 사용자 환경이나 코딩 스타일에 맞게 수정하세요.
    * AI가 특정 작업에서 어려움을 겪는다면 초기 기능 설명을 바꾸거나 작업을 더 세분화해 보세요.

## 도구별 안내

### Cursor

Cursor 사용자는 에이전트 채팅에서 `.md` 파일을 바로 활용하며 다음과 같이 진행할 수 있습니다.

1. 이 저장소의 파일을 준비합니다.
2. Cursor 에이전트 채팅에서 `@`로 파일을 참조합니다(예: `@create-prd.md`).
3. 위에 소개한 5단계 워크플로를 그대로 따릅니다.
4. **PRD를 위한 MAX 모드:** 예산이 허용한다면 PRD 생성 시 MAX 모드를 사용하면 더 완성도 높은 결과를 얻을 수 있습니다.

### Claude Code

Claude Code에서 이 도구들을 사용하려면 다음 단계를 따르면 됩니다.

1. **파일 복사:** 세 개의 `.md` 파일을 프로젝트의 하위 디렉터리(예: `/ai-dev-tasks`)에 복사합니다.

2. **CLAUDE.md에서 참조:** 프로젝트의 `./CLAUDE.md` 파일에 다음 내용을 추가합니다.
   ```
   # AI Dev Tasks
   Use these files when I request structured feature development using PRDs:
   /ai-dev-tasks/create-prd.md
   /ai-dev-tasks/generate-tasks.md
   /ai-dev-tasks/process-task-list.md
   ```

3. **사용자 정의 명령 만들기** (선택 사항): 접근성을 높이기 위해 `.claude/commands/` 디렉터리에 다음 파일을 만듭니다.
   - `.claude/commands/create-prd.md`
     ```
     Please use the structured workflow in /ai-dev-tasks/create-prd.md to help me create a PRD for a new feature.
     ```
   - `.claude/commands/generate-tasks.md`
     ```
     Please generate tasks from the PRD using /ai-dev-tasks/generate-tasks.md
     If not explicitly told which PRD to use, generate a list of PRDs and ask the user to select one under `/tasks` or create a new one using `create-prd.md`:
     - assume it's stored under `/tasks` and has a filename starting with `[n]-prd-` (e.g., `0001-prd-[name].md`)
     - it should not already have a corresponding task list in `/tasks` (e.g., `tasks-0001-prd-[name].md`)
     - **always** ask the user to confirm the PRD file name before proceeding
     Make sure to provide options in number lists so I can respond easily (if multiple options).
     ```
   - `.claude/commands/process-task-list.md`
     ```
     Please process the task list using /ai-dev-tasks/process-task-list.md
     ```

   파일을 추가한 후 Claude Code를 재시작(`/exit`)하세요.
   그런 다음 `/create-prd` 같은 명령으로 워크플로를 빠르게 시작할 수 있습니다.
   이 구성은 전체 프로젝트에 적용할 수도 있으며, 관련해서는 Claude Code 문서의 [이곳](https://docs.anthropic.com/en/docs/claude-code/memory)과 [이곳](https://docs.anthropic.com/en/docs/claude-code/common-workflows#create-personal-slash-commands)을 참고하세요.

### 기타 도구

다른 AI 기반 IDE나 CLI에서는 다음과 같이 활용하세요.

1. `.md` 파일을 프로젝트에 복사합니다.
2. 각 도구의 문서에 따라 파일을 참조합니다.
3. 동일한 워크플로 원칙을 따릅니다.

## 성공을 위한 팁

* **구체적으로:** 초기 기능 설명과 추가 지침을 명확하게 전달할수록 AI가 더 좋은 결과를 제공합니다.
* **능력 있는 모델 사용:** Cursor의 무료 버전은 구조화된 지시를 따라가는 데 어려움을 겪는 경우가 많습니다. 안정적인 작업 수행을 위해서는 Pro 플랜을 고려해 보세요.
* **PRD 제작 시 MAX 모드:** 앞서 언급했듯, 예산이 허용한다면 PRD 생성(`create-prd.mdc`)에 MAX 모드를 사용하면 더 세밀하고 높은 품질의 결과를 얻을 수 있습니다.
* **파일 태깅 정확성:** 작업을 생성할 때는 PRD 파일명(예: `@MyFeature-PRD.md`)을 정확히 태깅하세요.
* **인내와 반복:** AI는 강력한 도구지만 만능은 아닙니다. 안내하고, 수정하고, 반복할 준비를 하세요. 이 워크플로는 이러한 반복 과정을 더 원활하게 돕도록 설계되었습니다.

## 기여

이 `.md` 파일들을 개선하거나 워크플로에 맞는 새로운 아이디어가 있다면 환영합니다!

다음과 같이 참여해 주세요.

* 변경 사항을 논의하거나 신규 기능을 제안하려면 이슈를 열어 주세요.
* 개선 내용을 담은 풀 리퀘스트를 보내 주세요.

---

즐거운 AI 지원 개발 되시길 바랍니다!

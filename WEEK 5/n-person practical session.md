## 요약
# Pull Request 기초 (Pull Request Fundamentals)

## 📋 학습 개요

### 강의 목표
- Pull Request의 개념과 필요성을 이해한다
- GitHub의 Fork, Pull Request, Merge 흐름을 이해한다
- 실제 협업 시나리오에서 PR을 작성하고 처리할 수 있다
- Upstream과 Origin의 차이를 명확히 이해한다

***

## 1️⃣ Pull과 Push, Pull Request 이해

### Git과 GitHub 기능: Push와 Pull

#### 지역 저장소(Local Repository) 관점

```
┌─────────────────────────────────────────┐
│           LOCAL (Your Computer)          │
│                                          │
│           cool_repo                      │
│                                          │
│     Your computer talks to the           │
│     GitHub server with terminal          │
└─────────────┬──────────────┬─────────────┘
              │              │
              │ Push         │ Pull
              ↓              ↑
┌─────────────────────────────────────────┐
│           REMOTE (GitHub Server)         │
│                                          │
│     Repositories live on a GitHub        │
│     server (우리 수업과 같은 저장소)     │
│                                          │
│           cool_repo                      │
└─────────────────────────────────────────┘
```

#### Push (원격 저장소로 올리기)
- **기능**: 로컬 저장소의 변경사항을 원격 저장소로 업로드
- **권한**: **권한이 있는 사용자만 가능**
- **명령어**: `git push origin main`

#### Pull (지역 저장소로 내리기)
- **기능**: 원격 저장소의 변경사항을 로컬 저장소로 다운로드
- **권한**: **주소를 아는 모든 사용자 접근 가능** (Public 저장소)
- **명령어**: `git pull origin main`

### 브라우저와 터미널의 역할

```
┌──────────────────────────────────────────┐
│        Browser (웹 브라우저)                │
│                                          │
│  - Browser lets you access repository    │
│  - Send changes back to the server       │
└──────────────────────────────────────────┘

┌──────────────────────────────────────────┐
│        Terminal (터미널/Git Bash)          │
│                                          │
│  - Your computer talks to the GitHub     │
│    server with terminal                  │
│  - git push, git pull 명령 실행            │
└──────────────────────────────────────────┘
```

***

## 2️⃣ GitHub에서의 Origin과 Upstream

### 원격 서버(Remote)가 2개인 경우

#### Upstream (상류 저장소)
- **정의**: 오픈소스(프로젝트) 또는 타인의 원본 저장소
- **예시**: `atom/atom`, `ai7dnn/pr-train`
- **역할**: 원본 프로젝트의 최신 상태를 유지하는 메인 저장소

#### Origin (또는 Remote)
- **정의**: Upstream을 내 계정으로 Fork한 자신의 저장소
- **예시**: `me/atom`, `chatkang/pr-train`
- **역할**: 개인 작업 공간, PR을 위한 중간 저장소

### 구조 다이어그램

```
┌─────────────────────────────────────────┐
│         UPSTREAM (원본 저장소)           │
│                                          │
│         maintainer                       │
│         atom/atom                        │
│         ai7dnn/pr-train                  │
└─────────────┬───────────────────────────┘
              │
              │ Fork
              ↓
┌─────────────────────────────────────────┐
│         ORIGIN (Fork된 저장소)            │
│                                         │
│         me/atom                         │
│         chatkang/pr-train               │
└─────────────┬───────────────────────────┘
              │
              │ Clone
              ↓
┌─────────────────────────────────────────┐
│         LOCAL (로컬 저장소)                │
│                                         │
│         내 컴퓨터의 작업 폴더                │
└─────────────────────────────────────────┘
```

### 주요 작업 흐름

```
UPSTREAM ← fetch (최신 코드 가져오기)
   ↓
ORIGIN ← push (내 작업 올리기)
   ↓
LOCAL (코드 작성 및 커밋)
```

***

## 3️⃣ 다른 사용자 저장소, 오픈소스에 기여

### 프로젝트 기여(Contribution)의 종류

#### 기여의 정의
- 저장소(오픈소스)에 도움이 될만한 **모든 활동**
- 기능 제안 및 추가
- 기존 소스의 버그를 수정
- 여러 다양한 방법의 기여

### 오픈소스 기여 방안 (레벨별)

#### 초급: 오픈소스 공부를 시작했을 경우

**번역 작업에 기여**
- 오픈소스에서 영문으로 작성된 README 파일의 **한국어 번역**에 기여
- 접근성 향상, 커뮤니티 확대

**예시**:
```markdown
# Original README.md
## Installation
Run `npm install` to install dependencies.

# Translated README.ko.md (기여)
## 설치 방법
의존성을 설치하려면 `npm install`을 실행하세요.
```

#### 중급: 프로젝트를 어느 정도 이해하고 있는 경우

**문서화 작업에 기여**
- API 문서 작성
- 사용 가이드 작성
- 예제 코드 추가

**오타 및 번역 수정**
- 소스나 문서의 **오타 수정**
- **잘못 번역된 한글 수정**

**예시**:
```markdown
# Before (오타)
This funtion calculates the sum.

# After (수정)
This function calculates the sum.
```

#### 고급: 오픈소스를 깊이 알고 있는 경우

**기능과 버그 수정에 기여**
- **소스 코드 수정**에 기여
- 오픈소스의 **버그를 찾고 수정**
- **추가 기능 제안**과 코드 제안 및 추가

**예시**:
```python
# Before (버그)
def divide(a, b):
    return a / b  # ZeroDivisionError 가능

# After (수정)
def divide(a, b):
    if b == 0:
        raise ValueError("Division by zero is not allowed")
    return a / b
```

### 기여 활동의 가치

- 오픈소스 생태계 발전
- 개인 포트폴리오 구축
- 협업 경험 축적
- 코드 리뷰 능력 향상

***

## 4️⃣ Pull Request란?

### PR의 정의

**Pull Request (PR)**
- 간단히 PR, 우리말로는 **"수정 요청"**, **"끌기 요청"**
- 수정 권한이 없는 타인의 오픈소스(저장소)에 저장소 수정 등의 **기여 요청을 하는 알림**

### PR의 핵심 개념

#### 프로젝트 수행 시 개발자로서 코드 수정을 알림
- 저장소 소유자(또는 관리자) 관점에서, 소유자에게 **"수정 내용의 pull 요청"**하는 작업
- 기여자의 수정 내용을 **가져와(pull)** 소유자의 저장소에 **병합(merge)**하는 작업을 요청

⭐ **중요**: PR에서의 pull은 원격과 지역 개념을 떠나서 **기여자(또는 개발자)의 수정 등의 기여를 가져와 반영(병합)하는 것**을 말함

### PR의 주체

#### PR 작성자 (기여자)
- 개발자(또는 팀원), 기여자
- Developer

#### PR 검토자 (관리자)
- 프로젝트 관리자
- Code Owner
- 제안된 PR 검토와 병합 담당

### PR 생성 방법

- **Upstream을 Fork**하거나 **직접 수정**해서 PR 가능
- **PR 승인이 없으면** 계속 수정해서 다시 PR 요청

***

## 5️⃣ PR(Pull Request) 처리 과정

### 전체 워크플로우

```
┌─────────────────────────────────────────┐
│           기여자 관점                      │
└─────────────────────────────────────────┘
      1. Fork (New Branch)
              ↓
      2. Discussion, develop
              ↓
      3. Commit
              ↓
      4. Pull Request
              ↓
      5. Sync (병합 후)

┌─────────────────────────────────────────┐
│           관리자 관점                      │
└─────────────────────────────────────────┘
      1. Request review
              ↓
      2. Discussion
              ↓
      3. Code review and discussions
              ↓
      4. Accept PR
              ↓
      5. Merge
```

### 시각적 흐름도

```
Master Branch
    │
    ├─────────────────────────────────────→ (계속 개발)
    │                                           ↓
    │                                        Merge
Branch starts here
    │
    ├──→ First commits
    │         ↓
    ├──→ Pull Request
    │         ↓
    │    Code review and
    │    discussions
    │         ↓
    └──→ Merge (병합 완료)
```

### 단계별 상세 설명

#### 1단계: Fork (기여자)
- Upstream 저장소를 자신의 계정으로 복제
- 독립적인 작업 환경 생성

#### 2단계: Discussion, Develop (기여자)
- 이슈 확인 및 논의
- 로컬에서 코드 작성 및 테스트

#### 3단계: Commit (기여자)
- 변경사항을 커밋
- 명확한 커밋 메시지 작성

#### 4단계: Pull Request (기여자)
- Fork된 저장소에서 Upstream으로 PR 생성
- PR 제목과 설명 작성
- 관련 이슈 연결 (`#issue-number`)

#### 5단계: Request Review (관리자)
- PR 알림 수신
- 리뷰어 지정

#### 6단계: Discussion & Code Review (관리자 + 기여자)
- 코드 품질 검토
- 피드백 제공 및 수정 요청
- 기여자는 피드백에 따라 추가 커밋

#### 7단계: Accept PR & Merge (관리자)
- PR 승인
- Merge 실행
- 브랜치 삭제 (선택)

#### 8단계: Sync (기여자)
- Fork된 저장소를 Upstream과 동기화
- 최신 상태 유지

***

## 6️⃣ GUI GitHub로만 Pull Request 실습

### 실습 환경 설정

#### 두 개의 ID로 실습
- **기여자(팀원, 개발자)**: `chatkang` (파랑색)
- **관리자(PM, 팀장)**: `ai7dnn` (노란색)

#### 역할 분담

| 역할 | 계정 | 저장소 유형 | 수행 작업 |
|------|------|----------|----------|
| **관리자** | ai7dnn | Upstream | 저장소 생성, 이슈 생성, PR 검토 및 병합 |
| **기여자** | chatkang | Origin (Fork) | Fork, 파일 수정, Pull Request 생성 |

⭐ **실습 방법**: 짝 중에 한 명은 팀장(ai7dnn), 다른 한 명은 팀원(chatkang)으로 실습

***

## 7️⃣ Step 1: 팀장, Upstream 저장소 생성

### ai7dnn 계정으로 작업

#### GitHub에서 새 저장소 생성

```
GitHub → Repositories → New
```

#### 저장소 설정

**필수 입력 사항**:

| 항목 | 입력 값 | 설명 |
|------|---------|------|
| **Owner** | ai7dnn | 저장소 소유자 |
| **Repository name** | PR-train | 저장소 이름 |
| **Description** | PR 연습 저장소 | 설명 (선택) |
| **Visibility** | ⭕ Public | 공개 저장소 |
| **Initialize** | ✅ Add a README file | README 파일 포함 |
| **.gitignore template** | Python | Python 프로젝트용 |
| **License** | MIT License | MIT 라이선스 |

#### 생성 완료 화면

```
ai7dnn / PR-train

<> Code    Issues    Pull requests    Actions    Projects    Security    Insights

PR-train Public
main ▾    1 branch    0 tags

.gitignore        Initial commit
LICENSE           Initial commit
README.md         Initial commit

About
PR 연습 저장소

🌟 0 stars    👁 1 watching    🔱 0 forks
```

***

## 8️⃣ Step 2: 팀원, Remote 저장소 Fork

### chatkang 계정으로 작업

#### 1단계: Upstream 저장소 접속

```
https://github.com/ai7dnn/PR-train
```

#### 2단계: Fork 버튼 클릭

```
ai7dnn / PR-train

[Fork] 버튼 클릭 (우측 상단)
```

#### 3단계: Fork 설정

**Create a new fork 화면**:

```
Owner *
chatkang ▼

Repository name *
PR-train
✔ PR-train is available.

Description (optional)
PR 연습 저장소

✅ Copy the main branch only
   Contribute back to ai7dnn/PR-train by adding your own branch.

[Create fork] 버튼 클릭
```

⭐ **중요**: "Copy the main branch only" 체크 시 main 브랜치만 복사 (권장)

#### 4단계: Fork 완료 확인

```
chatkang / PR-train
forked from ai7dnn/PR-train

This branch is up to date with ai7dnn:main.

About
PR 연습 저장소
```

***

## 9️⃣ Step 3: 팀장, Upstream에 이슈 생성

### ai7dnn 계정으로 작업

#### 1단계: Issues 탭 이동

```
ai7dnn / PR-train

<> Code    [Issues]    Pull requests    Actions
```

⭐ **참고**: 팀장의 저장소(`ai7dnn/PR-train`)에서는 이슈가 보이며, 누구나 이슈 생성 가능하나, **Forked된 저장소**(`chatkang/PR-train`)에서는 **이슈 자체가 안 보임**

#### 2단계: New Issue 클릭

```
Issues → [New Issue] 버튼 클릭
```

#### 3단계: 이슈 작성

**이슈 내용**:

```
Title:
코드를 작성하세요!

Description:
기여할 수 있는 코드를 작성해 주세요~~~
```

**추가 설정**:
- **Assignees**: No one (또는 자신 지정)
- **Labels**: None yet
- **Projects**: None yet
- **Milestone**: No milestone

#### 4단계: 이슈 생성

```
[Create] 버튼 클릭
```

#### 이슈 생성 완료

```
ai7dnn / PR-train

Issues (1)

⭕ 코드를 작성하세요! #1
   opened 1 minute ago by ai7dnn
```

***

## 🔟 Step 4: 팀원, Upstream 이슈 확인

### chatkang 계정으로 작업

#### Upstream 저장소에서 이슈 확인

```
https://github.com/ai7dnn/PR-train/issues
```

**Issues 화면**:

```
ai7dnn / PR-train

Issues    1 Open    0 Closed

⭕ 코드를 작성하세요! #1
   opened 1 minute ago by ai7dnn
```

⭐ **안내**: Want to contribute to ai7dnn/PR-train?
- If you have a bug or an idea, browse the open issues before opening a new one.
- You can also take a look at the Open Source Guide.

***

## 1️⃣1️⃣ Step 5: 팀원, Forked 저장소에서 코드 작성

### chatkang 계정으로 작업

#### 1단계: 자신의 Fork 저장소로 이동

```
https://github.com/chatkang/PR-train
```

#### 2단계: 파일 생성

```
chatkang / PR-train

[Add file] ▾ → Create new file
```

#### 3단계: 파일 작성

**파일 경로 및 이름**:
```
code/hello.py
```

**파일 내용**:
```python
print('Hello Pull Request')
```

#### 4단계: 커밋

**Commit 메시지**:
```
Create hello.py
```

**Commit 설정**:
- ⭕ Commit directly to the main branch

```
[Commit new file] 버튼 클릭
```

#### 5단계: 파일 생성 확인

```
chatkang / PR-train

code/
  hello.py    Create hello.py    now

파일 내용:
1  print('Hello Pull Request')
```

***

## 1️⃣2️⃣ Step 6: 팀원, Pull Request 생성

### chatkang 계정으로 작업

#### 1단계: PR 알림 확인

**메인 저장소 화면**:

```
chatkang / PR-train
forked from ai7dnn/PR-train

This branch is 1 commit ahead of ai7dnn:main.

[Contribute] ▾    [Sync fork] ▾
```

⭐ **의미**: Fork한 저장소가 Upstream보다 1개 커밋 앞서 있음

#### 2단계: Contribute 버튼 클릭

```
[Contribute] ▾ → Open pull request
```

**안내 메시지**:
```
This branch is 1 commit ahead of ai7dnn:main.

Open a pull request to contribute your changes upstream.

[Open pull request] 버튼 클릭
```

#### 3단계: PR 작성

⭐ **중요**: 주소가 팀장(Upstream)의 주소로 바뀌어서 작업이 됨

```
https://github.com/ai7dnn/PR-train/compare/main...chatkang:PR-train:main
```

**Comparing changes 화면**:

```
base repository: ai7dnn/PR-train     base: main
    ←
head repository: chatkang/PR-train ▾  compare: main ▾

✓ Able to merge. These branches can be automatically merged.
```

**PR 제목 및 설명**:

```
Title:
Create hello.py #1

Description:
create hello.py
```

⭐ **팁**: 적정한 곳에 `#issue-number`를 삽입 (예: `#1`)하면 이슈와 자동 연결됨

**추가 설정**:
- ✅ Allow edits by maintainers (권장)

**커밋 정보**:
```
1 commit
Commits on Oct 3, 2023

Create hello.py
chatkang committed 4 minutes ago    Verified 0aff7f3
```

**변경된 파일**:
```
Showing 1 changed file with 1 addition and 0 deletions.

code/hello.py    +1 -0

@@ -0,0 +1 @@
+ print('Hello Pull Request')
```

#### 4단계: PR 생성

```
[Create pull request] 버튼 클릭
```

***

## 1️⃣3️⃣ Step 7: 팀원, PR 작성 성공 확인

### chatkang 계정으로 작업

#### PR 생성 완료 화면

```
ai7dnn / PR-train

Pull requests (1)

Create hello.py #1  #2
Open    chatkang wants to merge 1 commit into ai7dnn:main from chatkang:main

Conversation (0)    Commits (1)    Checks (0)    Files changed (+1 -0)
```

**PR 설명**:
```
chatkang commented now

create hello.py

Create hello.py    Verified 0aff7f3
```

**PR 상태**:
- ✅ This branch has no conflicts with the base branch
- ⚠️ Only those with write access to this repository can merge pull requests.

**추가 작업 안내**:
```
Add more commits by pushing to the main branch on chatkang/PR-train.

Still in progress? [Convert to draft]
```

**사이드바 정보**:
- **Reviewers**: No reviews
- **Assignees**: No one assigned
- **Labels**: None yet
- **Projects**: None yet
- **Milestone**: No milestone
- **Development**: Successfully merging this pull request may close these issues. None yet

⭐ **옵션**:
- ✅ Allow edits by maintainers (유지)

***

## 1️⃣4️⃣ Step 8: 팀장, Upstream에서 PR 확인

### ai7dnn 계정으로 작업

#### 1단계: Pull requests 탭 확인

```
ai7dnn / PR-train

<> Code    Issues (1)    [Pull requests (1)]    Actions
```

#### 2단계: PR 목록 확인

```
Pull requests

1 Open    0 Closed

⭕ Create hello.py #1  #2
   chatkang wants to merge 1 commit into ai7dnn:main from chatkang:main
   opened 3 minutes ago by chatkang    First-time contributor
```

⭐ **참고**: "First-time contributor" 배지가 표시됨

***

## 1️⃣5️⃣ Step 9: 팀장, PR 내용 확인 후 병합

### ai7dnn 계정으로 작업

#### 1단계: PR 상세 보기

```
ai7dnn / PR-train

Pull requests → Create hello.py #1  #2
```

#### 2단계: PR 내용 검토

**Conversation 탭**:
```
chatkang commented 3 minutes ago

create hello.py

Create hello.py    Verified 0aff7f3
```

**Files changed 탭**:
```
Showing 1 changed file with 1 addition and 0 deletions.

code/hello.py    +1 -0

@@ -0,0 +1 @@
+ print('Hello Pull Request')
```

#### 3단계: 병합 준비 확인

**Branch 상태**:
```
✅ This branch has no conflicts with the base branch
   Merging can be performed automatically.
```

**CI/CD 상태** (선택):
```
⚠️ Continuous integration has not been set up
   GitHub Actions and several other apps can be used to automatically 
   catch bugs and enforce style.
```

**Branch Protection** (선택):
```
Require approval from specific reviewers before merging
Branch protection rules ensure specific people approve pull requests 
before they're merged.

[Add rule]
```

#### 4단계: Merge Pull Request

```
[Merge pull request] 버튼 클릭
```

**Merge 확인 화면**:
```
Merge pull request #2 from chatkang/main

Create hello.py
```

**Merge 옵션**:
- ⭕ Create a merge commit
- ⭕ Squash and merge
- ⭕ Rebase and merge

```
[Confirm merge] 버튼 클릭
```

⭐ **이후 작업**: Confirm 버튼도 클릭

#### 5단계: Merge 완료 확인

```
✅ Pull request successfully merged and closed

chatkang's commits are now part of ai7dnn:main

You can safely delete the chatkang:main branch.

[Delete branch] (선택 사항)
```

***

## 1️⃣6️⃣ Step 10: 팀장, PR 병합 확인

### ai7dnn 계정으로 작업

#### 저장소 메인 화면 확인

```
ai7dnn / PR-train

<> Code    Issues (1)    Pull requests (0)

PR-train Public
main ▾    1 branch    0 tags

code/                Create hello.py        11 minutes ago
.gitignore           Initial commit         27 minutes ago
LICENSE              Initial commit         27 minutes ago
README.md            Initial commit         27 minutes ago
```

⭐ **결과**: 팀원이 작성한 `code/` 폴더가 보임

#### 파일 내용 확인

```
ai7dnn / PR-train / code / hello.py

chatkang    Create hello.py    0aff7f3    11 minutes ago

1  print('Hello Pull Request')
```

***

## 1️⃣7️⃣ Step 11: 팀원, Remote에서 PR 병합 확인

### chatkang 계정으로 작업

#### 자신의 Fork 저장소 확인

```
chatkang / PR-train
forked from ai7dnn/PR-train

This branch is 1 commit behind ai7dnn:main.
```

⭐ **의미**: 커밋의 수가 Upstream보다 하나 적음

#### Commits 비교

**Upstream (ai7dnn/PR-train)**:
```
Commits on Oct 3, 2023

Merge pull request #2 from chatkang/main    Verified 751d6fc
Create hello.py                             Verified 0aff7f3
Initial commit                              Verified dbd44e1

총 3개 커밋
```

**Remote (chatkang/PR-train)**:
```
Commits on Oct 3, 2023

Create hello.py                             Verified 0aff7f3
Initial commit                              Verified dbd44e1

총 2개 커밋
```

⭐ **분석**:
- Upstream에서 PR이 병합되어 **n회의 커밋 발생** (Merge commit 포함)
- Remote에서는 Upstream에서 PR이 병합된 커밋이 **반영되지 않아 n-1회의 커밋 발생**

***

## 1️⃣8️⃣ Step 12: 팀원, Sync Fork로 동기화

### chatkang 계정으로 작업

#### 1단계: Sync 알림 확인

```
chatkang / PR-train

This branch is 1 commit behind ai7dnn:main.

[Sync fork] ▾
```

#### 2단계: Sync fork 클릭

```
[Sync fork] ▾ → Update branch
```

**안내 메시지**:
```
This branch is out-of-date

Update branch to keep this branch up-to-date by syncing 1 commit 
from the upstream repository.

Learn more about syncing forks

[Compare]    [Update branch]
```

⭐ **기능**: Remote에서 Upstream과 동일하게 만듦

#### 3단계: Update branch 클릭

```
[Update branch] 버튼 클릭
```

#### 4단계: 동기화 완료 확인

```
chatkang / PR-train

This branch is up to date with ai7dnn:main.

✅ Successfully fetched and fast-forwarded from upstream ai7dnn:main.
```

#### 5단계: Commits 재확인

**동기화 후 (chatkang/PR-train)**:
```
Commits on Oct 3, 2023

Merge pull request #2 from chatkang/main    Verified 751d6fc
Create hello.py                             Verified 0aff7f3
Initial commit                              Verified dbd44e1

총 3개 커밋 (Upstream과 동일)
```

***

## 1️⃣9️⃣ Step 13: 팀장, 이슈 연결 확인

### ai7dnn 계정으로 작업

#### Issues 탭에서 이슈 확인

```
ai7dnn / PR-train

Issues (1)

⭕ 코드를 작성하세요! #1
   opened 27 minutes ago by ai7dnn    0 comments
```

#### 이슈 상세 보기

```
코드를 작성하세요! #1
Open    ai7dnn opened this issue 27 minutes ago · 0 comments

ai7dnn commented 27 minutes ago    Owner

코드 작성
```

**연결된 커밋**:
```
ai7dnn added a commit that referenced this issue 12 minutes ago

Merge pull request #2 from chatkang/main    Verified 751d6fc
```

⭐ **확인**: PR에서 `#1`을 언급했기 때문에 이슈와 자동으로 연결됨

**Development 섹션**:
```
Development

New issue
Create a branch for this issue or link a pull request.
```

***

## 📌 핵심 요약 (Summary)

### Pull Request 개념

#### Push vs Pull
- **Push**: 로컬 저장소 → 원격 저장소 (권한 필요)
- **Pull**: 원격 저장소 → 로컬 저장소 (누구나 가능)

#### Upstream vs Origin
- **Upstream**: 원본 저장소 (타인/오픈소스)
- **Origin**: Fork한 자신의 저장소

#### Pull Request (PR)
- 수정 권한이 없는 저장소에 기여를 요청하는 알림
- 기여자의 수정 내용을 가져와(pull) 병합(merge)하는 작업 요청

### PR 처리 흐름

```
1. Fork (기여자)
    ↓
2. 코드 작성 및 Commit (기여자)
    ↓
3. Pull Request 생성 (기여자)
    ↓
4. Code Review (관리자)
    ↓
5. Merge (관리자)
    ↓
6. Sync Fork (기여자)
```

### GitHub에서 PR 실습 단계

#### 관리자 (Upstream)
1. 저장소 생성 (`ai7dnn/PR-train`)
2. 이슈 생성 (#1: 코드를 작성하세요!)
3. PR 검토 및 병합
4. 이슈 연결 확인

#### 기여자 (Origin)
1. Fork (`chatkang/PR-train`)
2. Upstream 이슈 확인
3. 코드 작성 (`code/hello.py`)
4. Pull Request 생성 (#2)
5. PR 병합 확인
6. Sync Fork로 동기화

### 주요 명령어 및 작업

| 작업 | GitHub 위치 | 설명 |
|------|----------|------|
| **Fork** | 저장소 우측 상단 | Upstream을 자신의 계정으로 복제 |
| **Create file** | Add file → Create new file | 새 파일 작성 |
| **Pull Request** | Contribute → Open pull request | PR 생성 |
| **Merge** | Merge pull request 버튼 | PR 병합 |
| **Sync fork** | Sync fork → Update branch | Fork 동기화 |

### 이슈와 PR 연결

```markdown
# PR 설명에서
Create hello.py #1

# 결과
→ Issue #1과 자동으로 연결됨
```

***

## 실습 체크리스트

### 관리자 (Upstream) 작업

- [ ] GitHub에서 새 저장소 생성 (`PR-train`)
- [ ] README, .gitignore, LICENSE 포함 설정
- [ ] Issues 탭에서 새 이슈 생성 (#1)
- [ ] Pull requests 탭에서 PR 확인
- [ ] PR 내용 검토 (Conversation, Files changed)
- [ ] Merge pull request 실행
- [ ] Confirm merge 클릭
- [ ] 병합된 파일 확인 (`code/hello.py`)
- [ ] 이슈와 PR 연결 확인

### 기여자 (Origin) 작업

- [ ] Upstream 저장소 Fork
- [ ] Fork 설정 확인 (Copy main branch only)
- [ ] Upstream에서 이슈 확인 (`https://github.com/ai7dnn/PR-train/issues`)
- [ ] 자신의 Fork 저장소에서 파일 생성 (`code/hello.py`)
- [ ] 파일 커밋 (Commit directly to main)
- [ ] Contribute → Open pull request
- [ ] PR 제목 및 설명 작성 (`#1` 이슈 번호 포함)
- [ ] Allow edits by maintainers 체크
- [ ] Create pull request 클릭
- [ ] PR 생성 확인
- [ ] Upstream에서 병합 대기
- [ ] Sync fork → Update branch로 동기화
- [ ] Commits 개수 확인 (Upstream과 동일)
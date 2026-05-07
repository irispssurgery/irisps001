# 🔍 Researcher — 해당 에러가 발생하는 주요 원인(로컬에 커밋이 없는 경우, 현재 브랜치 이름이 main이 아닌 master인 경우, 브랜치 생성이 안 된 경우 등)을 분석하여 정리하십시오.

🔍 Researcher: 작업 시작합니다.

# 📋 Git Error 분석 보고서: `src refspec main does not match any`

본 보고서는 `git push` 실행 시 발생하는 `error: src refspec main does not match any` 및 `failed to push some refs` 에러의 근본 원인을 분석하고, 상황별 즉각적인 해결책을 제시합니다.

## 1. 에러의 핵심 의미
이 에러는 **"로컬 저장소에서 `main`이라는 이름의 브랜치(또는 참조)를 찾을 수 없어, 원격 저장소(remote)로 보낼 대상이 없다"**는 뜻입니다. 즉, Git이 전송할 '소스(src)'가 존재하지 않는 상태입니다.

## 2. 주요 발생 원인 분석

### ① 로컬에 커밋(Commit)이 없는 경우 (가장 빈번)
*   **현상:** `git init`으로 저장소를 새로 만든 후, 파일을 `git add`는 했으나 `git commit`을 한 번도 수행하지 않은 상태에서 `push`를 시도할 때 발생합니다.
*   **이유:** Git에서 브랜치는 커밋을 가리키는 포인터입니다. 첫 번째 커밋이 생성되기 전까지는 `main`이라는 브랜치 자체가 실질적으로 존재하지 않는 상태(unborn branch)로 간주됩니다.

### ② 브랜치 이름 불일치 (`master` vs `main`)
*   **현상:** 로컬 브랜치 이름은 `master`로 생성되었는데, 명령어를 `git push origin main`으로 입력한 경우입니다.
*   **이유:** 과거 Git의 기본 브랜치 명칭은 `master`였으나, 최근 표준은 `main`입니다. 환경 설정에 따라 로컬은 `master`인데 명령은 `main`을 찾고 있어 참조 오류가 발생합니다.

### ③ 브랜치 생성 및 체크아웃 미비
*   **현상:** 특정 브랜치에서 작업 중이며, `main` 브랜치로 전환(checkout)하거나 생성하지 않은 상태에서 `main`을 push하려고 할 때 발생합니다.
*   **이유:** 현재 작업 중인 브랜치(HEAD)와 명령어로 지정한 브랜치(`main`)가 물리적으로 분리되어 있습니다.

---

## 3. 상황별 해결 가이드 (Action Plan)

### [Case 1] 첫 커밋을 하지 않은 경우 (초기 세팅 중)
가장 먼저 로컬에 변경 사항을 확정(commit)해야 합니다.
```bash
git add .
git commit -m "Initial commit"
git push origin main (또는 master)
```

### [Case 2] 브랜치 이름이 `master`로 되어 있는 경우
로컬 브랜치 이름을 `main`으로 변경하여 일치시킵니다.
```bash
# 1. 현재 브랜치 이름 확인
git branch

# 2. 현재 브랜치(master)를 main으로 강제 변경
git branch -M main

# 3. 다시 Push 시도
git push -u origin main
```

### [Case 3] 원격 저장소와 로컬의 상태가 꼬인 경우
원격의 내용을 먼저 가져온 뒤 재시도합니다.
```bash
git pull origin main --allow-unrelated-histories
# 충돌 해결 후
git push origin main
```

## 4. 요약 및 체크리스트
| 체크 항목 | 확인 명령어 | 해결 조치 |
| :--- | :--- | :--- |
| **커밋 존재 여리** | `git log` | 에러 발생 시 `git commit` 수행 |
| **현재 브랜치명** | `git branch` | `master`라면 `git branch -M main` 실행 |
| **파일 스테이징** | `git status` | `git add .` 수행 여부 확인 |

📊 평가: 완료 — 에러의 기술적 원인을 3가지 핵심 유형으로 분류하고, 즉시 적용 가능한 해결 명령어를 매핑하여 정리함.

📝 다음 단계: 위 가이드를 바탕으로 개발 환경의 `git branch` 결과를 확인하여 적절한 Case를 선택해 실행할 것.

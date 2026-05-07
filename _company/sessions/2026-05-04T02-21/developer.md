# 💻 Developer — 에러 해결을 위한 단계별 명령어 세트를 작성하십시오. 1) `git branch`로 현재 브랜치 확인, 2) `git add .` 및 `git commit -m 'initial commit'`으로 첫 커밋 생성, 3) `git branch -M main`으로 브랜치명 변경, 4) `git push -u origin main`으로 푸시하는 과정을 포함하십시오.

💻 Developer: 작업 시작합니다.

# 🛠 Git Push Error 해결을 위한 단계별 명령어 세트

`error: src refspec main does not match any` 에러는 로컬 저장소에 커밋된 내용이 없거나, 푸시하려는 `main` 브랜치가 존재하지 않을 때 발생합니다. 아래 명령어를 순서대로 터미널에 입력하십시오.

```bash
# 1. 현재 로컬 브랜치 상태 확인
# (브랜치 목록에 아무것도 뜨지 않거나 커밋이 없다면 다음 단계 진행)
git branch

# 2. 모든 변경 사항을 스테이징 영역에 추가
git add .

# 3. 첫 번째 커밋 생성 (에러의 근본 원인인 '커밋 없음' 상태 해결)
git commit -m "initial commit"

# 4. 현재 브랜치 이름을 main으로 강제 변경 (master -> main)
git branch -M main

# 5. 원격 저장소(origin)의 main 브랜치로 푸시 및 업스트림 설정
git push -u origin main
```

### 💡 명령어 요약 및 역할
| 단계 | 명령어 | 목적 |
| :--- | :--- | :--- |
| **확인** | `git branch` | 현재 로컬 브랜치 및 존재 여부 체크 |
| **준비** | `git add .` | 모든 파일을 커밋 대상에 포함 |
| **확정** | `git commit -m '...'` | 스냅샷을 생성하여 브랜치 포인터 생성 (필수) |
| **표준화** | `git branch -M main` | 브랜치 명칭을 최신 표준인 `main`으로 통일 |
| **전송** | `git push -u origin main` | 원격 저장소와 로컬 브랜치를 연결하며 데이터 전송 |

📊 평가: 완료 — CEO의 지시 사항을 모두 포함한 실행 가능한 명령어 세트 작성을 완료함.
📝 다음 단계: 사용자가 위 명령어를 터미널에 실행하여 푸시 성공 여부 확인.

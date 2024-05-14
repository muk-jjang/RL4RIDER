# RL4RIDER

### clone from https://github.com/ai4co/rl4co

## Commit/Issue/PR Examples

### Commit

```
🔥 [add] #1 add html cleansing code
🔥 [add] #4 data preprocessing code
🐛 [fix] #12 fix bugs
🛠️ [git] #12 resolve merge conflict
🛠️ [git] #12 .gitignore
✨ [feat] #19 implement main logics (incomplete)
📝 [docs] #24 update git files
📝 [docs] #31 add TODO
🎨 [style] #31 fix typo
📌 [dev] #31 update dependencies
🛠️ [git] #2 merge
```

### Issue

```
[✨/feature/mindong] implement login feature
[🌱/develop/jeau] v0.1.12
[🚑/hotfix/joon] fix login Bug
```

### Branch & PR

```
feature#1/mindong/login
hotfix#2/jeau/fix-social-login
develop#3/joon/v0.1.12
chore#4/mindong/update-readme
chore#5/joon/style-change
add#1/jeau/add-skeleton-code
```

## Programming Rule

- **tips**

  - cmd+P, ctrl+P : 파일 검색
    - 아무렇게나 쳐도 파일 좀 잘 찾아줌, 파일 이름 지을 때 이 기능 사용할 것을 염두에 두고 지을 것
    - \# 누르면 symbol 검색 가능
  - hover, cmd+Click, ctrl+Click으로 파일 넘나들며 코딩하는 경우가 잦음, docstring이나 자세하게 작성할 수록 편함.
  - symbol 선택 후 shift+cmd+F / shift+ctrl+F로 reference들 확인하면 편함

- **import**

  - `@/`로 absolute import 가능 (pull해줘야 함)
  - Ex. `import * as S from '@/screens/styles';`

- **extensions**

  - Auto Import - ES6, TS, JSX, TSX (중)
    - 자동으로 import 해줌
  - Auto Rename Tag (하)
    - 아주 편함...
  - Better Comments (필수)
    - 프로젝트 내에서 코멘트 표시할 때, ! ? \* 등으로 표시하는 rule 정하면 협업 편할 듯
  - Bracket Pair Color DLW (중)
    - 없으면 웹개발 불가능
  - Github Copilot (상)
    - 웹개발 속도 \* 10
  - Path Intellisense (중)
    - import할 때, 경로 자동완성
  - Prettier - Code formatter (필수)
    - 코드 포맷팅, 이걸로 통일할 것임
  - vscode-pets (하)
    - 귀여움

## Commit Message Convention

### emoji \[type\] message

```
🔥 [add] #1 add html cleansing code
🔥 [add] #4 data preprocessing code
🐛 [fix] #12 fix bugs
🛠️ [git] #12 resolve merge conflict
🛠️ [git] #12 .gitignore
✨ [feat] #19 implement main logics (incomplete)
📝 [docs] #24 update git files
📝 [docs] #31 add TODO
🎨 [style] #31 fix typo
📌 [dev] #31 update dependencies
🛠️ [git] #2 merge
```

### type

```
✨ feat : 새로운 기능 추가
🔥 add : 기능은 아닌 코드 추가
🐛 fix : 버그 수정
📝 docs : 문서 수정
🎨 style : 코드 포맷팅, 세미콜론 누락, 코드 리프랙터, 코드 변경이 없는 경우
🛠️ git : 깃허브 관련
📌 dev : 개발환경 (packages, requirements, 등등)
```

### message

- 첫글자는 대문자로 시작
- 필요한 경우 message 아래에 내용 첨부
- type 다음에 #N 으로 이슈번호 붙이기

```
Ex
🔥 [Feat] #34 Implement main logics (incomplete)

TODO
- vehicle_update 함수 수정 필요
- request_time 변수 추가 필요
- calculate_time unit test
```

### fix

- `git commit --amend -m "바꿀 메시지"`
- `git push --force`

## Branch Naming Convention

### Overall

```
📢작업 흐름📢

1. 작업 하기 전에 무조건 이슈 올리기

2. feature 브랜치 만들기
   - 브랜치 컨벤션 : feat/#이슈번호

3. feature 브랜치로 전환한 후 작업 진행하기

4. 작업 끝나고 add, commit, push

5. PR하기

6. 머지하기
   - 2명 이상의 승인을 받아야 머지 가능

7. feature 브랜치 제거하기
   - 원격 브랜치, 로컬 브랜치 제거
```

### type

```
main: 메인 브랜치
feature: 기능 개발 브랜치
hotfix: 긴급 수정 브랜치
develop: 개발 브랜치
```

### name

### example

```
feature#1/mindong/login
hotfix#2/jeau/fix-social-login
develop#3/joon/v0.1.12
chore#4/mindong/update-readme
chore#5/joon/style-change
add#1/jeau/add-skeleton-code
```

### Issue naming convention

- Emoji/Type/Identifier/Title

```
✨ feature: For new functionalities/features.
🔥 add: 뭔가 디게 밑에 거 어떤 것도 아닌데 애매할 때
🛠 chore: 기타 등등 (minor change)
🌱 develop: 개발 브랜치 (버전 체킹용)
🚑 hotfix: 핫픽스 브랜치
🚧 spike: Research or investigative tasks.
```

- Example

```
[✨/feature/mindong] implement Login Feature
[🌱/develop/jeau] v0.1.12
[🚑/hotfix/joon] fix Login Bug
```

### When forgot to create branch

```bash
git stash
# 현재 작업 내용을 stash라는 어떤 공간에 일단 저장함
# stash 하면 갑자기 다 사라짐, 놀라지 말 것.

git checkout -b new-branch-name
# Ex. git checkout -b feature#1/cake/login
# 새 브랜치를 만듦

git stash apply
# stash에 저장된 작업 내용을 불러옴
# 이후 커밋 진행
git add file1 file2
git commit -m "commit message"
# Ex. git commit -m "✨ [Add] Implement Login Feature"

git checkout main
# main으로 돌아옴

git checkout -b another-new-branch-name
# 다시 다른 브랜치를 만듦

git stash apply
git add file3 file4
git commit -m "commit message"

# ... 이런 식으로 진행

git stash pop
git push origin new-branch-name
# Ex. git push origin feature#1/cake/login
# 아니면, pull request를 날리고 merge하면 됨 (이게 더 낫쥬?)

git branch -D another-new-branch-name
```

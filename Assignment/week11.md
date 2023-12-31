# MERGE
> 두 개의 브랜치를 하나로 병합 <br>
> A + B

# fast-forward 병합
> 현재 브랜지 master가 병합할 대상 커밋의 직접적인 뿌리(조상)가 되는 경우<br>
> 두 브랜치가 일렬 상태 <br>
> bugfix 브랜치 이력이 master 브랜치 이력을 모두 포함하는 경우<br>

> master 브랜치는 단순히 이동<br>
> 간단히 가리키는 지점이 대상 커밋이 되고 master가 bugfix로 이동<br>
> 작업공간과 스테이징 영역이 이동되는 Y 상태로 됨<br>

- $ git merge bugfix

# 3-way 병합
> 두 브랜치의 조상이 같은 경우<br>
> master 브랜치 내의 변경 내용과 bugfix 브랜치 내의 변경 내용을 하나로 통합할 필요 O<br>
> 새로운 커밋을 사용하여 두 기록을 합침<br>

> 새로운 커밋 E 생성<br>
> 두 브랜치의 변경을 가져온 'merge commit(병합 커밋)‘ E를 생성<br>
> 병합 완료 후, 통합 브랜치인 'master' 브랜치로 통합된 이력이 생성, -m이 없으면 메시지 입력할 기본 편집기 실행<br>
> ‘Merge branch bugfix’이 기본 메시지 내용<br>

- $ git merge bugfix

# 여러 병합 방법
> $ git merge bugfix - 일렬 상태의 기본은 fast-forward 병합<br>
> $ git merge --no--ff bugfix - 옵션을 줄 시 3-way 병합<br>
> $ git merge --ff-only bugfix - 상태가 fast-forward인 일렬 상태에서만 병합<br>
> $ git merge --squash bugfix - 커밋 이력과 병합 브랜치 이력을 남기지 않음

# 병합 충돌(conflict)
> 3-way 상태에서 두 브랜치의 동일 조상인 커밋 1을 기준<br>
> 병합할 두 브랜치 마지막 커밋을 비교<br>

- <b>충돌의 기준?</b><br>
> 파일 충돌 없음<br>
> 수정되지 않거나 한쪽 브랜치에서만 수정된 경우<br>
> 파일 충돌 발생<br>
> 두 브랜치 모두에서 변경 사항이 달리 발생한 파일

# 충돌 해결
> 충돌이 발생하면 해당 파일의 충돌을 먼저 해결<br>
> 충돌이 발생한 파일 직접 편집<br>
> 계속해서 add, commit 진행<br>
> 필요하면 합병된 이전 브랜치 삭제<br>

> 충돌한 파일 내부 표시<br>
> 충돌 파일을 vscode로 열기<br>

- $ git merge --abort - 충돌 이후 병합 취소

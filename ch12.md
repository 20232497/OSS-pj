# base의 이해
> 3-way 상태에서 base의 이해<br>
> 'master' 브랜치 커밋 B에서 분기되는 'bugfix' 브랜치<br>
> 현재 master와 bugfix의 공통 조상을 base라 칭함

# rebase의 이해
> 재배치 rebase 병합 수행<br>
> base를 수정<br>
> B에서 마스터의 최신 커밋인 D로 수정 -> D 이후에 bugfix를 배치<br>
> 이후 다시 'fast-forward 병합’ 수행<br>
> 'master' 브랜치의 HEAD가 'bugfix' 브랜치 마지막 커밋으로 이동<br>

> 'fast-forward 병합’ 방식<br>
> master 브랜치 뒤로 bugfix 브랜치의 이력이 이동<br>
> 이력이 하나의 줄기로 이어짐<br>
> 충돌 발생 가능<br>

- $ git rebase master - rebase만 하면 'master'의 위치는 그대로 유지<br>
- $ git merge bugfix - 마스터 브랜치의 위치를 변경하려면 fast-foward(빨리 감기) 병합 필요<br>

# 충돌 발생 가능
> 이동되는 X와 Y의 내용이 'master'의 C, D 커밋들과 충돌하는 부분이 생길 수 있음<br>
> 각각의 커밋에서 발생한 충돌 내용을 수정 후, 추가, 계속 수행 필요<br>

충돌 발생 후 해결 절차<br>
> 1. 파일 수정<br>
> 2. 파일 추가 - $ git add <수정파일><br>
> 3. rebase 계속 수행, 마지막 메시지 메시지 수정 - $ git rebase --continue

# 3-way merge와 rebase 비교
- merge - 여러 분기가 생긴 변경 내용의 이력이 모두 그대로 남아 있기 때문에 이력이 복잡<br>

- rebase - 히스토리가 선형으로 단순해지고 좀 더 깨끗한 이력을 남김, 원래의 커밋 이력이 변경

# fast-forward merge와 rebase 비교
- fast-forward merge - 조상에 위치한 브랜치에서 선행 브랜치의 마지막으로 이동하는 병합<br>

- rebase - 두 갈래의 브랜치에서 기존의 베이스를 수정, 병합할 브랜치 마지막 커밋을 새로운 베이스로 수정하는 병합

# git rebase
- 일반적 rebase 방법: topic에서 main을 rebase 한 이후, 다시 main으로 이동 fast-forward 병합 수행<br>
> $ git checkout topic<br>
> $ git rebase main<br>
> $ git checkout main<br>
> $ git merge topic <br>

- 다른 rebase 방법: 어느 브랜치든 main topic 순서로 재배치 방법<br>
> $ git rebase main topic<br>
> $ git checkout main<br>
> $ git merge topic<br>

# 최근 커밋 메시지 수정
> $ git commit --amend - 기본 편집기로 메시지 편집<br> 
> $ git commit --amend –m '' - 명령어 상에 직접 메시지 입력  <br> 
> $ git commit --amend --no-edit - 메시지 수정 없이 다시 커밋 수정 

# 여러 커밋 수정
> 작업 공간이 깨끗한 이후, 이전 여러 개의 커밋을 수정<br>
> rebase의 --interactive를 사용하여 커밋 시퀀스를 새로운 기본 커밋에 결합<br>
> $ git rebase -i HEAD ~ 3<br>
> $ git rebase --interactive HEAD ~ 3 <br>
> HEAD ~ n: HEAD부터 n개의 행 편집 가능<br>
> 로그 결과와 다르게 오래된 커밋부터 표시

# 주요 rebase –i 대화형 명령어
> p(ick): 해당 커밋을 수정하지 않고 그대로 사용<br>
> r(eword): 개별 커밋 메시지를 다시 작성<br>
> s(quash): 계속된 이후 커밋을 이전 커밋에 결합<br>
> d(rop): 커밋 자체를 삭제<br>

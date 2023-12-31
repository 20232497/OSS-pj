# OSS (open source software)
> 누구나 특별한 제한 없이 코드를 보고 사용할 수 있는 소프트웨어<br>
> 소스코드 공개, 복제 가능

# OSI (open source initiative)
> open source.org<br>
> 공개 소스 정의의 관리 및 촉진을 담당하는 비영리 조합

# Free Software
> 리처드 스톨먼 개발<br>
> GNU 프로젝트와 관련된 소프트웨어에서 자유를 중시<br>
> Copyleft<br>
> Free software에서 OSS가 발전됨

# OSS 저작권
> GPL - LGPL - Apache - BSD - MIT<br>
> 강도 높은 저작권부터 낮은 순으로 나열

# Stash
> 마지막 커밋의 내용이 저장<br>
> 작업 디렉토리와 스테이지의 내용이 저장<br>
> $git stash = $git stash save<br>
> $git stash -m '' = $git stash save ''<br>
> 옵션 -k: 작업폴더만 저장<br>
> 옵션 -u: untracked file까지 저장

# Stash -> 저장소
> 최근 임시저장 내용을 가져와 반영<br>
> $git stash apply - 작업 디렉토리에 반영<br>
> $git stash apply --index - 작업 디렉토리와 스테이징 영역에 복원<br>
> $git stash pop - 복원 후 Stash 삭제<br>
> $git stash pop stash@{n} - 복원 후 Stash 삭제

# Stash 목록
> $git stash list

# 내용 비교
> $git stash show - 커밋 자료와 최신 임시저장 비교<br>
> $git stash show stash@{n} - 커밋 자료와 특정 임시저장 비교<br>
> 옵션 -p: 상세 정보까지 표시

# 삭제
> $git stash drop - 최근 임시저장 삭제<br>
> $git stash drop stash@{n} - 특정 임시저장 삭제<br>
> $git stash clear - 모든 임시저장 삭제

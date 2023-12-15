## 원격저장소 생성

$git clone 복사된 주소 - 원격저장소와 동일한 이름으로 복사<br>
$git clone 복사된 주소 새로운 폴더명 - 원격저장소를 새로운 이름으로 복사<br>
$git clone 복사된 주소. - 현재 디렉토리에 바로 저장<br>

## 원격저장소 목록
$git remote - 저장소 이름만 보임<br>
$git remote -v - 저장소의 이름과 주소까지 보임<br>
$git remote add origin URL - 원격저장소를 origin에 저장<br>
$git remote rename origin org - 원격저장소 이름 수정<br>
$git remote rm org - 원격저장소 삭제<br>
$git remote show origin - 원격저장소의 상세 정보<br>

## push
쓰기권한이 있어야 가능<br>
쓰기권한? 자신의 저장소 or 협업자 권한<br>
로컬저장소의 변동사항이 원격저장소로 전송<br>
$git push origin main<br>
push 성공 시에는 뒤의 인자 생략 가능<br>

## pull
원격저장소의 수정을 로컬저장소에 반영<br>
push = fetch + merge<br>
fetch - 원격저장소의 정보를 로컬저장소에 반영<br>
$git fetch origin main<br>
merge - 변경된 정보를 로컬저장소와 병합<br>
$git merge origin/main<br>

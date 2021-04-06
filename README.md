### Hi there  👋
My name is Lee Ju Hyung
nice to me you

<!--
**jhlee7562/jhlee7562** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->


git push origin master 

git branch feat/doolri

git log --oneline --all --graph
-->현재 둘리 위치를 보여줌. 이상황에서 커밋하면 마스터 브랜치로 커밋이 됨
    그래서 둘리는 둘리브랜치로 바꿔서 커밋을 해줘야함

git checkout feat/doolri
--> 둘리브랜치로 변경을 해주는것, 둘리는 이제 여기서 작업해서 커밋하면 됨

touch doolri.txt
--> 둘리 브랜치인 상태에서 둘리의 지구여행! 이라고 새로만들어서 저장.
     팀장파일인 team.txt를 열어서 수정하고 add함

git add .

git commit -m "둘리는 열심히 개발했어요"
--> push는 하지않고 둘리브랜치에서 계속 커밋만 하는 상태

git checkout master
--> master 의 브랜치로 가는 명령어.
     둘리가 작업해서 올려놓은것은 없음, 팀장만든 그상태

git checkout feat/doolri
--> 다시 둘리 브랜치로 가

git log --oneline --all --graph
--> 다시 브랜치 상태를 확인함

git branch feat/dounaut
--> 도우너 개발자 추가

git checkout feat/dounat
--> 도우너 브랜치로 가라

touch dounat.txt
--> 도우너 브랜치에서 도우너.txt를 만들고 내용을 입력함. team.txt를 안건듬

git add . 
git commit -m "도우너는 열심히 개발했어요~"
--> 도우너브랜치에서 만든거 커밋함

git log --oneline --all --graph
--> 현재 상태를 확인함 -> 마스터에서 갈래가 2개로 갈라지며 나옴. 둘리랑 도우너
     master에는 개발코드가 반영되지 않은 상태


------------------------merge(병합) 하는 법

git checkout master
--> master 브랜치로 가라

git merge feat/dounat
--> master 브랜치에 도우너.txt가 들어와야함
     도우너의 개발사항이 반영 됐음.

git log --oneline --all --graph
--> 현재 상황을 보여줌. 도우너가 마스터와 같은 버전 관리중이란게 표시됨.

git merge feat/doolri
--> 둘리는 원본버전을 건드렸기 때문에 새로운 커밋을 하라는 창이 나올수있음
     둘리의 커밋을 병합함이라고 작성하면 됌

다 들어온 뒤 team.txt 눌르면 둘리가 쓴 메모도 들어옴

git log --oneline --all --graph
--> master 브랜치로 병합된 둘리,도우너가 보여짐 (초록색 가지로)

--------------------------- 이제 둘리와 도우너는 병합했으니 필요가 없어서 둘리랑, 도우너
브랜치를 지워주면 됌

git branch -d feat/doolri
git branch -d feat/dounat
--> 둘리, 도우너 브랜치 삭제시키기

git log --oneline --all --graph
--> 둘리,도우너 삭제한 브랜치 확인

--------------------------------- 수정사항을 한 브랜치

git branch fix/doolri
--> 둘리 브랜치 수정하는거 만듬

git checkout fix/doolri
--> 둘리 브랜치에서 team.txt 내용 수정하고 저장

git add .
git commit -m "둘리의 fix사항~ team.txt 수정함"
--> 둘리가 위 내용을 커밋함.

git log --oneline --all --graph
--> 현재 상황 확인, 둘리가 fix 사항을 추가해서 커밋해놓은것 확인됨

git checkout master
--> master 브랜치로 이동

git branch fix/dounat
--> 도우너 브랜치 수정하는거 만듬

git checkout fix/dounat
--> 도우너가 브랜치로 이동 team.txt에 내용 넣어서 수정함. (팀장,둘리,도우너가 넣어짐)

git add .
git commit -m "도우너의 fix커밋~~ team.txt수정"
--> 도우너가 수정한 버전 커밋

git checkout master
--> 마스터로 이동

git merge fix/doolri
--> 둘리가 도우너보다 먼저 병합해달라고 요청했음.

git merge fix/dounat
--> 도우너가 둘리 후에 병합해달라고 했음
     이렇게 하면 둘리,도우너가 수정한 두개의 파일이 충돌이 됨.


--------------------------------------- vs code로 git study 폴더 열기
둘리, 도우너 두개의 충돌 파일이 나타남.
팀장님이 그 파일을 수정함. (수동으로 검토해야함)
vs code 종료

git commit -am "충돌사항 해결커밋"
--> 위 수정내용 후 txt 파일을 열면 팀장이 수동검토한 파일로 저장되어져있음

git log --oneline --all --graph
--> 둘리,도우너 충돌사항이 커밋된 사실을 알 수 잇음.1!!

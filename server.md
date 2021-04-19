기초
-npm init으로 프로젝트를 만든다.
-npm install express --save
-install할 때 --save를 적으면 package.json의 dependencies에 라이브러리 정보가 저장된다.
-저장한 라이브러리는 node_modules 폴더에 저장된다.
-expressjs 홈페이지의 getting start -> Hello world의 코드를 사용해서 서버를 킬 수 있다.
-node index.js로 노드앱을 실행할 수 있으며 package.json의 script를 이용해 따로 스크립트를 설정할 수 있다.

몽고DB연결
-회원가입 후 클러스터를 만든다. (Build a new cluster)
-AWS, 싱가포르, M0 Sandbox를 선택하고 이름을 설정한 뒤 Create Cluster 클릭
-클러스터의 CONNECT 버튼을 누르고 유저를 만든 뒤 Create DB user
-Choose a connection method 클릭
-Connect Your Application 클릭
-나오는 코드를 복사해둔다.

몽구스
-몽고디비를 편하게 사용할 수 있는 라이브러리
-npm install mongoose --save
-몽구스를 이용해서 몽고디비와 연결한다. (index.js에 코드작성)

몽고디비 모델과 스키마
-유저데이터 베이스에 들어갈 속성들을 보관하기 위해 스키마를 만든다.
-모델은 스키마를 감싸는 역할을 한다.
-스키마는 한 오브젝트의 속성들이다. (글 제목, 글 내용, 작성시간 등등)
-models 폴더를 만들고 안에 User.js 파일을 만든다. (몽구스 함수를 이용해 스키마 작성)

#깃과 깃허브
-git-scm.com에서 다운로드 가능
-git --version으로 잘 다운됐는지 확인가능
-





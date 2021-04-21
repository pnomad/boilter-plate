#기초
-npm init으로 프로젝트를 만든다.
-npm install express --save
-install할 때 --save를 적으면 package.json의 dependencies에 라이브러리 정보가 저장된다.
-저장한 라이브러리는 node_modules 폴더에 저장된다.
-expressjs 홈페이지의 getting start -> Hello world의 코드를 사용해서 서버를 킬 수 있다.
-node index.js로 노드앱을 실행할 수 있으며 package.json의 script를 이용해 따로 스크립트를 설정할 수 있다.

#몽고DB연결
-회원가입 후 클러스터를 만든다. (Build a new cluster)
-AWS, 싱가포르, M0 Sandbox를 선택하고 이름을 설정한 뒤 Create Cluster 클릭
-클러스터의 CONNECT 버튼을 누르고 유저를 만든 뒤 Create DB user
-Choose a connection method 클릭
-Connect Your Application 클릭
-나오는 코드를 복사해둔다.

#몽구스
-몽고디비를 편하게 사용할 수 있는 라이브러리
-npm install mongoose --save
-몽구스를 이용해서 몽고디비와 연결한다. (index.js에 코드작성)

#몽고디비 모델과 스키마
-유저데이터 베이스에 들어갈 속성들을 보관하기 위해 스키마를 만든다.
-모델은 스키마를 감싸는 역할을 한다.
-스키마는 한 오브젝트의 속성들이다. (글 제목, 글 내용, 작성시간 등등)
-models 폴더를 만들고 안에 User.js 파일을 만든다. (몽구스 함수를 이용해 스키마 작성)

#깃과 깃허브
-git-scm.com에서 다운로드 가능
-git --version으로 잘 다운됐는지 확인가능
-git init을 이용해 깃저장소를 프로젝트에 만들 수 있다.
-git status를 이용해 지금 깃의 상태를 확인할 수 있다.
-node_modules는 깃저장소에 올리지 않을 것이니 .gitignore 파일을 만든 뒤 안에 node_modules를 작성한다.
-우리가 사용하는 프로젝트 디렉토리에서 git add .를 사용하면 파일들이 Staging Area로 이동한다. (임시저장소)
-이미 node_modules가 staging area로 이동했으면 git rm --cached node_modules -r으로 제거해준다.
-git commit -m ""을 해주면 파일들이 git repository local에 올라간다.
-git repository remote(깃 허브 클라우드 저장소)에 올리기 위해서는 깃허드에 가입한다.
-이후 깃허브에 repository를 만들고 생성된 주소를 이용해 아래 코드를 작성한다.
-git remote add origin https://github.com/pnomad/boilter-plate.git
-git repository remote에 저장하기 위해서는 git push origin master를 입력한다.
-다음에 다시 넣기 위해서는 git pull origin mastger를 작성하고 일련의 과정을 반복한다.

#BodyParser와 포스트맨
-클라이언트에 입력해 보낸 정보를 bodyparser를 이용해 서버에 정보를 전달한다.
-npm install body-parser --save
-포스트맨은 클라이언트를 구현하지 않아도 테스트할 수 있는 도구이다.
 구글에 검색해서 다운로드할 수 있다.

#회원가입 기능
-index.js에 post메소드를 이용해 라우터를 만든다.
-유저 모델을 require로 가져와서 인스턴트화 시켜서 사용한다.
-bodyParser도 사용한다. 클라이언트 내용을 분석해서 받아오는 기능.
-만들어진 라우터를 테스트하기 위해서는 포스트맨으로 해당 주소에 정보를 전해준다.
-정보는 Body-raw-JSON 형식으로 전달한다.










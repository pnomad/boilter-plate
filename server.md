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

#nodemon 설치
-서버를 재시작하지 않아도 수정된 소스를 반영
-npm install nodemon --save-dev
-노드몬을 사용하는 스크립트를 package.json에 작성한다.

#소스 속 비밀정보 관리
-몽고디비 연결에서 id, 비번을 깃헙에 올리면 위험하다.
-config 폴더를 만들고 dev.js 파일을 만든다.
-개발하는 경우와 배포한 후의 경우에서 비밀정보 관리는 다르다.
-배포 후에는 배포사이트(헤로쿠)에서 정보를 관리해야한다.
-config에 prod.js, key.js를 만든다.
-이후 .gitignore에 dev.js 작성

#Bcrypt로 암호화 하기
-비밀번호를 암호화해서 데이터베이스에 올려야 관리자도 개인의 비밀번호를 모른다.
-npm install bcrypt --save
-register 라우터에 정보를 저장하기 전에 비번을 암호화한다.
-그러기 위해서 User.js에서 userSchema.pre('save', 함수)를 만든다.
-next에 정보가 담겨서 다시 index의 register라우터의 다음 순서가 진행된다.
-비크립트는 솔트를 만들고 그것을 이용해서 이용해서 비밀번호를 암호화시킨다. 

#로그인 기능 만들기
-로그인 라우터를 만든다.
-DB에 해당 이메일이 있는지 찾고 비번이 같은지 확인하고 토큰을 생성한다.
-찾을때는 몽고디비 메소드인 findOne 사용
-comparePassword 메소드를 User모델에서 만들어서 비교
-암호화된 번호를 복호화할 수 없기 때문에 입력된 비번을 비크립트로 암호화해서 비교한다.(compare함수 사용)
-비밀번호가 같으면 토큰을 생성해준다.
-npm install jsonwebtoken --save
-User모델에 generateToken 메소드를 만든다. (jsonwebtoken을 활용)
-jwt의 sign메소드를 이용해서 id와 특정 string을 합쳐서 토큰이 만들어진다.
-생성된 토큰은 브라우저의 쿠키에 저장한다.
-npm install cookie-parser --save

#Auth 기능
-토큰을 유저 정보(DB)에 넣고 쿠키에도 넣었었다.
-쿠키를 디코드해서 id를 만들어서 DB에서 확인해서 auth를 처리
-라우터 작성, auth라는 middleware를 만들어준다.
-middleware폴더를 만들고 auth.js파일을 만든다. 인증처리는 여기서 진행된다.
-User모델에서 auth.js에서 사용할 findByToken 메소드를 만들어준다.

#로그아웃
-토큰을 지워주면 된다. 
-토큰을 지우면 auth기능에서 토큰이 없다고 체크하기 때문에 인증이 안돼서 로그아웃 된다.
-라우터를 만든다. 역시 미들웨어로 auth 넣는다.









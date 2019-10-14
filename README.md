# 데모사이트
jsp를 통해 제작한 관리자 사이트입니다. 기본적인 로그인과 로그아웃 그리고 게시판 기능과 채팅, 사이트평가 구현해놨습니다. 화면은 BOOTSTRAP를 통해 작업했고 데이터베이스는 MySQL를 이용 했습니다.
[데모사이트]http://15.164.228.99:8080/UserChat/index.jsp

# ERD 설계
![스크린샷 2019-09-26 오전 6 22 30](https://user-images.githubusercontent.com/37436822/65640902-5f137300-e026-11e9-8bf3-232c473636bc.png)

총 5개의 테이블을 만들고 1:N, N:1의 관계를 통해 설계했습니다.
# 개발환경
* java
* jsp
* javascript
* jquery
* mysql
* bootstrap
* css
* aws
* tomcat
# 주요기능
* 자유게시판 CRUD
* 게시판 답변 , 파일업로드
* 회원가입
* 로그인,ID 찾기
* xss 공격 방어
* 사이트 평가
* 채팅
# 작업방식
프론트 환경은 BOOTSTRAP를 사용하여 작성하였으며 주로 Javascript로 작업하였습니다. 그 외 필요한 부분들은 jQuery를 사용했습니다. 데이터베이스는 MySQL를 통해 스키마를 설계하였습니다.

게시판 작업에서 게시판 목록을 구현할 때는 GET을 사용했고 등록, 수정, 삭제를 할 경우에는 POST를 사용했습니다. 삭제시에는 데이터를 지우는 것이 아니라 데이터 값을 추가해서 삭제할 경우네는 화면에 안보이게 하는 방식으로 코드를 정리했습니다.
# 로그인,회원가입
로그인과 회원가입의 경우 servlet를 이용하여 가입할수 있도록 하였습니다. 이후 로그인이 되어있는 경우와 되어있지 않는경우를 나누어서 메뉴가 다르게 생길수 있도록 하였습니다. 아이디 중복체크를 통하여 기존에 있는 아이디와 동일한것이 있는지를 확인할수 있도로 했습니다.
비밀번호는 비밀번호와 비밀번호 확인을 통하여 중복체크 할수있도록 유도하였고 다를경우 메세지를 통하여 이용자가 알수 있도록 했습니다.
로그인을 하지 않을 경우에는 메인루트를 타고 TABLE경로에서만 로그인이 필요하도록 작업하였습니다. 로그인이 되어 있을 경우에는 상단 메뉴 드롭다운에 Logout이 생성되고 로그아웃이 되면 Login, Join이 생성됩니다.
# 자유게시판
게시판의 경우는 게시판 번호,제목,작성자,조회수를 통하여 전반적인 내용을 알수 있도록 했습니다.
이후 글쓰기,수정,삭제,답변을 통해 이용할수 있도록 했습니다.
삭제의 경우 해당 데이터가 삭제되는것이 아니고 이용자가 해당 게시물을 볼수 없도록 처리했습니다.
# 채팅,친구찾기,프로필사진
채팅의 경우 ajax로 처리했습니다. 새로고침을 하지않아도 실시간으로 채팅을 서버에서 불러와 대화를 나눌수 있도록 하였습니다.
또한 상대방과 나의 구분을 위해서 사용자 본인인 경우에는 채팅창에 아이디가 표시되는것이 아닌 '나'로 표시했습니다.
프로필사진의 경우 기본적인 프로필사진을 이용하고 이후 이용자의 의해 프로필사진을 업데이트 할수있도록 하였습니다.
cos.jar 라이브러를 통하여 파일을 업로드 할수있도록 구현했습니다.
친구찾기의 경우 검색을 통해 해당 아이디가 있는지를 판별하여 프로필사진과 함께 보여질수 있도록 했습니다.
이후 채팅을 할수 있도록 버튼을 추가하였고 메시지를 왔음에도 읽지않는경우 몇개의 메세지가 왔는지 알수있도록 표시했습니다.
# 사이트평가
![스크린샷 2019-09-26 오후 2 13 56](https://user-images.githubusercontent.com/37436822/65659844-edf4af80-e067-11e9-8968-056984fa77ec.png)

사이트평가에서는 servlet를 이용하지 않고 action.jsp페이지를 이용하여 카드형태로 등록하고 삭제하고 추천할수 있도록 구현했습니다.
검색을 통해 찾을수 있도록 했으며 게시판별,최신순,추천순으로 나열할수 있도록 했습니다.
모달창을 이용하여 데이터를 저장하고 이를 카드형태로 값을 뿌려줬습니다.


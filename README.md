# 개발자가 되자
## Github에 저장소 만들기
* 저장소를 한글로 만들면 이름이 안나온다. 영어로 만들자
* mkdir 디렉토리
* cd 디렉토리
* git init
* 키가 없다면 [이렇게 링크를?](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
* 키를 만들고 cat ~/.ssh/id_rsa.pub
* ssh키는 디바이스 별로 인증한다 (https로 하면 매번 ID/PW를 쳐야함)

### gitbash에서 잠깐
* gitbash는 쉘스크립트를 지원하는 녀석
* 쉘은 유닉스의 명령어 인터페이스

## 내가 만든 로컬 저장소를 원격저장소로
* git add.
* git commit -m muragora
* git push origin master
* 에드하구 커밋하고 푸시하고...

## 개발자가 되기 위해서
* 영어랑 친해지기
* 단축키랑 친해지기
* 마크다운으로 문서 정리하기

# 크롬 개발자 모드
* elements : 태그 수정 들
* resources : 코드, 이미지, 클라이언트의 쿠키,세션 등의 정보
* network : 웹페이지 로드부터 이미지랑 리소스들을 가져오는 모습을 보여주는(얼마나 많은 시간과 어떤 순서로 리소스를 가져오고 어떤 요청과 응답이 오고가는지)
* source : 자바스크립트 디버깅용. 스크립트를 한줄한줄 실행함
* Timeline : 크롬의 성능측정하는 고급정보제공기능
* profiles : 크롬에서 동작하는 자바스크립트나 css의 성능을 측정해서 어디서 병목이 나는지 도와주는 도구, 어디서 메모리누수가 일어나는지 객체별로 확인 가능
* audit: 웹페이지의 상태 체크. 성능에 악영향끼치는 부분 조언
* console : 자바스크립트명령을 실시간으로 입력해볼 수 있는 기능. 로깅하는 기능. 에러,워닝,로그를 알려주는 기능
* 독을 누르면 별도화면으로 열 수 있음.
* 콘솔말고 다른탭에 있다가 현재상태를 체크하고 싶으면 >= 처럼 생긴걸 누르면 콘솔창과 동일
* setting에서 user agent가면 크롬이아니고 explorer로 접근한거같은 신호를 서버에 전달 가능.
* shortcuts에는 단축키

# 자바스크립트
* 자바스크립트의 원래이름은 live script
* 근데 당시에 자바가 유명해서...
* 자바랑 아무 관련이 없다
* 오늘의 js는 브라우저뿐아니라 서버에도 있고 js엔진이라는 프로그램을 가진 모든 디바이스에 있다

## 브라우저내의 js가 하는 일
* 현대 js는 안전한 언어
* 메모리나 cpu에 접근하지 않는 초창기엔 브라우저를 위해 만들어진 언어
* js는 유저의 안전을?위해 데이터에 해를 끼치지 않도록 제한됨
* 하드의 임의파일을 읽고 쓰거나 복사해 os에 접근하지 못함
* 접근은 제한하지만 유저의 드로핑이나 인풋버튼의 선택을 통해 파일들을 실행하는 방법은 있음
* 등등 너무많다...

## js의 특별한 점
* HTML/CSS와 완벽한 통합
* 간단
* 모든브라우저에서 지원

## js에서 나만몰랐던...
* scr하고 let은 js에서만쓰더라....

## js에서 어렵던 자료형
* 자료형 변환이 마구된다
* let msg = "asdf";
* msg = 12345;
* 그렇다면 "" + 1 + 2 = "12"
* "" - 1 + 2 = 1
* +는 문자열 "" + 1 이 문자열의 합이되서 "1"
* -는 숫자계산밖에 안되므로 숫자로 변환
* 1 + 2 + "px" = "3px"

## 재미따...어릴때열심히할걸...
* 새로운걸 하면 앞에걸 까먹는 기분이다




# 아래는 예시

# 개발자처럼 개발 환경 설정하기

## Font
폰트는 개발 생산성에 아주 중요한 요소이다. 고정폭(Monospaced)폰트를 사용하는 것이 여러 줄을 입력할 때에도 공백을 포함한 문장의 글자 폭을 일정하게 유지시켜 주어 가독성에 도움이 된다. 아래의 목록들을 참조해서 취향껏 골라보자.
* [Programming Fonts — A List](https://medium.com/@caulfieldOwen/programming-fonts-a-visual-guide-567fc210d2c6)
* [103 Best programming fonts as of 2018 - Slant](https://www.slant.co/topics/67/~best-programming-fonts)

## IDE (Integrated Development Environment)
개발에 필요한 툴을 통칭한다. 예전에는 빌드와 디버깅이 가능한지 등의 기준으로 IDE와 단순 Editor를 명확히 구분했으나, Editor 상에서도 빌드를 수행할 수 있는 플러그인 등이 많이 보편화되면서 IDE라는 단어로 모두 묶어서 부르는 추세이다. 프론트엔드 개발을 위해서는 아래의 툴들이 보편적으로 많이 사용되니, 이것저것 사용해보다 가장 마음에 드는 툴로 갈아타면 된다. 아래에서 무겁다/가볍다는 메모리 점유율이나 버벅이는 정도를 말한 것이다. 무겁다=버벅인다. 가볍다=버벅이지 않는다. 로 생각하면 되겠다.

### Vim
* 가장 가벼움
* 풀 CLI 인터페이스임 (단축키 잘쓰면 개발의 신처럼 보일 수 있음)
* 숙달되는데 시간이 아주 오래 걸림

### [Sublime Text](https://www.sublimetext.com/) `추천`
* 가벼움
* 다양한 플러그인
* 업데이트가 엄청 빠른 편은 아님

### [Visual Studio Code](https://code.visualstudio.com/) `강력 추천`
* IDE 명가 Microsoft에서 만듦
* 가벼운 축에 속함 (Editor)
* 매우 다양하고 편리한 플러그인

### [WebStorm: 유료](https://www.jetbrains.com/webstorm/) `추천`
* IDE 명가 JetBrains에서 만듦
* 빌드, 디버깅, 참조 추적 등 기존에 IDE에서 제공하는 모든 기능을 fully support함
* 약간 무거움
* Professional Edition은 유료지만 Community Edition은 무료임.

### [Atom](https://atom.io/)
* GitHub에서 만듦
* 졸라 무거움 (Editor인데도)
* 크래쉬 졸라 빈번함 (뻑하면 꺼짐)

### [Brackets](http://brackets.io/)
* Adobe에서 만듦
* 중간 정도의 가벼움
* 디자이너들이 좋아한다는 썰이 있음

## Terminal
흰 바탕에 검은 글씨의 기본 bash 터미널은 가독성도 떨어지고 기능도 많지 않다. 터미널을 커스터마이즈 해보자.

### [Oh My ZSH](https://ohmyz.sh/) `강력 추천`
* 말이 필요없다. 명령어 자동완성이나 git 브랜치 서포트 등 각종 편의기능과 테마도 다양하게 존재한다.
이거 붙여넣어 보세여
복사해서
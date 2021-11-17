# mobileVerification

> 2020 카카오페이 공채 경력 프론트엔드 과제
사용자의 정보 입력을 통한 휴대폰 본인 인증 화면 개발

1. 과제 요구사항(requirement)
  과제 요구사항
    - webpack 환경을 구성
    - webpack-dev-server 환경 구성
    - start script를 통해서 hot-loading 적용
    - build script를 구성하여 /public 폴더에 빌드한 html, js, css를 export
    - 모든 구현은 vanila javascript(es5, es6, typescript도 가능)로 구현한다.
    - 구현하는 화면은 삽입된 디자인 스타일을 동일하게 할 필요는 없으며 요구사항에 맞게 구성해도 무방하다.
    - 단위 테스트 적용
    - 단위 테스트는 테스팅 library를 사용해도 무방함
    - 해결 전략을 README.md에 작성한다.
  이름
    - 한글만 입력
    - 최대 10자
  주민등록번호
    - 숫자만 입력가능
    - 생년월일 6자리와 뒷자리 1자리
    - format : 820816-1
  통신사
    - Select box로 구현
    - 통신사 데이터 (내부 변수 또는 파일로 사용)
  휴대폰 번호
    - 숫자만 입력 가능
    - 최소 10, 최대 11자리 입력
    - format : 전화번호 중간에 스페이스 삽입 ( 010 111 2222 or 010 1111 2222)
  공통
    - 각 input의 제한 사항을 만족하면 다음 input으로 자동 포커스 이동
    - 통신사를 선택하고 나면 휴대폰 번호로 이동
    - 휴대폰 번호 11자리까지 입력되고 나면 주민 등록 번호로 이동
    - 주민등록번호 6+1자리 입력되고 나면 이름으로 이동
    - 각 Input은 입력 및 validation에 따른 동작
    - 입력 값이 없을 때는 색상 변경 없음
    - 입력 후 포커스를 잃으면 validation 확인 후 색상 변경
    - 입력에 대한 validation이 만족되면 색상 원복
  약관
    - 3가지 필수 약관, 1가지 선택 약관이 존재
    - 전체 동의 하기를 선택하면 모든 약관이 선택
    - 모든 필수 선택 약관이 선택되면 약관에 동의 하는 것으로 간주
    - 약관 데이터 (내부 변수 또는 파일로 사용)
  인증 번호 요청 버튼
    - 모든 입력 값 및 약관이 동의 (필수 약관 동의)가 되기 전은 비활성화
    - 활성화 유무는 모든 입력 값의 변경에 따라 실시간으로 확인
    - 버튼을 click 하면 입력된 정보를 아래의 object와 같이 생성하여 console 창에 출력 (포맷에 유의)

2. 개발 환경(dev-spec)
 - NPM 6.14.5
 - node 12.18.1
 - visual studio code 1.62.2
 - chrome 95.0.4638.69

3. Dependencies(dependencies)
  npm init
  npm install --save-dev webpack
  npm install --save-dev webpack-cli
  npm install --save-dev webpack-dev-server
    - webpack@5.64.0
    - webpack-cli@4.9.1
    - webpack-dev-server@4.5.0
  npm install --save-dev @babel/core @babel/cli @babel/preset-env
  npm install --save-dev babel-loader
  npm install --save-dev babel-preset-env
  npm install --save-dev babel-jest
    - babel/core@7.16.0
    - bable/cli@7.16.0
    - babel-loader@8.2.3
    - babel-preset-env@1.7.0
    - babel/preset-env@7.16.4
    - babel-jset@27.3.1
  npm install --save-dev jest
    - jest@27.3.1
  npm install --save-dev sass
  npm install --save-dev node-sass
    - sass@1.43.4
    - node-sass@6.0.1
  npm install --save-dev css-loader
  npm install --save-dev file-loader
  npm install --save-dev html-loader
  npm install --save-dev sass-loader
  npm install --save-dev html-loader
  npm install --save-dev style-loader
  npm install --save-dev url-loader
    - css-loader@6.5.1
    - file-loader@6.2.0
    - html-loader@3.0.1
    - sass-loader@12.3.0
    - style-loader@3.3.1
    - url-loader@4.1.1
  npm install --save-dev html-webpack-plugin
  npm install --save-dev mini-css-extract-plugin
    - html-webpack-plugin@5.5.0
    - mini-css-extract-plugin@2.4.4

4. 설치 및 실행 방법(installation)
  yarn install 
  npm i 
  npm run server

5. 문제 해결 전략(solution)

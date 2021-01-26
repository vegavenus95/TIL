# Firebase
> Baas(Backend as a Service)  
> 서버측 코드를 작성하지 않고도 클라우드와 연동하여 모바일 응용 프로그램을 효율적으로 개발할 수 있는 환경을 제공  
> 주요 특징으로 <b>실시간 데이터베이스, 사용자 인증(oAuth), 클라우드, 호스팅, 오류 보고, 에드워즈, 에드몹, 애널리스틱스</b> 등의 서비스 제공  

### 기능

- Authentication  
Firebase에서 제공하는 UI인증을 사용 할 수도 있고, Firebase SDK를 사용해서 로직 처리만 사용할 수도 있다.  
google, facebook, twitter, github 와 제휴되어 각각의 계정으로 로그인 인증을 제공한다.(+kakao, naver도 api 사용하면 가능!)  

 
- Realtime Database  
온라인으로 제공되는 NoSQL DB(오프라인 모드를 지원하기도 함)이다.  
앱에서 하나의 DB를 보게되므로 여러 사용자에게 동기화 된 데이터를 제공할 수 있다.  
리얼타임 데이터베이스(실시간 데이터베이스)를 생성하여 사용할 수 있다.  


- Cloud Messaging  
push와 같은 알림 기능과 더불어 데이터 메세지 기능을 제공한다.  
메시지는 기기별, 그룹별, 주제별로 분류하여 전송할 수 있다.  


- Storage(Google Cloud Storage)  
사용자의 사진, 동영상 등의 컨텐츠를 저장할 수 있는 공간을 제공한다.  
-> AWS S3와 더불어 서버에 파일 업로드 하는 데 사용할 수 있다.


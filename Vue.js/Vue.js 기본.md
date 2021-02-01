# Vue.js    

### 정의  
> 웹 페이지 화면을 개발하기 위한 프론트엔드 프레임워크이다.  

### 특징  
- MVVM 패턴 사용  
![mvvm](https://user-images.githubusercontent.com/41683845/106479555-caf4ce00-64ed-11eb-8701-d1c3f9e0d04e.PNG)  

용어 | 설명
:------------: | :-------------:
뷰(View) | 사용자에게 보이는 화면
돔(DOM) | HTML 문서에 들어가는 요소(태그, 클래스, 속성 등)의 정보를 담고 있는 데이터 트리
돔 리스너(DOM Listener) | 돔의 변경 내역에 대해 즉각적으로 반응하여 특정 로직을 수행하는 장치
모델(Model) | 데이터를 담는 용기. 보통은 서버에서 가져온 데이터를 자바스크립트 객체 형태로 저장
데이터 바인딩(Data Binding) | 뷰(View)에 표시되는 내용과 모델의 데이터를 동기화
뷰 모델(ViewModel) | 뷰와 모델의 중간 역할. 돔 리스너와 데이터 바인딩을 제공하는 영역

- Virtual DOM 사용    
- Angular, React에 비해 매우 작고 가벼우며 복잡도가 낮음    
- Template과 Component를 사용하여 재사용이 가능한 사용자 인터페이스를 묶고 View Layer를 정리하여 사용    

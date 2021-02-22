# Vuex    

### 정의  
> vue.js 애플리케이션을 위한 상태 관리 라이브러리.  
> 모든 컴포넌트들에서 접근 가능한 <b>중앙 집중식 데이터 저장소</b>.

### 장점
> MVC 패턴에서 발생하는 구조적 오류 해결.  
> 컴포넌트 간 명시적인 데이터 전달 가능.  
> 여러 컴포넌트에서 같은 데이터 업데이트.  

### 특징  
> state, mutation, actions, getters

![vuex](https://user-images.githubusercontent.com/41683845/108675360-0bae9880-752a-11eb-820a-2866fb58b781.PNG)  

1. 컴포넌트는 Dispatch를 통해 Actions을 접근한다.  
2. Action에서는 Backend API를 호출하여 값을 가져온 후에, Commit을 통해 Mutations에 접근한다.  
3. Mutations에서는 크롬 확장 프로그램인 Devtools와 통신을 하여 디버깅이 쉽도록 기능을 제공하는 역할을 할 뿐 이니라, Mutate 를 통해 State를 변경 한다.  
4. State가 변경되면 컴포넌트는 다시 렌더링 되어 화면에 나타낸다.    

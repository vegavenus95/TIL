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

- state: data 역할, 데이터를 불러옴.  

- getters: computed 역할, 캐시되어야할 데이터.  
위 두 속성으로 component에 접근  

- mutations: 이곳에 있는 함수들을 commit해서 state를 변화시킴.  
mutations에 비동기 로직이 포함된다면? -> 순서를 알기 어려움
State 변화를 Mutations에서 하고
commit: Mutations의 함수 실행  

- actions: 비동기로직을 처리함.
여기서 비즈니스로직을 처리함.
Dispatch: Actions의 함수 실행
Actioncs에서 중요한 로직을 다 짜고
그 다음 commit으로 Mutation으로 넘김.   
  
-> Dispatch(‘[action메소드명]’)를 통해 Vuex store의 Action 그룹에 속한 메서드를 실행시킬 수 있음.  
Action메소드 혹은 Vue컴포넌트에서 Commit(‘[mutation 메소드명]’)을 통해 Mutation 그룹에 속한 메서드를 실행할 수 있음.
컴포넌트에서는 $store.commit(), Actions 메소드에서는 첫번째 인자로 넘겨받는 context.commit()으로 트리거 시킴.

![vuex](https://user-images.githubusercontent.com/41683845/108675360-0bae9880-752a-11eb-820a-2866fb58b781.PNG)  

### 라이프사이클  
  
1. 컴포넌트는 Dispatch를 통해 Actions을 접근한다.  
2. Action에서는 Backend API를 호출하여 값을 가져온 후에, Commit을 통해 Mutations에 접근한다.  
3. Mutations에서는 크롬 확장 프로그램인 Devtools와 통신을 하여 디버깅이 쉽도록 기능을 제공하는 역할을 할 뿐 이니라, Mutate 를 통해 State를 변경 한다.  
4. State가 변경되면 컴포넌트는 다시 렌더링 되어 화면에 나타낸다.    

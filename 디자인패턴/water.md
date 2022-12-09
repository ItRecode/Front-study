### 디자인 패턴

소프트웨어를 개발하는 과정의 반복되는 일반적인 문제들에 대해 기준이 되는 해결책을 제공하는 개념이다.

## 1. Compound Component 패턴

불필요한 prop drilling 없이 선언적인 컴포넌트를 만들 수 있다. 관심사를 분리하고 이해하기 쉬운 API를 갖춘 컴포넌트를 원하면 고려해야 할 패턴이다.

![image](https://user-images.githubusercontent.com/50071076/206644605-99408261-c2d3-49f6-bb6b-5ab41522cbfe.png)

`장점`

- API 복잡성 감서
- 유연한 마크업 구조
- 관심사의 분리

`단점`

- 너무 높은 UI의 유연성
- 너무 무거운 JSX

`패턴을 사용하는 라이브러리`

- React Bootstrap

## 2. Control Props

컴포넌트를 제어 컴포넌트로 변환한다. 외부 상태는 사용자가 컴포넌트의 기존 동작을 변경하는 사용자 지정 로직을 삽입하도록 허용하게 사용된다.

![image](https://user-images.githubusercontent.com/50071076/206644655-c77ec6bc-569f-49ce-b74d-f7b8d46639a0.png)

`장점`

- 더 많은 제어권 부여

`단점`

- 구현의 복잡성

`패턴을 사용하는 라이브러리`

- material UI

## 3. Custom Hook

기존 presentaton, container 패턴에서 로직을 hooks로 관리하는 것을 말한다. UI 재사용을 넘어서 로직까지 재사용이 가능해진다.

![image](https://user-images.githubusercontent.com/50071076/206644694-9303ef2c-6196-42f2-b333-061c0a9a40fa.png)

`장점`

- 더 많은 제어권 부여: 훅과 컴포넌트 사이에 자신의 로직을 삽입

`단점`

- 구현의 복잡성

`패턴을 사용하는 라이브러리`

- React hook form

## 4. Props Getter

아주 강력한 제어권을 주는 반면 컴포넌트를 통합하기 어렵다. 기본 props를 노출하는 대신 props getter의 목록을 제공. getter는 많은 props를 반환하는 함수이다.

![image](https://user-images.githubusercontent.com/50071076/206644735-a03cb23d-0410-4622-b2fb-c5855b2ee170.png)

`장점`

- 쉬운 사용: 사용자는 올바른 getter를 올바른 JSX 요소에 연결하기만 하면 됨
- 유연성: 특정한 유스케이스를 위해 필요한 경우 사용자는 getter에 포함된 props를 재정의할 수 있습니다.

`단점`

- 가시성 부족: getter가 제공하는 추상화로 인해 컴포넌트를 더 쉽게 구현할 수 있지만, 내부가 보이지 않는 것처럼 느껴질 수 있다.

`패턴을 사용하는 라이브러리`

- React table
- Downshift

## 5. State reducer

컴포넌트 내부의 동작 방식을 변경할 수 있는 방법을 제공, 커스터머 훅과 유사하지만 훅에 전달하는 리듀서를 정의한다. 이 reducer는 컴포넌트의 내부 행동을 오버로드한다.

![image](https://user-images.githubusercontent.com/50071076/206644818-f89dd4de-349c-43d2-a42b-485de7ebcc24.png)

`장점`

- 더 많은 제어권 부여: 가장 복잡도가 큰 경우에도 state reducers를 사용하는 것이 사용자에게 제어권을 넘기는 가장 좋은 방법입

`단점`

- 구현의 복잡성
- 가시성 부족

`패턴을 사용하는 라이브러리`

- downshift

## **Presentational and Container Component Pattern**

**Container**와 **Presentational**의 두 카테고리로 나뉜다.

**Presentational**

- 화면에 보여지는 것만 담당하는 컴포넌트
- 즉, 다른 부분과는 의존성을 갖지 않고, 데이터가 어떻게 가져와지고 변화되는지 모른다.
- 만약 상태를 갖는다면 UI와 관련된 상태만 갖는다.

**Container**

- 동작에 관한 것을 담당하는 컴포넌트
- DOM 마크업 구조나 스타일을 가지지 않는다.
- 데이터를 가져오거나 변화시키고 컴포넌트의 행동을 정의한다.

이 디자인 패턴은 관심사 분리, 재사용성, 마크업이 편하다는 장점이 있지만 이제는 hooks를 통해 할 수 있다.

## Atomic Design Pattern(아토믹 디자인 패턴)

디자인 시스템에서 컴포넌트들을 효율적으로 구성하는 방식을 의미한다.

Atoms, molecules, Organisms, Template, Pages로 효과적인 인터페이스 시스템을 만든다.

**Atoms**

- Label, Text, Button 등의 디자인과 기능의 최소 단위라고 할 수 있다.
- 모든 컴포넌트들의 기초가 되는 블록이며, 더 이상 분해 될 수 없는 필수 요서이다.

**Molecules**

- 2개 이상의 원자로 구성되어 있으며, 하나의 단위로 함께 동작하는 UI 컴포넌트들의 단순한 그룹

**Organisms**

- 분자, 원자 또는 다른 유기체의 그룹으로 구성된 비교적 복잡한 그룹

**Template**

- 컴포넌트들을 배치하고 설계의 구조를 보여준다.

**Pages**

- 실제 컨텐츠들을 배치한 UI를 보여준다.

애플리케이션과 분리하여 컴포넌트를 개발하고 테스트할 수 있고, 한번 패턴이 확립되면 더 빠르고 유연한 변경을 할 수 있다. 하지만 props drilling이 5단계로 들어갈 수도 있다. 또한 수 많은 컴포넌트가 각각 어떤 기능을 하는지 명확히 구분하기 어려워진다.

## Middleware 패턴

컴포넌트들이 서로 직접 통신하는 대신 중재자 역할을 하는 객체를 통하도록 한다.

![image](https://user-images.githubusercontent.com/50071076/206644929-6ee1ab96-e6bf-4067-8761-a9cc1197aa3b.png)

## 디렉토리 구조

- hooks
- components : UI모듈
  - atom: 버튼 체크박스 같은 아주 작은 컴포넌트
  - block: page는 아니지만 공통적으로 사용할 수 있는 부분.
  - pages
- middleware
- types
- utils
- api
- stores

### 참조 사이트

- https://blog.wishket.com/5%ea%b0%80%ec%a7%80-%ec%b5%9c%ec%8b%a0-%ea%b3%a0%ea%b8%89-%eb%a6%ac%ec%95%a1%ed%8a%b8-%ed%8c%a8%ed%84%b4-%e2%91%a1-props-getters-state-reducer/
- https://ui.toast.com/weekly-pick/ko_20200213
- https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0
- https://woong-jae.com/react/220609-react-design-pattern
- https://patterns-dev-kr.github.io/design-patterns/introduction/

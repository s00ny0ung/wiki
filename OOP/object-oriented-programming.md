# 객체지향

요즘 부쩍 객체지향에 대한 관심이 커져 많은 자료를 찾아보고 공부하던 중 최범균님의 블로그에 기재된 객체지향 기초 이야기 5편을 보고 큰 도움이 되어 정리를 해보았다.
항상 헷갈렸었는데 이번 기회에 다시 한번 정리하는 기회가 되었고 현재 객체지향의 사실과 오해(저. 조용호) 책을 읽고 있었는데 많은 도움이 되었던 것 같다.

## 요약

- 절차 지향의 핵심은 **데이터** 중심 - 함수들 간에 데이터가 흐름 ( 데이터를 공유 )
- 객체 지향은 **객체(데이터+기능)** 중심 - 객체들이 메시지(요청)를 주고받으며 서로 대화 ( 데이터가 객체들 간에 흐르지 않음 )
- 객체지향모델링 - 각각 객체가 어떤 기능을 제공하는지 정의하는 작업이다. 기능, 메시지를 주고받음 (협업)

- 객체의 핵심은 기능을 제공하는 것이다.
- Java는 클래스를 이용하여 객체를 표현한다.
- 필드 - 객체의 상태 보관
- 메소드 - 기능 구현
- 생성자 - 객체 생성
- private protected default public - 접근 제어자

### 캡슐화(encapsulation)

- 객체지향의 기본원칙으로 내부의 구현이 변경되더라도 외부에 영향을 최소화(내부 구현을 외부에 노출하지 않고 기능을 잘 캡슐화)
- 해당 기능을 변경해야 하는 상황에서 해당 클래스만 변경
- 변화가 여러 클래스로 확장되지 않음 (내부 구현이 변경되더라도, 그 기능을 사용하는 코드에 영향을 주지 않음)
- 따라서 유지보수 비용을 줄일 수 있음. (이것저것 수정할 필요가 없으므로)
- 내부 구현의 유연함을 주는 기법

### 추상화(Abstraction)

- 공통된 속성이나 관계를 뽑고 동시에 구현의 상세함을 숨김(복잡한 것을 감춤)
- 여러 개의 상세한 구현이 아닌 하나의 개념으로 생각할 수 있도록 도와줌 - 추상화
- 데이터나 프로세스 등을 의미가 비슷한 개념이나 표현으로 정의해 나가는 과정이면서 동시에 개별 객체의 구현에 대한 상세함을 감추는 것
- 추상화된 개념 -> 인터페이스로 제공

### 다형성(polymorphism)

- 다형성으로 추상화가 빛남
- 다형성 : 한 클래스의 객체는 그 클래스가 상속받은 모든 상위 타입도 될 수 있다
- 실제 사용되는 구현 클래스가 변경되었음에도 불구하고 그 타입을 사용하는 코드가 영향을 받지 않는 것

### 유연함(Flexibility) - 다형성과 관련

- 추상화 타입이 아닌 실제 구현체를 이용해서 개발하면 유연하지 않은 코드 유발
- 실제 구현체를 사용하면 구현에 변화가 생겼을 때 변화의 영향력이 이곳저곳 퍼짐
- 구현체가 아닌 인터페이스에 대고 프로그래밍하기 - 유연함을 제공한다.
- 즉, 인터페이스에 대고 프로그래밍함으로써 실제 사용되는 구현 객체를 쉽게 변경할 수 있는 유연함을 얻게 됨.
- 유연한 코드를 얻어내려면 먼저 기능(객체)을 추상화하는 연습을 많이 해줘야 함.
- 변화가 발생하는 부분이 있다면, 이 부분을 추상화해서 인터페이스 타입을 이용해서 프로그래밍해 주어야 한다. 인터페이스 타입을 사용해서 구현하게 되면, 실제 구현 객체가 변경되더라도 인터페이스 타입을 이용해서 구현한 코드는 영향을 받지 않게 된다.

### 상속보단 조립

- 상속은 'IS A' 관계일 때 의미를 가짐.
- 예를 들어, ArrayList는 AbstractList이다. (ArrayList is a AbstractList). 따라서, ArrayList가 오버라이딩 하지 않은 AbstractList의 메서드를 호출하더라도 ArrayList 객체는 아무런 문제를 일으키지 않으며, ArrayList는 기대하는 바대로 동작한다.
- 따라서, 구현 상속을 이용해서 기능을 재사용하려면 반드시 두 클래스가 같은 역할을 수행하는지 확인해야 한다. 두 클래스가 생성하는 두 객체가 서로 다른 추상 타입을 위한 것이라면 기능 재사용의 방법으로 상속을 선택하면 안 된다.
- 구현 상속은 정말 필요할 때 만 쓸 것!
- 구현 상속은 유지보수를 어렵게 만드는 요인이 된다. 예를 들어, 스프링의 AbstractController를 생각해보자. AbstractWizardFormController, SimpleFormController, MultiActionController 등이 이 클래스의 구현을 상속받고 있다. 이는 AbstractController의 기능을 수정하려면 그 하위 클래스들이 받을 영향에 대해서 고려해야 한다는 것을 뜻한다. 즉, 상속 받은 클래스가 많으면 많을수록 코드 변경 시 고려해야 하는 클래스들의 숫자는 비례해서 증가하며, 이는 변경의 어려움이 증가한다는 것을 뜻한다. 따라서, 구현 상속을 통해 기능을 재사용하려거든 정말 필요한 경우에 한해서 적용해야 하며, 조립이나 메타 정보 사용 등의 방법으로 풀 수 있다면 다른 방법을 사용하는 것이 코드 유지보수에 있어 유리하다.

### 단일 책임 원칙(SRP - Single Responsiblity Principle)

- 객체는 단 한 개의 책임(역할)만을 가져야 한다는 뜻으로, 객체를 변경해야 하는 이유는 단 하나여야 한다는 원칙

### 의존 역전 원칙(DIP - Dependency  Inversion Principle)

- 구현클래스가 아닌 인터페이스 타입을 사용하라는 규칙
- 구현 클래스는 자주 변경될 가능성이 높기 때문에, 변화 가능성이 상대적으로 적은 추상 타입이나 메서드에 의존하면 변화에 따른 영향을 최소화할 수 있다

### 개방 폐쇄 원칙(OCP - Open-Closed Principle)

- 특정 클래스(또는 모듈 등)는 그 클래스를 수정하지 않으면서 확장(extension) 가능해야 한다라는 원칙


>http://javacan.tistory.com/ 에 기재된 객체지향 기초 이야기 포스트를 기반으로 요약하였습니다. 문제가 될 시 삭제하겠습니다.

# 자바 기초

## 0. 객체 지향 프로그래밍(Object-Oriented Programming)

- 프로그램을 수 많은 객체라는 기본 단위로 나누고, 이 객체들의 상호작용으로 프로그램을 구성하는 방식
- 로직을 상태(state)와 행위(behave)로 이루어진 객체로 만드는 것
- 레고 블록처럼 객체를 조립해서 하나의 프로그램을 만드는 것
- 코드의 재사용성을 증가시키는 목적
- 유지 보수를 감소시키는 장점
- 강한 응집력(Strong Cohesion), 약한 결합력(Weak Coupling)을 지향

1. 캡슐화(Encapsulation)
   - 프로그램의 세뷰 구현을 외부로 드러나지 않도록 특정 클래스 내부로 감추는 것
   - 접근 제어 지시자를 통해 외보에서 접근을 제어
2. 상속(Inheritance)
   - 자식 클래스가 부모 클래스의 특성과 기능을 그대로 물려받는 것을 말한다.
   - 자식 클래스에서 재 정의를 통해 부모 클래스의 메소드를 사용
3. 다형성(Polymorphism)
   - 하나의 메소드, 클래스가 상황에 따라 다른 의미로 해석될 수 있다
   - Overloading은 다향성의 가장 대표적인 예

## 1. Java 프로젝트 생성

## 2. 객체와 클래스

- 객체(Object)를 만드는 기능을 한다
- 붕어빵 틀(클래스)과 붕어빵(객체)
- 여러가지 필드(Field)와 메소드(Method)를 가진다
- JVM 시작 시 RunTime Data Area의 Method(Static) Area에 할당

1. Field : 속성 = 상태 = 맴버 변수
2. Method : 객체의 동작, 행위, 기능
3. Constructor(생성자)
   - Instance 생성해주는 특수한 메소드로 값을 반환하지 않는다
   - 생성자의 이름은 클래스의 이름과 동일
   - 접근 제어 지시자는 반드시 public
4. Instance 생성
   - 어떠한 타입의 어떠한 객체 변수 생성
   - new 키워드를 통해 JVM RunTime Data Area내의 Heap 영역에 Instance 저장할 메모리 할당
   - 생성자를 통해 객체를 생성(초기화)
   - 생성자가 종료되면 new 연산자는 객체의 **참조 값을 반환**한다
   - 변수에 객체의 **참조 값 할당**

5. 은닉화
   - 클래스의 field는 Private로 접근 제어지시자로 지정한 뒤 Getter, Setter를 통해 Field의 값을 변경, 호출한다
   - Getter : 값을 호출, Setter : 값을 변경

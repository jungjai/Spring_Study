# 자바 기초 2

## 0. static

- 변수나 메소드 앞에 static 키워드를 붙여 사용
- 전역, 정적의 의미로 사용
- static 맴버 변수, static method가 있다

JVM 구동시 Runtime Data Areas의 Method(Static) Area에 적재된다 (= 프로그램 시작시 인스턴트화 됨)

프로그램 시작 후 그래서 클래스나 메소드에서 별도의 인스턴트화 없이도 사용이 가능

1. static 변수
   1. static으로 설정하면 같은 곳의 메모리 주소(동일 참조 값)만을 가리키기 때문에 static 변수의 값을 공유하게 된다
   2. 클래스 변수라고도 불림
   3. 모든 클래스는 해당 변수를 공유
   4. 인스턴트화 하지 않고도 사용 가능
   5. 보통 final 키워드와 같이 사용
2. static Method
   1. static으로 설정하면 같은 곳의 메모리 주소(동일한 참조 값)만을 가리키기 때문에 static method의 값을 공유하게 된다
   2. 클래스 메소드라고도 불림
   3. Override가 불가능
   4. static Method에서는 인스턴스 변수에 접근이 불가능하다. static 변수에서만 접근이 가능

## 1. final

- 해당 Entity가 오직 한 번 할당 될 수 있음을 의미
- 상속 / 변경을 금지하는 규제
- final 변수 : 해당 변수가 생성자나 대입 연산자를 통해 한 번만 초기화 가능함을 의미
- final 메소드 : 해당 메소드를 @Override 하거나 숨길 수 없음을 의미
- final 클래스 : 해당 클래스를 상속할 수 없음을 의미. 즉, 상속 계층 구조에서 마지막 클래스를 의미
- 상수를 표현할 때 static과 같이 사용 (final static 상수이름)
- final 키워드가 붙으면 해당 객체는 immutable이 된다

1. Mutable & Immutable
   1. Mutable
      - 변경 가능 객체, 상태를 바꿀 수 있는 객체
      - 최초 생성 이후에도 자유롭게 값 변경 가능
      - StringBuilder, StringBuffer, 참조 타입 변수
      - Final 키워드를 붙이면 immutable
   2. Immutable
      - 변경 불가 객체, 상태를 바꿀 수 없는 객체
      - 최초 생성(인스턴트화) 이후로는 값 변경 불가
      - Int 같은 기본 자료형 & String

** final은 꼭 값이 변하지 않을(immutable) 변수에 final을 붙여야 한다 **


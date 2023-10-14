Learn about Spring basic 

# 스프링의 진짜 핵심
- 스프링은 자바 언어 기반의 프레임워크
- 자바 언어의 가장 큰 특징 - 객체 지향 언어
- 스프링은 객체 지향 언어가 가진 강력한 특징을 살려내는 프레임워크
- 스프링은 좋은 객체 지향 애플리케이션을 개발할 수 있게 도와주는 프레임워크

### 다형성 
- 역할과 구현으로 세상을 구분
- `클라이언트에 영향을 주지 않고` 새로운 기능을 줄 수 있다.
  - 예시
    - 운전자 / 자동차
    - 공연 무대
    - 키보드, 마우스 등
  - 역할과 구현을 분리
    - 역할과 구현으로 구분하면 세상이 단순해지고, 유연해지며 변경도 편리해진다.
    - 장점
      - `클라이언트`는 대상의 역할(인터페이스)만 알면 된다.
      - `클라이언트`는 구현 대상의 `내부 구조를 몰라도` 된다.
      - `클라이언트`는 구현 대상의 내부 구조가 변경되어도 영향을 받지 않는다.
      - `클라이언트`는 구현 대상 자체를 변경해도 영향을 받지 않는다.
  - 자바 언어의 다형성을 활용
    - 역할 = 인터페이스
    - 구현 = 인터페이스를 구현한 클래스, 구현 객체
    - 객체를 설계할 때 역할과 구현을 명확히 분리
    - 객체 설계시 역할(인터페이스)을 먼저 부여하고, 그 역할을 수행하는 구현 객체 만들기
  - 다형성의 본질
    - 인터페이스를 구현한 객체 인스턴스를 `실행 시점`에 `유연`하게 `변경`할 수 있다.
    - 다형성의 본질을 이해하려면 `협력`이라는 객체 사이의 관계에서 시작해야함
    - `클라이언트를 변경하지 않고, 서버의 구현 기능을 유연하게 변경할 수 있다.`
  - 한계
    - 역할(인터페이스) 자체가 변하면, 클라이언트, 서버 모두에 큰 변경이 발생
    - 만약 자동차 역할을 비행기 역할로 변경해야 한다면?
    - 연극 대본 자체가 변경되어야 한다면?
    - USB 인터페이스가 변경된다면?

### 스프링과 객체 지향
- 다형성이 가장 중요하다!
- 스프링은 다양성을 극대화해서 이용할 수 있게 도와준다.
- 스프링에서 이야기하는 제어의 역전(IoC), 의존관계 주입(DI)은 다형성을 활용해서 역할과 구현을 편리하게 다룰 수 있도록 지원한다.
- 스프링을 사용하면 마치 레고 블럭 조립하듯이! 공연 무대의 배우를 선택하듯이! 구현을 편리하게 변경할 수 있다.
---
### ⭐ 역할과 구현으로 구분하는 것이 무엇보다 중요하다.
### ⭐ 좋은 개발 습관은 제약을 두는 것이다.
### SOLID Principle
- 클린코드로 유명한 로버트 마틴이 좋은 객체 지향 설계의 5가지 원칙을 정리
- SRP : 단일 책임 원칙(Single Responsibility Principle)
- OCP : 개방-폐쇄 원칙(Open/Closed Principle)
- LSP : 리스코프 치환 원칙(Liskov Substitution Principle)
- ISP : 인터페이스 분리 원칙(Interface Segregation Principle)
- DIP : 의존관계 역전 원칙(Dependency Inversion Principle)

1. SRP 단일 책임 원칙  
Single Responsibility Principle
   - *한 클래스는 하나의 책임만 가져야한다.*
   - 하나의 책임이라는 것은 모호하다. 클 수 있고, 작을 수 있다. 문맥과 상황에 따라 다르다.
   - 중요한 기준은 변경이다. 변경이 있을 때 파급 효과가 적으면 단일 책임 원칙을 잘 따른 것이다.
   - 예) UI 변경, 객체의 생성과 사용을 분리

2. OCP 개방-폐쇄 원칙  
Open/Closed Principle
   - *소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다.*
   - 다형성을 활용해보자
   - 인터페이스를 구현한 새로운 클래스를 하나 만들어서 새로운 기능을 구현
   - 지금까지 배운 역할과 구현의 분리를 생각해보자

3. LSP 리스코프 치환 원칙  
Liskov Substitution Principle
   - *프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야한다.*
   - 다형성에서 하위 클래스는 인터페이스 규약을 다 지켜야 한다는 것, 다형성을 지원하기 위한 원칙, 인터페이스를 구현한 구현체를 믿고 사용하려면 이 원칙이 필요하다.
   - 단순히 컴파일에 성공하는 것을 넘어서는 이야기
   - 예) 자동차 인터페이스의 엑셀은 앞으로 가라는 기능, 뒤로 가게 구현하면 LSP 위반, 느리더라도 앞으로 가야함

4. ISP 인터페이스 분리 원칙  
Interface Segregation Principle
   - *특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다.*
   - 자동차 인터페이스 -> 운전 인터페이스, 정비 인터페이스로 분리
   - 사용자 클라이언트 -> 운전자 클라이언트, 정비사 클라이언트로 분리
   - 분리하면 정비 인터페이스 자체가 변해도 운전자 클라이언트에 영향을 주지 않음
   - 인터페이스가 명확해지고, 대체 가능성이 높아진다.

5. DIP 의존관계 역전 원칙  
Dependency Inversion Principle
   - *프로그래머는 "추상화에 의존해야지, 구체화에 의존하면 안 된다." 의존성 주입은 이 원칙을 따르는 방법 중 하나다.*
   - 쉽게 이야기해서 구현 클래스에 의존하지 말고, 인터페이스에 의존하라는 뜻
   - 앞에서 이야기한 `역할(Role)에 의존하게 해야 한다는 것과 같다.` 객체 세상도 클라이언트가 인터페이스에 의존해야 유연하게 구현체를 변경할 수 있다.
   - 구현체에 의존하게 되면 변경이 아주 어려워진다.

### 다시 스프링으로
스프링 이야기에 왜 객체 지향 이야기가 나오는가?
- 스프링은 다음 기술로 다형성 + OCP, DIP를 가능하게 지원
  - DI(Dependency Injection) : 의존관계, 의존성 주입
  - DI 컨테이너 제공
- `클라이언트 코드의 변경 없이 기능 확장`
- 쉽게 부품을 교체하듯이 개발

스프링이 없던 시절로
- 옛날 어떤 개발자가 좋은 객체 지향 개발을 하려고 OCP, DIP 원칙을 지키면서 개발을 해보니, 너무 할일이 많았다. 배보다 배꼽이 크다. 그래서 프레임워크로 만들어버림
- 순수하게 자바로 OCP, DIP 원칙들을 지키면서 개발을 해보면, 결국 스프링 프레임워크를 만들게 된다. (더 정확히는 DI 컨테이너)
- DI 개념은 말로 설명해도 이해가 잘 안된다. 코드로 짜봐야 필요성을 알게된다!
실무고민
- 하지만 인터페이스를 도입하면 추상화라는 비용이 발생한다.
- 기능을 확장할 가능성이 없다면, 구체 클래스를 직접 사용하고, 향후 꼭 필요할 때 리팩토링해서 인터페이스를 도입하는 것도 방법이다.
---
### 관심사의 분리
- 애플리케이션을 하나의 공연이라 생각해보자. 각각의 인터페이스를 배역(배우 역할)이라 생각하자. 그런데! 실제 배역 맞는 배우를 선택하는 것은 누가 하는가?
- 로미오와 줄리엣 공연을 하면 로미오 역할을 누가 할지 줄리엣 역할을 누가 할지는 배우들이 정하는게 아니다. 이전 코드는 마치 로미오 역할(인터페이스)을 하는 레오나르도 디카프리오(구현체, 배우)가 줄리엣 역할(인터페이스)을 하는 여자 주인공(구현체, 배우)을 직접 초빙하는 것과 같다. 디카프리오는 공연도 해야하고 동시에 여자 주인공도 공연데 직접 초빙해야 하는 `다양한 책임`을 가지고있다.
- 관심사를 분리하자
  - 배우는 본인의 역할인 배역을 수행하는 것에만 집중해야 한다.
  - 디카프리오는 어떤 여자 주인공이 선택되더라도 똑같이 공연할 수 있어야 한다.
  - 공연을 구성하고, 담당 배우를 섭외하고, 역할에 맞는 배우를 지정하는 책임을 담당하는 별도의 `공연 기획자`가 나올시점이다.
  - 공연 기획자를 만들고, 배우와 공연 기획자의 책임을 확실히 분리하자

### AppConfig 등장
- 애플리케이션의 전체 동작 방식을 구성(config)하기 위해, `구현 객체를 생성`하고, `연결`하는 책임을 가지는 별도의 설정 클래스를 만들자.

### IoC, DI, Container 🕋 -> 🪑🚪🧳
1. 제어의 역전 IoC(Inversion of Control)
   - 기존 프로그램은 클라이언트 구현 객체가 스스로 필요한 서버 구현 객체를 생성하고, 연결하고, 실행했다. 한 마디로 구현 객체가 프로그램의 제어 흐름을 스스로 조종했다. 개발자 입장에서는 자연스러운 흐름이다.
   - 반면에 AppConfig가 등장한 이후에 구현 객체는 자신이 로직을 실행하는 역할만 담당한다. 프로그램의 제어 흐름은 이제 AppConfig가 가져간다. 예를들어서 'OrderServiceImpl'은 필요한 인터페이스들을 호출하지만 어떤 구현 객체들이 실행될지 모른다.
   - 프로그램에 대한 제어 흐름에 대한 권한은 모두 AppConfig가 가지고 있다. 심지어 'OrderServiceImpl'도 AppConfig가 생성한다. 그리고 AppConfig는 'OrderServiceImpl'이 아닌 OrderService 인터페이스의 다른 구현 객체를 생성하고 실행할 수도 있다. 그런 사실도 모른체 'OrderServiceImpl'은 묵묵히 자신의 로직을 실행할 뿐이다.
   - 이렇듯 프로그램의 제어 흐름을 직접 제어하는 것이 아니라 외부에서 관리하는 것을 제어의 역전(IoC)이라고 한다.

2. 의존관계 주입 DI(Dependency Injection)
   - 'OrderServiceImpl'은 'DiscountPolicy' 인터페이스에 의존한다. 실제 어떤 구현 객체가 사용될지는 모른다.
   - 의존관계는 `정적인 의존 관계와, 실행 시점에 결정되는 동적인 객체(인스턴스) 의존 관계`들을 분리해서 생각해야 한다.

   1. `정적인 클래스 의존 관계`
      - 클래스가 사용하는 import 코드만 보고 의존관계를 쉽게 판단할 수 있다. 정적인 의존관계는 애플리케이션을 실행하지 않아도 분석할 수 있다.

   2. `동적인 객체 인스턴스 의존 관계`
      - 애플리케이션 실행 시점에 실제 생성된 객체 인스턴스의 참조가 연결된 의존 관계다.
      - 애플리케이션 '실행 시점(런타임)'에 외부에서 실제 구현 객체를 생성하고 클라이언트에 전달해서 클라이언트와 서버의 실제 의존관계가 연결 되는 것을 '의존관계 주입'이라한다.
      - 객체 인스턴스를 생성하고, 그 참조값을 전달해서 연결된다.
      - 의존관계 주입을 사용하면 클라이언트 코드를 변경하지 않고, 클라이언트가 호출하는 대상의 타입 인스턴스를 변경할 수 있다.
      - 의존관계 주입을 사용하면 정적인 클래스 의존관계를 변경하지 않고, 동적인 객체 인스턴스 의존관계를 쉽게 변경할 수 있다.

3. IoC 컨테이너, DI 컨테이너
   - AppConfig처럼 객체를 생성하고 관리하면서 의존관계를 연결해 주는 것을 IoC컨테이너 또는 `DI 컨테이너`라 한다.
   - 의존관계 주입에 초점을 맞추어 최근에는 주로 DI 컨테이너라 한다.
   - 또는 어셈블러, 오브젝트 팩토리 등으로 불리기도 한다.
---
### Singleton Container and Pattern 🎲 🗃
1. Singleton Container
   - 웹 애플리케이션 싱글톤
   - 스프링은 태생이 기업용 온라인 서비스 기술을 지원하기 위해 탄생했다.
   - 대부분의 스프링 애플리케이션은 웹 애플리케이션이다. 물론 웹이 아닌 애플리케이션 개발도 얼마든지 개발할 수 있다.
   - 웹 애플리케이션은 보통 여러 고객이 동시에 요청을 한다.

2. Singleton Pattern
   - 클래스의 인스턴스가 딱 1개만 생성되는 것을 보장하는 디자인 패턴이다.
   - 그래서 객체 인스턴스를 2개 이상 생성하지 못 하도록 막아야 한다.
   - private 생성자를 사용해서 외부에서 임의로 new를 막아야한다.

3. Singleton Container의 장점과 주의점(실무에서 중요)
   1. `장점`
      - 스프링 컨테이너는 싱글톤 패턴의 문제점을 해결하면서, 객체 인스턴스를 싱글톤(1개만 생성)으로 관리한다. 지금까지 우리가 학습한 스프링 빈이 바로 싱글톤으로 관리되는 빈이다.
      - 스프링 컨테이너는 싱글톤 패턴을 적용하지 않아도, 객체 인스턴스를 싱글톤으로 관리한다. 이전에 설명한 컨테이너 생성 과정을 자세히 보자. 컨테이너는 객체를 하나만 생성해서 관리한다.
      - 스프링 컨테이너는 싱글톤 컨테이너 역할을 한다. 이렇게 싱글톤 객체를 생성하고 관리하는 기능을 싱글톤 레지스트리라 한다.
      - 스프링 컨테이너의 이런 기능 덕분에 싱글톤 패턴의 모든 단점을 해결하면서 객체를 싱글톤으로 유지할 수 있다.
   2. `주의점`
      - 싱글톤 패턴이든, 스프링 같은 싱글톤 컨테이너를 사용하든, 객체 인스턴스를 하나만 생성해서 공유하는 싱글톤 방식은 여러 클라이언트가 하나의 같은 객체 인스턴스를 공유하기 때문에 싱글톤 객체는 상태 유지(stateful)하게 설계하면 안 된다.
      - 무상태(stateless)로 설계해야한다.
      - 특정 클라이언트에 의존적인 필드가 있으면 안 된다.
      - 특정 클라이언트가 값을 변경할 수 있는 필드가 있으면 안 된다.
      - 가급적 읽기만 가능해야 한다.
      - 필드 대신에 자바에서 공유되지 않은, 지역변수, 파라미터, ThreadLocal등을 사용해야 한다.
      - 스프링 빈의 필드에 공유 값을 설정하면 정말 큰 장애가 발생할 수 있다.
---
### 스프링 빈 설정 메타 정보 - Bean Definition
- 스프링은 어떻게 이런 다양한 설정 형식을 지원하는 것일까? 그 중심에는 `Bean Definition`이라는 추상화가 있다.
- 쉽게 이야기해서 *역할과 구현을 개념적으로 나눈 것*이다!
  - XML을 읽어서 BeanDefinition을 만들면 된다.
  - 자바 코드를 읽어서 BeanDefinition을 만들면 된다.
  - 스프링 컨테이너는 자바 코드인지, XML인지 몰라도 된다. 오직 BeanDefinition만 알면 된다.
- `BeanDefinition`을 빈 설정 메타정보라 한다.
  - `@Bean`, `<bean>`당 각각 하나씩 메타 정보가 생성된다.
- 스프링 컨테이너는 이 메타정보를 기반으로 스프링 빈을 생성한다.
---
### 웹 애플리케이션과 싱글톤
- 스프링은 태생이 기업용 온라인 서비스 기술을 지원하기 위해 탄생했다.
- 대부분의 스프링 애플리케이션은 웹 애플리케이션이다. 물론 웹이 아닌 애플리케이션 개발도 얼마든지 개발할 수 있다.
- 웹 애플리케이션은 보통 여러 고객이 동시에 요청을 한다.
- 우리가 만들었던 스프링 없는 순수한 DI 컨테이너인 AppConfig는 요청을 할 때 마다 객체를 새로 생성한다.
- 고객 트래픽이 초당 100이 나오면 초당 100개 객체가 생성되고 소멸된다! -> 메모리 낭비가 심하다.
- 해결방안은 해당 객체가 딱 1개만 생성되고, 공유하도록 설계하면 된다. -> 싱글톤 패턴

### 싱글톤 패턴
- 클래스의 인스턴스가 딱 1개만 생성되는 것을 보장하는 디자인 패턴이다.
- 그래서 객체 인스턴스를 2개 이상 생성하지 못 하도록 막아야 한다.
  - private 생성자를 사용해서 외부에서 임의로 new 키워드를 사용하지 못 하도록 막아야 한다.
  1. static 영역에 객체 instance를 미리 하나 생성해서 올려준다.
  2. 이 객체 인스턴스가 필요하면 오직 `getInstance()`메서드를 통해서만 조회할 수 있다. 이 메서드를 호출하면 항상 같은 인스턴스를 반환한다.
  3. 딱 1개의 인스턴스만 존재해야 하므로, 생성자를 private으로 막아서 혹시라도 외부에서 new 키워드로 객체 인스턴스가 생성되는 것을 막는다.
- *싱글톤 패턴 문제점*
  - 싱글톤 패턴을 구현하는 코드 자체가 많이 들어간다.
  - 의존관계상 클라이언트가 구체 클래스에 의존한다. -> DIP를 위반한다.
  - 클라이언트가 구체 클래스에 의존해서 OCP 원칙을 위반할 가능성이 높다.
  - 테스트하기 어렵다.
  - 내부 속성을 변경하거나 초기화하기 어렵다.
  - private 생성자로 자식클래스를 만들기 어렵다.
  - 결론적으로 유연성이 떨어진다.
  - 안티패턴으로 불리기도 한다.

### 싱글톤 컨테이너
스프링 컨테이너는 싱글톤 패턴의 문제점을 해결하면서, 객체 인스턴스를 싱글톤(1개만 생성)으로 관리한다.
지금까지 우리가 학습한 스프링 빈이 바로 싱글톤으로 관리되는 빈이다.
- *싱글톤 컨테이너*
  - 스프링 컨테이너는 싱글톤 패턴을 적용하지 않아도, 객체 인스턴스를 싱글톤으로 관리한다.
    - 이전에 설명한 컨테이너 생성 과정을 자세히 보자. 컨테이너는 객체를 하나만 생성해서 관리한다.
  - 스프링 컨테이너는 싱글톤 컨테이너 역할을 한다. 이렇게 싱글톤 객체를 생성하고 관리하는 기능을 싱글톤 레지스트리라고 한다.
  - 스프링 컨테이너의 이런 기능 덕분에 싱글톤 패턴의 모든 단점을 해결하면서 객체를 싱글톤으로 유지할 수 있다.
    - 싱글톤 패턴을 위한 지저분한 코드가 들어가지 않아도 된다.
    - DIP, OCP, 테스트, private 생성자로 부터 자유롭게 싱글톤을 사용할 수 있다.
  - 스프링 컨테이너 덕분에 고객의 요청이 올 때 마다 객체를 생성하는 것이 아니라, 이미 만들어진 객체를 공유해서 효율적으로 재사용할 수 있다.
  - 참고 : 스프링의 기본 빈 등록 방식은 싱글톤이지만, 싱글톤 방식만 지원하는 것은 아니다. 요청할 때 마다 새로운 객체를 생성해서 반환하는 기능도 제공한다. 자세한 내용은 뒤에 빈 스코프 참고

### 싱글톤 방식의 주의점
- 싱글톤 패턴이든, 스프링 같은 싱글톤 컨테이너를 사용하든, 객체 인스턴스를 하나만 생성해서 공유하는 싱글톤 방식은 여러 클라이언트가 하나의 같은 객체 인스턴스를 공유하기 때문에 싱글톤 객체는 상태를 유지(stateful)하게 설계하면 안 된다.
- 무상태(stateless)로 설계해야 한다!
  - 특정 클라이언트에 의존적인 필드가 있으면 안 된다.
  - 특정 클라이언트가 값을 변경할 수 있는 필드가 있으면 안 된다!
  - 가급적 읽기만 가능해야 한다.
  - 필드 대신에 자바에서 공유되지 않는, 지역변수, 파라미터, ThreadLocal 등을 사용해야 한다.
- 스프링 빈의 필드에 공유 값을 설정하면 정말 큰 장애가 발생할 수 있다!!!

### @Configuration과 바이트코드 조작의 마법
스프링 컨테이너는 싱글톤 레지스트리다. 따라서 스프링 빈이 싱글톤이 되도록 보장해주어야 한다. 그런데 스프링이 자바 코드까지 어떻게 하기는 어렵다.
자바 코드를 보면 분명 3번 호출되어야 하는 것이 맞다. 그래서 스프링은 클래스의 바이트코드를 조작하는 라이브러리를 사용한다.
모든 비밀은 `@Configuration`을 적용한 `AppConfig`에 있다.
순수한 클래스라면 다음과 같이 출력되어야 한다. `class hello.core.AppConfig`
그런데 예상과는 다르게 클래스 명에 xxxCGLIB가 붙으면서 상당히 복잡해진 것을 볼 수 있다.
이것은 내가 만든 클래스가 아니라 스프링이 CGLIB라는 바이트코드 조작 라이브러리를 사용해서 AppConfig 클래스를 상속받은
임의의 다른 클래스를 만들고, 그 다른 클래스를 스프링 빈으로 등록한 것이다!
- @Bean이 붙은 메서드마다 이미 스프링 빈이 존재하면 빈을 반환하고, 스프링 빈이 없으면 생성해서 스프링 빈으로 등록하고 반환하는 코드가 동적으로 만들어진다.
- 덕분에 싱글톤이 보장되는 것이다.
- *참고* AppConfig@CGLIB는 AppConfig의 자식 타입이므로, AppConfig 타입으로 조회할 수 있다.
---
### Component Scan - 탐색 위치와 기본 스캔 대상
- 탐색할 패키지의 시작 위치 지정
- 모든 자바 클래스를 다 컴포넌트 스캔하면 시간이 오래 걸린다. 그래서 꼭 필요한 위치부터 탐색하도록 시작 위치를 지정할 수 있다.
- `basePackages` : 탐색할 패키지의 시작 위치를 지정한다. 이 패키지를 포함해서 하위 패키지를 모두 탐색한다.
  - `basePackages = {"hello.core", "hello.service"}` 이렇게 여러 시작 위치를 지정할 수도 있다.
- `basePackageClasses` : 지정한 클래스의 패키지를 탐색 시작 위치로 지정한다.
- 만약 지정하지 않으면 `@ComponentScan`이 붙은 설정 정보 클래스의 패키지가 시작 위치가 된다.

- *권장하는 방법*
  <p>개인적으로 즐겨 사용하는 방법은 패키지 위치를 지정하지 않고, 설정 정보 클래스의 위치를 프로젝트 최상단에 두는 것이다.
     최근 스프링 부트도 이 방법을 기본으로 제공한다.
  </p>
- 예를 들어서 프로젝트가 다음과 같이 구조가 되어 있으면
  - `com.hello`
  - `com.hello.service`
  - `com.hello.repository`
- `com.hello` -> 프로젝트 시작 루트, 여기에 AppConfig 같은 메인 설정 정보를 두고, @ComponentScan 애노테이션을 붙이고, `basePackages` 지정은 생략한다.
<p>
이렇게 하면 `com.hello`를 포함한 하위는 모두 자동으로 컴포넌트 스캔의 대상이 된다.
그리고 프로젝트 메인 설정 정보는 프로젝트를 대표하는 정보이기 때문에 프로젝트 시작 루트 위치에 두는 것이 좋다 생각한다.
참고로 스프링 부트를 사용하면 스프링 부트의 대표 시작 정보인 `@SpringBootApplication`를 이 프로젝트 시작 루트 위치에 두는 것이 관례이다.
(그리고 이 설정안에 바로 `@ComponentScan`이 들어있다!)
</p> 

### ⭐ 개발할 때 어설픈 추상화나 어설픈 코드 줄이기 보다 코드를 좀 더 쓰더라도(중복이 있더라도) 명확한 것이 훨씬 더 좋은 선택이다.

---
### Various Dependency Injection Ways 💉🧬
스프링 라이프 사이클에서 스프링 빈을 등록하는 단계랑 스프링 의존관계를 주입하는 단계가 구분되어있다.
- 생성자 주입
- 수정자 주입(setter 주입)
- 필드 주입
- 일반 메서드 주입

1. 생성자 주입
   - 이름 그대로 생성자를 통해서 의존관계를 주입 받는 방법이다.
   - 지금까지 우리가 진행했던 방법이 바로 생성자 주입이다.
   - 특징
     - 생성자 호출 시점에 딱 1번만 호출되는 것이 보장된다.
     - `* 불변, 필수 *` 의존관계에 사용
     - 클래스 내의 생성자가 딱 1개일 경우는 @Autowired를 생략해도 된다.

2. 수정자 주입(setter 주입)
   - setter라 불리는 필드의 값을 변경하는 수정자 메서드를 통해서 의존관계를 주입하는 방법이다.
   - 특징
     - `* 선택, 변경 *` 가능성이 있는 의존관계에 사용
     - 자바빈 프로퍼티 규약의 수정자 메서드 방식을 사용하는 방법이다.

3. 필드 주입
   - 이름 그대로 필드에 바로 주입하는 방법이다.
     (* 안티 패턴)
   - 특징
     - 코드가 간결해서 많은 개발자들을 유혹하지만 외부에서 변경이 불가능해서 테스트하기 힘들다는 치명적인 단점이 있다.
     - DI 프레임워크가 없으면 아무것도 할 수 없다.
     - 사용하지말자!
       - (예외) 애플리케이션의 실제 코드와 관계 없는 테스트 코드에선 사용 가능
       - (예외) 스프링 설정을 목적으로 하는 @Configuration 같은 곳에서만 특별한 용도로 사용

4. 일반 메서드 주입
   - 일반 메서드를 통해서 주입 받을 수 있다.
   - 특징
     - 한번에 여러 필드를 주입 받을 수 있다.
     - 일반적으로 잘 사용하지 않는다.

참고 : 어쩌면 당연한 이야기이지만 의존관계 자동 주입은 스프링 컨테이너가 관리하는 스프링 빈이어야 동작한다.
스프링 빈이 아닌 `Member` 같은 클래스에서 `@Autowired` 코드를 적용해도 아무 기능도 동작하지 않는다.

### 생성자 주입을 선택해라!
과거에는 수정자 주입과 필드 주입을 많이 사용했지만, 최근에는 스프링을 포함한 DI Framework 대부분이 생성자 주입을 권장한다. 그 이유는 다음과 같다.
- `불변`
- `누락`
- `fianl keyword`

1. 불변
   - 대부분의 의존관계 주입은 한번 일어나면 애플리케이션 종료시점까지 의존관계를 변경할 일이 없다. 오히려 대부분의 의존관계는 애플리케이션 종료 전까지 변하면 안 된다.(불변해야한다)
   - 수정자 주입을 사용하면, setXxxx 메서드를 public으로 열어두어야 한다.
   - 누군가 실수로 변경할 수도 있고, 변경하면 안 되는 메서드를 열어두는 것은 좋은 설계 방법이 아니다.
   - 생성자 주입은 객체를 생성할 때 딱 1번만 호출되므로 이후에 호출되는 일이 없다. 따라서 불변하게 설계할 수 있다.

2. 누락
   - 생성자 주입을 사용하면 테스트 코드에서 주입 데이터를 `누락`했을 때 `컴파일 오류`가 발생한다.

3. final keyword
   - 생성자 주입을 사용하면 필드에 `final` 키워드를 사용할 수 있다. 그래서 생성자에서 혹시라도 값이 설정되지 않는 오류를 컴파일 시점에 막아준다.
   - `final` -> 이 의미는 생성자로만 값을 입력해주거나 처음에 수동으로만 값을 입력해 줄 수 있기 때문에 `불변`이다.

4. 📋 Conclusion
   - `참고`
     - 기억하자! `🌟컴파일 오류는 세상에서 가장 빠르고, 좋은 오류다!`
     - 수정자 주입을 포함한 나머지 주입 방식은 모두 생성자 이후에 호출되므로, 필드에 `final` 키워드를 사용할 수 없다. 오직 생성자 주입 방식만 `fianl` 키워드를 사용할 수 있다.
   - 생성자 주입 방식을 선택하는 이유는 여러가지가 있지만, 프레임워크에 의존하지 않고, 순수한 자바 언어의 특징을 잘 살리는 방법이기도 하다.
   - 기본으로 생성자 주입을 사용하고, 필수 값이 아닌 경우에는 수정자 주입 방식을 옵션으로 부여하면 된다. 생성자 주입과 수정자 주입을 동시에 사용할 수 있다.
   - 항상 생성자 주입을 선택하라! 그리고 가끔 옵션이 필요하면 수정자 주입을 선택하라. 필드 주입은 사용하지 않는게 좋다.

### 롬복과 최신 트랜드
막상 개발을 해보면, 대부분이 다 불변이고, 그래서 다음과 같이 생성자에 final 키워드를 사용하게 된다.
그런데 생성자도 만들어야 하고, 주입 받은 값을 대입하는 코드도 만들어야 하고...
필드 주입처럼 좀 편리하게 하는 사용 방버은 없을까?
역시 개발자는 귀찮은 것은 못 참는다!
- 롬복 라이브러리가 제공하는 `@RequiredArgsConstructor` 기능을 사용하면 final이 붙은 필드를 모아서 생성자를 자동으로 만들어준다. (다음 코드에는 보이지 않지만 실제 호출 가능하다.)
- 롬복이 자바의 애노테이션 프로세서라는 기능을 이용해서 컴파일 시점에 생성자 코드를 자동으로 생성해준다. 실제 `class`를 열어보면 다음 코드가 추가되어 있는 것을 확인할 수 있다.

### 조회 - 빈이 2개 이상 문제
스프링 빈 조회에서 학습했듯이 타입으로 조회하면 선택된 빈이 2개 이상일 때 문제가 발생한다.
`DiscountPolicy`의 하위타입인 `FixDiscountPolicy`, `RateDiscountPolicy` 둘다 스프링 빈으로 선언해보자.
오류메시지가 친절하게도 하나의 빈을 기대했는데 `fixDiscountPolicy`, `RateDiscountPolicy` 2개가 발견되었다고 알려준다.
이때 하위 타입으로 지정할 수도 있지만, 하위 타입으로 지정하는 것은 DIP를 위배하고 유연성이 떨어진다.
그리고 이름만 다르고, 완전히 똑같은 타입의 스프링 빈이 2개 있을 때 해결이 안 된다.
스프링 빈을 수동 등록해서 문제를 해결해도 되지만, 의존 관계 자동 주입에서 해결하는 여러 방법이 있다.

### @Autowired 필드명, @Qualifier, @Primary
조회 대상 빈이 2개 이상일 때 해결 방법
- @Autowired 필드명 매칭
- @Qualifier -> @Qualifier 끼리 매칭 -> 빈 이름 매칭
- @Primary 사용

1. @Autowired 필드명 매칭
   - `@Autowired`는 타입 매칭을 시도하고, 이때 여러 빈이 있으면 필드 이름, 파라미터 이름으로 빈 이름을 추가 매칭한다.
   - `*필드명 매칭은 먼저 타입 매칭을 시도하고 그 결과에 여러 빈이 있을 때 추가로 동작하는 기능이다.*`
   - *@Autowired 매칭 정리*
     - 타입 매칭
     - 타입 매칭의 결과가 2개 이상일 때 필드명, 파라미터 명으로 빈 이름 매칭

2. @Qualifier 사용
   - `@Qualifer`는 추가 구분자를 붙여주는 방법이다. 주입 시 추가적인 방법을 제공하는 것이지 빈 이름을 변경하는 것은 아니다.
   - `*빈 등록시 @Qualifier를 붙여 준다.*`
   - `*주입시에 @Qualifier를 붙여주고 등록한 이름을 적어준다.*`
   - `@Qualifer`로 주입할 때 `@Qualifer("mainDiscountPolicy")`를 못 찾으면 어떻게 될까? 그러면 mainDiscountPolicy라는 이름의 스프링 빈을 추가로 찾는다. 하지만 경험상 `@Qualifier`는 `@Qualifier`를 찾는 용도로만 사용하는게 명확하고 좋다.
   - *@Qualifer 정리*
     - @Qualifier끼리 매칭
     - 빈 이름 매칭
     - `NoSuchBeanDefinitionException` 예외 발생

3. @Primary 사용
   - `@Primary`는 우선순위를 정하는 방법이다. @Autowired 시에 여러 빈이 매칭되면 `@Primary`가 우선권을 가진다.

여기까지 보면 `@Primary`와 `@Qualifier` 중에 어떤 것을 사용하면 좋을지 고민이 될 것이다. 
`@Qualifier`의 단점은 주입 받을 때 다음과 같이 모든 코드에 `@Qualifier`를 붙여주어야 한다는 점이다.

*@Primary, @Qualifier 활용*   
코드에서 자주 사용하는 메인 데이터베이스의 커넥션을 획득하는 스프링 빈이 있고, 코드에서 특별한 기능으로 가끔 사용하는 서브 데이터베이스의 커넥션을 획득하는 스프링 빈이 있다고 생각해보자.
메인 데이터베이스의 커넥션을 획득하는 스프링 빈은 `@Primary`를 적용해서 조회하는 곳에서 `@Qualifier`지정 없이 편리하게 조회하고, 
서브 데이터베이스 커넥션 빈을 획득할 때는 `@Qualifier`를 지정해서 명시적으로 획득하는 방식으로 사용하면 코드를 깔끔하게 유지할 수 있다.
물론 이때 메인 데이터베이스의 스프링 빈을 등록할 때 `@Qualifier`를 지정해주는 것은 상관 없다.

*우선순위*   
`@Primary`는 기본값처럼 동작하는 것이고, `@Qualifier`는 매우 상세하게 동작한다.
이런 경우 어떤 것이 우선권을 가져갈까?
스프링은 자동보다는 수동이, 넓은 범위의 선택권보다는 좁은 범위의 선택권이 우선 순위가 높다.
따라서 여기서도 `@Qualifier`가 우선권이 높다.

#### 로직분석 
    - DiscountService는 Map으로 모든 `DiscountPolicy`를 주입받는다.
    이때 `fixDiscountPolicy`, `rateDiscountPolicy`가 주입된다.
    - `discount ()` 메서드는 discountCode로 "fixDiscountPolicy"가 넘어오면
    map에서 `fixDiscountPolicy` 스프링빈을 찾아서 실행한다.
    물론 "rateDiscountPolicy"가 넘어오면 `fixDiscountPolicy` 스프링 빈을 찾아서
    실행한다.

#### 주입분석
    - `Map<String, DiscountPlicy>` : map의 키에 스프링 빈의 이름을 넣어주고,
    그 값으로 `DiscountPolicy` 타입으로 조회한 모든 스프링 빈을 담아준다.
    - `List<DiscountPolicy>` : `DiscountPolicy` 타입으로 조회한 모든 스프링
    빈을 담아준다.
    만약 해당하는 타입의 스프링 빈이 없으면, 빈 컬렉션이나 Map을 주입한다.

### "자동, 수동의 올바른 실무 운영 기준"
- *편리한 자동 기능을 기본으로 사용하자*
    - 그러면 어떤 경우에 커모넌트 스캔과 자동 주입을 사용하고, 어떤 경우에 설정 정보를 통해서 수동으로 빈을 등록하고, 의존관게도 수동으로 주입해야 할까?
    - 결론부터 이야기하면, 스프링이 나오고 시간이 갈수록 점점 더 자동을 선호하는 추세다. 스프링은 `@Component` 뿐만 아니라 `@Controller`, `@Service`, `@Repository`처럼 계층에 맞추어 일반적인 애플리케이션 로직을 자동으로 스캔할 수 있도록 지원한다. 거기에 더해서 최근 스프링 부트는 컴포넌트 스캔을 기본으로 사용하고, 스프링 부트의 다양한 스프링 빈들도 조건이 맞으면 자동으로 등록하도록 설게했다.
    - 설정 정보를 기반으로 애플리 케이션을 구성하는 부분과 실제 동작하는 부분을 명확하게 나누는 것이 이상적이지만, 개발자 입장에서 스프링 빈을 하나 등록할 때 `@Component`만 넣어주면 끝나는 일을 `@Configuration` 설정 정보에 가서 `@Bean`을 적고, 객체를 생성하고, 주입할 대상을 일일이 적어주는 과정은 상당히 번거롭다. 또 관리할 빈이 많아서 설정 정보가 커지면 설정 정보를 관리하는 것 자체가 부담이 된다. 그리고 결정적으로 자동 빈 등록을 사용해도 OCP, DIP를 지킬 수 있다.
- *그러면 수동 빈 등록은 언제 사용하면 좋을까?*
  - 애플리케이션은 크게 업무로직과 기술 지원 로직으로 나눌 수 있다.
    - "업무 로직 빈" : 웹을 지원하는 컨트롤러, 핵심 비즈니스 로직이 있는 서비스, 데이터 계층의 로직을 처리하는 리포지토리 등이 모두 업무 로직이다. 보통 비즈니스 요구사항을 개발할 때 추가되거나 변경된다.
    - "기술 지원 빈" : 기술적인 문제나 공통 관심사(AOP)를 처리할 때 주로 사용된다. 데이터베이스 연결이나 공통 로그 처리처럼 업무 로직을 지원하기 위한 하부 기술이나 공통 기술들이다.
    - 업무 로직은 숫자도 매우 많고, 한번 개발해야 하면 컨트롤러, 서비스, 리포지토리처럼 어느 정도 유사한 패턴이 있다. 이런 경우 자동 기능을 적극 사용하는 것이 좋다. 보통 문제가 발생해도 어떤 곳에서 문제가 발생했는지 명확하게 파악하기 쉽다.
    - 기술 지원 로직은 업무 로직과 비교해서 그 수가 매우 적고, 보통 애플리케이션 전반에 걸쳐서 광범위하게 영향을 미친다. 그리고 업무 로직은 문제가 발생했을때 어디가 문제인지 명확하게 잘 드러나지만, 기술 지원 로직은 적용이 잘 되고 있는지 아닌지 조차 파악하기 어려운 경우가 많다. 그래서 이런 기술 지원 로직들은 가급적 수동 빈 등록을 사용해서 명확하게 드러내는 것이 좋다.
- "애플리케이션에 광범위하게 영향을 미치는 기술 지원 객체는 수동 빈으로 등록해서 딱! 설정 정보에 바로 나타나게 하는 것이 유지 보수하기 좋다."
- 비즈니스 로직 중에서 다형성을 적극 활용할 때
  - 의존관계 자동 주입 - 조회한 빈이 모두 필요할 떄, List, Map을 다시 보자. `DiscountService`가 의존관계 자동 주입으로 `Map<String, DiscountPolicy>` 에 주입을 받는 상황을 생각해보자. 여기에 어떤 빈들이 주입될 지, 각 빈들의 이름은 무엇인지 코드만 보고 한번에 쉽게 파악할 수 있을까? 내가 개발했으니 크게 관계가 없지만, 만약 이 코드를 다른 개발자가 개발해서 나에게 준것이라면 어떨까? 자동 등록을 사용하고 있기 떄문에 파악하려면 여러 코드를 찾아봐야 한다.
  - 이런 경우 수동 빈으로 등록하거나 또는 자동으로 하면 *특정 패키지에 같이 묶어*두는 게 좋다! 핵심은 딱 보고 이해가 되어야 한다!
  - 이 설정 정보만 봐도 한눈에 빈의 이름은 물론이고, 어떤 빈들이 주입될지 파악할 수 있다. 그래도 빈 자동 등록을 사용하고 싶으면 파악하기 좋게 `DiscountPolicy`의 구현 빈들만 따로 모아서 특정 패키지를 모아두자.
  - 참고로 *스프링과 스프링 부트가 자동으로 등록하는 수 많은 빈들은 예외*다. 이런 부분들은 스프링 자체를 잘 이해하고 스프링의 의도대로 잘 사용하는게 중요하다. 스프링 부트의 경우 `DataSource`같은 데이터베이스 연결에 사용하는 기술 지원로직까지 내부에서 자동으로 등록하는데, 이런 부분은 매뉴얼을 잘 참고해서 스프링 부트가 의도한 대로 편리하게 사용하면 된다. 반면에 *스프링 부트가 아니라 내가 직접 기술 지원객체를 스프링 빈으로 등록한다면 수동으로 등록해서 명확하게 드러내는 것이 좋다.*

#### 정리
    편리한 자동 기능을 기본으로 사용하자
    직접 등록하는 기술 지원 객체는 수동 등록
    다형성을 적극 활용하는 비즈니스 로직은 수동 등록을 고민해보자

---
### Bean Life Cycle Call Back 🤹🕙
데이터베이스 커넥션 풀이나 네트워크 소켓처럼 애플리케이션 시작 시점에 필요한 연결을 미리 해두고, 애플리케이션 종료 시점에 연결을 모두 종료하는 작업을 진행하려면, 객체의 초기화와 종료 작업이 필요하다.
- 간단하게 외부 네트워크에 미리 연결하는 객체를 하나 생성한다고 가정해보자. 실제로 네트워크에 연결하는 것은 아니고, 단순히 문자만 출력하도록 했다. 이 `NetworkClient`는 애플리케이션 시작 시점에 `connect()`를 호출해서 연결을 맺어두양 하고, 애플리케이션이 종료되면 `disconnect()`를 호출해서 연결을 끊어야 한다.
- 생성자 부분을 보면 url 정보 없이 connect가 호출되는 것을 확인할 수 있다. 너무 당연한 이야기지만 객체를 생성하는 단계에는 url이 없고, 객체를 생성한 다음에 외부에서 수정자 주입을 통해서 `setUrl()`이 호출되어야 url이 존재하게 된다.
- 스프링은 간단하게 다음과 같은 라이프 사이클을 가진다 : "객체 생성" -> "의존관계 주입"
- 스프링 빈은 객체를 생성하고, 의존관계 주입이 다 끝난 다음에야 필요한 데이터를 사용할 수 있는 준비가 완료된다. 따라서 초기화 작업은 의존관계 주입이 모두 완료되고 난 다음에 호출해야 한다. 그런데 개발자가 의존관계 주입이 모두 완료된 시점을 어떻게 알 수 있을까? *스프링은 의존관계 주입이 완료되면 스프링 빈에게 콜백 메서드를 통해서 초기화 시점을 알려주는 다양한 기능을 제공*한다. 또한 *스프링은 스프링 컨테이너가 종료되기 직전에 소멸 콜백을 준다.* 따라서 안전하게 종료 작업을 진행할 수 있다.
- 스프링 빈의 이벤트 라이프 사이클
  - "스프링 컨테이너 생성" -> "스프링 빈 생성" -> "의존관계 주입" -> "초기화 콜백" -> "사용" -> "소멸 전 콜백" -> "스프링 종료" 
  - "초기화 콜백" : 빈이 생성되고, 빈의 의존관계 주입이 완료된 후 호출
  - "소멸 전 콜백" : 빈이 소멸되기 직전에 호출"
  
### "객체의 생성과 초기화를 분리하자"
생성자는 필수 정보(파라미터)를 받고, 메모리를 할당해서 객체를 생성하는 책임을 가진다. 반면에 초기화는 이렇게 생성된 값을 활용해서 외부 커넥션을 연결하는 등 무거운 동작을 수행한다. 따라서 생성자 안에서 무거운 작업을 함께 하는 것보다는 객체를 생성하는 부분과 초기화하는 부분을 명확하게 나누는 것이 유지보수 관점에서 좋다. 물론 초기화 작업이 내부 값들만 약간 변경하는 정도로 단순한 경우에는 생성자에서 한번에 다 처리하는게 나을 수 있다.

#### 스프링은 크게 3가지 방법으로 빈 생명주기 콜백을 지원한다.
    - 인터페이스(InitializingBean, DisposableBean)
    - 설정 정보에 초기화 메서드, 종료 메서드 지정
    - @PostConstruct, @PreDestroy 애노테이션 지원
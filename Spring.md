* 생성 책임 분리

* DI 의존 관계 주입!

* 객체를 연극의 배우로 생각을 해보자. 배우가 상대 배우를 선택한다면 여러 책임을 지니게 된다. 따라서 기획자를 따로 두고 기획자가 배우를 선택하도록 해야 한다.

# SOLID

## SRP 단일 책임 원칙
- 한 클래스는 하나의 책임만 가져야 한다
## OCP 
- 확장에는 열려 있으나 변경에는 닫혀있어야 한다
## LISCOV
## IP
## DIP 의존 관계 역전 원칙
- 추상화에 의존해야지, 구체화에 의존하면 안 된다

## IoC, DI, 그리고 컨테이너
### IoC (Inversion of control)
- 구현 객체는 실행하는 역할만 담당
- 프로그램에 대한 제어 흐름에 대한 권한은 구현 객체가 아닌 다른 객체에서 설정해줌

#### framework vs library
- 프레임워크가 내가 작성한 코드를 제어하고, 대신 실행하면 그것은 프레임워크가 맞다. (JUnit)
- 반면에 내가 작성한 코드가 직접 제어의 흐름을 담당한다면 그것은 프레임워크가 아니라 라이브러리다

### DI(Dependency Injection)
- 의존 관계는 **정적인 클래스 의존 관계와 실행 시점에 결정되는 동적인 객체(인스턴스) 의존 관계** 로 분리해서 생각해야 한다.

- 정적인 의존관계
    - import만 봐도 분석 가능하다. 실제로 Diagram이라는 툴로 diagram을 볼 수 있다

- 동적인 의존관계
    - 실제로 어떤 객체가 주입될지 모름. 실행이 된 후에 알 수 있다.
    - 객체 다이어그램
    
- 정적인 클래스 의존관계를 변경하지 않고, 동적인 클래스 의존관계를 쉽게 변경 가능하다!!!

### IoC 컨테이너, DI 컨테이너
- 객체를 생성하고 관리하면서 의존관계를 연결해주는 것을 말함.
- 생성, 연결의 역할만 지님. DB repository는 어떤 객체이고 이러한 configuration을 설정해줌
- 요즘에는 대부분 **DI 컨테이너**라고 함

# Spring Annotation

- Configuration
  - 설정 정보
  
- Bean
  - Spring container에 등록됨
  
## 스프링 컨테이너
- 'ApplicationContext'를 스프링 컨테이너라 한다.
- 스프링 컨테이너가 @Configuration이 붙은 설정 클래스의 @Bean이 붙은 메서드를 모두 호출해서 반환된 객체들을 등록하고 관리한다
이렇게 스프링 컨테이너에 등록된 객체를 스프링 빈이라 한다.
  
- 설정 클래스의 Bean 메서드 명을 스프링 빈의 이름으로 사용한다.
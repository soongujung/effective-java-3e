# Item36 - 비트필드 대신 EnumSet을 사용하라

# 0. 참고자료

공식 예제 Github Repository (번역자 제공)  

- https://github.com/WegraLee/effective-java-3e-source-code/tree/master/src/effectivejava/chapter6



# 1. 핵심정리

EnumSet의 유일한 단점은 (자바 9까지는 아직) 불변 EnumSet을 만들수 없다는 것이다.  

열거할 수 있는 타입을 한데 모아 집합 형태로 사용한다고 해도 비트 필드를 사용할 이유는 없다. EnumSet 클래스는 아래와 같은 장점을 제공해주기 때문이다.  

- 비트 필드 수준의 명료함과 성능을 제공하고
- enum(열거타입)의 장점까지 선사(item 34)하기 때문이다.  

  

> **불변 EnumSet을 만들지 못하는 문제**  
>
> 자바 11까지도 이 수정은 이루어지지 않았다고 한다. 조슈아 블로크의 바람과 달리 자바 개발팀은 불변 EnumSet이 그리 필요하지 않다고 보는 것 같다.  
>
> 구글의 Guava 라이브러리를 사용하면 불변 EnumSet을 만들수 있긴 하지만(https://bit.ly/2NlxW60 참고), 이 역시 내부에서는 EnumSet을 사용해 구현했으므로 성능 면에서는 손해다.  

  

# 2. 비트필드 예제


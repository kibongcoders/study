# Java에서의 Thread
Java에서 빼놓을 수 없는 것이 있다면 그것은 JVM이다.
Thread도 마찬가지로 JVM이 Thread를 관리하게 되는데, 크게 5가지를 관리한다.
- Thread의 생명주기 관리
- Thread의 스케줄링
- Thread의 동기화
- Thread의 스택 관리
- Thread의 예외 처리

## JVM이 Thread를 관리하는 방법
### Thread의 생명주기 관리
Thread는 크게 6가지 상태를 가지고 있다.
- New
- Runnable
- Blocked
- Waiting
- Timed Waiting
- Terminated
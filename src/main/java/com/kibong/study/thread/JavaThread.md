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
  - Thread 객체가 생성되었지만 실행중이거나 실행 준비 상태는 아님 -> start() 메소드가 호출되지 않은 상태
- Runnable
  - 실행 준비중인 상태이거나 실행중인 상태 -> start() 메소드가 호출되에 Runnable인 상태
- Blocked
  - Thread가 synchronized 블록에 의해 일시정지된 상태, synchronized 키워드로 보호된 블록에 들어갈려고 하지만 다른 Thread가 사용중인 경우 -> synchronized 블록에 들어가기 위해 기다리는 상태
- Waiting
    - Thread가 다른 Thread가 특정 작업을 완료할 때까지 기다리는 상태 -> wait(), join() LockSupport.park() 메소드 호출시 발생
- Timed Waiting
    - 지정된 대기 시간 동안 다른 Thread가 특정 작업을 완료할 때까지 기다리는 상태 -> sleep(), wait(long timeout), join(long timeout), LockSupport.parkNanos() 메소드 호출시 발생
- Terminated
    - Thread가 실행을 완료 했거나 예외적으로 종료된 상태 -> run() 메소드가 종료되면 Terminated 상태
멀티스레드를 위한 클래스로 **Thread를 확장**하여 **run()** 메소드를 오버라이딩 하여 **run()** 내부에 동시다발적으로 동작시키려는 명령문을 작성한다
객체를 생성하여 **start()** 를 호출하여 [[스레드]]를 가동시킨다

- [!] 응급성이 있는 객체는 **가능하면** 다른 객체들보다 더 빨리 작업을 수행하도록 **우선순위**를 설정할 수 있다.

- **run()** : 동시다발적으로 동작시키려는 명령문을 오버라이딩한 이 메소드 내부에 작성한다
- **start()** : 여러 메소드에게 **run()** 을 하도록 시작사인을 보낸다. 동시다발 실행을 원하면  run()이 아니라 **start()** 를 객체별로 호출해야 한다
- **setPriority(int newPriority)** : 스레드의 우선순위를 설정한다. 매개변수는 상수가 있으며 Max, Min, Norm이 정해져 있다.
- **join()** : 스레드가 죽을때까지 기다린다
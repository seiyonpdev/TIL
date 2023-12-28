- 인터페이스
- 완전 추상 → 바디가 구체화된 메소드를 가질 수 없다 → start() 없음 
	→ start()하려면 [[Thread]]로 포장해야함 → Thread 생성자 중에서 Runnable을 매개변수로 받는 생성자가 있음
	- 형식
		(new Thread(Runnable 구현한 클래스 객체)).start();

- **run()** 
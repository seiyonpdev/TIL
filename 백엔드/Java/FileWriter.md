- 새 파일을 생성하는 클래스
- 생성자에 String 주소, boolean append에서 append를 true로 주면 두번째 이후로 덮어쓰기가 아니라 있던 파일에 내용이 추가된다

- 형식
	FileWriter fw = new FileWriter("c:\파일명.txt");
	fw.write("hello");
	//이렇게 하면 hello라고 써있는 '파일명'이라는 제목으로 메모장이 생성된다
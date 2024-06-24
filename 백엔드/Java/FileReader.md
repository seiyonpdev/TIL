- 파일에 있는 내용을 읽어오는 클래스

- 형식
	FileReade fr = new FileReader("c:\파일명.txt");
	String str = fr.read();
	System.out.println(str);
	fr.close();
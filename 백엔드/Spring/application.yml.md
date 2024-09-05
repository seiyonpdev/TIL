
- 스프링에서 서버를 기동할 때 전달할 설정값들을 모아놓은 파일
- DB나 kafka에 접속하기 위해 필요한 ID, PW 등을 적어둔다
	- 여기에 들어가는 ID, PW를 평문으로 두면 보안상 좋지 않기 때문에 암호화된 ID, PW를 적고 ENC()로 감싼다
	- ENC()로 감싼 암호문을 서버를 켰을 때는 복호화해서 사용해야 하므로 vm argument로 복호화 키를 줘서 서버에서 복호화 할 수 있게 한다

##### vm argument
- Boot Dashboard → local 아래에서 서버를 선택하고 우클릭 → Open Config → Argument → VM Arguments에 커스텀 설정을 적는다
- JQuery 라이브러리를 사용해 문서 객체를 조작하거나 효과를 부여할 수 있다
- 이벤트나 시각 효과를 줄 수 있다

- 형식
	<\script src="\https://code.jquery.com/jquery-3.7.1.js"><\/script>

- $("h1") : 이상태는 body의 모든 h1의 배열
- $("h1").html() : 이 상태는 첫번째 값을 가져오는 getter. 모든 값을 가져오려면 반복문 필요.
- $("h1").html("설정값") : 이 상태는 모든 값에 대한 setter

- $("h1").attr(매개변수1, 매개변수2) : 매개변수가 1개면 속성값을 읽어오고 둘이면 값을 설정한다

- $("h1").css(매개변수1, 매개변수2) : 매개변수가 1개면 값을 읽어오고 둘이면 값을 설정한다
	한번에 설정하려면 {}를 열어 객체를 매개변수로 준다.
	ex. 
	$(".box").css({
	background : "orange",
	width : 100,
	height : 100,
	float : "left",
	margin : 10
	});

- $("#a").html(data)
	data를 html 적용해서 a에 설정하고 읽어올때 사용

- $("#b").text(data)
	data를 그냥 문자열로 b에 설정하고 읽어올때 사용

- val()
	입력양식에 있는 값을 가져오거나 설정할 때 사용
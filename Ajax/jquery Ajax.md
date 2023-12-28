
- 형식
	$.ajax(url, 객체);
		$.ajax("list.jsp", {success:function(r)});
	$.ajax(객체);
		$.ajax({url:"list.jsp", 
		data:{*서버로 전달할 객체*}
		success:function(r)});

- 예시
	$.ajax("서버의 프로그램 이름", {
		success:function(arr){            **←응답이 성공적인지 체크**
			$.each(arr, function(){
				var tr = $("<\tr><\/tr>");
				var td1 = $("<\td><\/td>").html(this.name);
				var td2 = $("<\td><\/td>").html(this.age);
				var td3 = $("<\td><\/td>").html(this.addr);
				$(tr).append(td1, td2, td3);
				$("tbody").append(tr);
			})
		}
	});

- 서버로 전달할 객체를 만드는 보조 메소드
	- serialize()
		- form을 가져와서 **쿼리스트링**으로 만들어준다(get방식으로 정보를 가져올때처럼)
		- id속성으로는 작동X, form의 각 항목에서 **name 속성을 필요로 한다**
		var book = $("#myform").serialize();
	- serialiaeArray()
		- form을 가져와서 **객체**로 만들어준다
		var book = $("#myform").serializeArray();
	- $.param()
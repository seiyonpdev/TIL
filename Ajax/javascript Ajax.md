
- 형식
	var request = new XMLHttpRequest();        **←Ajax통신을 위한 객체**
	request.onreadystatechange = function(){  **←서버 응답 상태를 확인하는 이벤트**
		if(request.readyState == 4){              **←응답 완료됐는지 체크**
			if(request.status == 200){          **←멀쩡한 응답이 왔는지 체크**
				var arr = eval("("+ request.responseText +")");  **←가져온 스트링을 객체화**
				객체화한 배열을 반복문으로 돌면서 노드 생성해서 어펜드
			}
		}
	}
	request.open("전송방식", "가져올데이터가 담긴 파일", 비동기로할건지boolean);
	request.send();  ← 실제로 전송
	alert(**request.responseText**) ← 가져온 정보를 담은 변수
	

- 비동기일 때는 응답완료신호를 받고 노드를 생성한다
- 동기일때는 응답완료신호가 필요없다

- 전송방식은 정보가 오픈되는 get, 정보를 감춰주는 post중 하나
- 비동기에 false를 주면 동기 방식으로 응답이 올때까지 다른 행동을 못하고 기다린다
- 비동기 방식으로 하려면 응답이 완료됐을 때 노드를 생성하는 코드가 추가돼야 한다
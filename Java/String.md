- 다른 [[클래스]]들은 사용하려면 import 해야하지만 java.lang 패키지의 클래스들은 import하지 않고 사용할 수 있다
- String은 문자열을 표현하기 위해서 자바가 제공하는 참조 [[자료형]]
- 원래는 String도 다른 클래스들처럼 객체를 생성하고 사용해야 하지만, 특별히 기본 자료형처럼 쓰는 것을 허용한다. 
- **String은 불변(immutable)** 한다. String을 메소드에 넣으면 처리된 새로운 String이 만들어지고 참조변수가 새 String을 가리킨다. 이러면 이전의 String을 가리키는 참조변수가 없어 그것이 가비지, 더 이상 참조되지 않는 메모리가 된다. 이런 문제 때문에 변하는 문자열을 사용하고 싶을 때에는 **StringBuffer**나 **StringBuilder**를 사용한다. 둘은 비슷한데 대체로 StringBuffer를 많이 쓴다.

- char배열의 전부 혹은 일부분으로 String을 만들 수 있다
	ex.) Stirng str = new String(char\[\] charArr);
		String str2 = new String(charArr, 0 , 5);
		위의 매개변수 : char\[\] , offset, count
- String을 byte의 배열로 변환할 수 있고 반대도 가능하다
	- 파일입출력 하거나 네트워크 통신으로 데이터를 전달할 때에는 byte형으로 변환 후 전달한다
	ex.) String str = new String(byte\[\] bytes);


- **charAt(int index)** : String에서 index번째의 char를 리턴
- **length()** : String의 길이를 int로 반환
- String 안에서 substring이 처음 등장하는 index를 반환하는 **indexof(String substr)**;
	- 해당 substring이 없으면 -1 반환
	- **lastIndexOf(char ch)** : 뒤에서부터 찾는다
- **substring(int beginindex, int endindex)** : 스트링의 beginindex에서 endindex까지 잘라서 잘라낸 string을 리턴한다. 시작 인덱스의 문자는 포함, 끝 인덱스의 문자는 불포함
	- 시작인덱스만 주면 시작인덱스부터 끝까지 잘라서 반환한다
- **replace(CharSequence target, CharSequence replacement)** : target을 replacement로 바꾼 String을 만들어 리턴
- **split(String regex)** : [[표현식]]을 사용해서 분리할 기준을 주면 그 기준에 따라 문자열을 분리해 문자열 배열로 리턴
- **startsWith(String prefix)** : 어떤 문자열이 특정 접두어로 시작하는가를 부울린으로 리턴
- **endsWith(String suffix)** : 어떤 문자열이 특정 접미사로 끝나는가를 부울린으로 리턴
- **toLowerCase()** : 문자열을 소문자로 바꾼 문자열을 리턴
- **toUpperCase()** : 문자열을 대문자로 바꾼 문자열을 리턴
- **equals(String str)** : 문자열이 str과 같은지 판별해서 부울린으로 리턴
- **equalsIgnoreCase(String str)** : 문자열이 str과 같은지를 **대소문자 구분 없이 판별**해서 부울린으로 리턴
- **valueOf(int, double, boolean...)** : static메소드이므로 String.valueOf(...)로 사용. 어떤 자료형이라도 String으로 바꿔서 리턴 (근데 그냥 **+ ""** 해서 편하게 문자열로 만들기도 함, 정석은 아닌데 자주 쓰임)
- **trim()** : 문자열 앞뒤의 공백문자를 제거한 문자열을 리턴
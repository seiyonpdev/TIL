
 - 타입 단언 : 개발자가 해당 타입에 대해 확신이 있을 때 사용하는 타입 지정 방식이다. 타 언어의 타입 캐스팅과 비슷한 개념이며 타입스크립트를 컴파일 할 때 특별히 타입을 체크하지 않고, 데이터의 구조도 신경쓰지 않는다

```typescript
//변수의 타입을 미리 지정한 버전
const name: string = ‘Becca’;
//타입 단언을 사용한 버전
const name = ‘Becca’ as string;

//타입 단언 사용 예시
interface Cat {
	name: string;
	color: string;
}

const kitty: Cat = {}; // X, 오류 발생
kitty.name = ‘kitty’;
kitty.color = ‘black’;

const kitty = {} as Cat; // O, 오류 없음
kitty.name
```
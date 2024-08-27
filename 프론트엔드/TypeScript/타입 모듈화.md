
- 타입 모듈화 : 타입을 한 ts파일에 모아두고 export로 내보내서 필요한 다른 파일에서 import해서 쓰게끔 한다
- 그냥 Java에서 쓰던 것과 다를 바 없다

```typescript

//export 하는 방법 1
export interface Frog {
	size: number;
	color: string
}

//export 하는 방법 2
interface Snail {
	size: number;
	shell: boolean;
}
export { Snail };

//import 하는 방법
//from을 먼저 쓰고 {}를 채우면 자동완성을 쓸 수 있어서 실수를 줄일 수 있다
//대충 위의 두 인터페이스를 types.ts에 작성했다고 가정
import { Snail, Frog } from “types.ts”;

```
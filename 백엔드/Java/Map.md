- key(키)와 value(값) 쌍으로 이뤄진 자료구조
- key는 중복 X
	- 만약 중복된 key의 값을 추가하면(put) 새로운 값으로 갱신하고 이전의 값을 반환한다

1. HashMap
2. LinkedHashMap
3. TreeMap

- **put(K key, V value)** : 원소를 추가하는 메소드, 이전 값(value)이 있었으면 그걸 리턴, 없으면 null을 리턴
- **get(K key)** : value를 가져오는 메소드

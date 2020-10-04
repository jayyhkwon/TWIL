## HashMap

- 해쉬 테이블 구조
  - key와 hash 함수를 이용해 인덱스를 구하여 value를 저장하는 구조

- 데이터 저장을 위해 Node라는 객체 배열을 사용함 (tab = new Node[16])
- tab의 기본 크기는 16, Node 객체는 LinkedList

```
static class Node<K,V> implements Map.Entry<K,V> {
        final int hash;
        final K key;
        V value;
        Node<K,V> next;
}
```



### put 연산 

- key를 이용해  hash 값을 구하고 저장할 버킷(인덱스)을 찾는다.
- 해쉬 충돌이 발생하면 (버킷에 이미 Node가 존재하는 경우) seperate chainning을 이용하여 연결한다.
  - 배열 크기가 커질 수록 open addressing보다 삭제, 검색에 효율적이다

- 하나의 버킷에 8개 이상의 Node가 존재하면 Red-Black Tree 구조로 변환한다 (검색속도가 O(N) -> O(logN) )



참고

<a href="https://d2.naver.com/helloworld/831311">네이버 D2</a> <br>


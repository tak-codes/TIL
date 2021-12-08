# Date Structure
### 자료구조 기초이론 정리
[참고 자료](https://ralp0217.tistory.com/entry/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0Stack-Queue-Deque?category=917872)

1. 스택(Stack)
* 스택은 젠가 모형과 같이 차곡차곡 쌓아 올린 자료구조를 말한다.

* 같은 구조와 크기의 자료를 정해진 방향으로만 쌓을 수 있고, top으로 정한 곳을 통해서만 접근을 할 수 있다.

* 즉 삽입하거나 삭제하거나 등 자료를 처리해야 하는 상황에서 top에 있는 데이터만 접근을 하여 push나 pop을 진행할 수 있다는 것이다. 
* 따라서 후입선출방식인 Last In First Out 구조이다.

    * 활용
        * 웹페이지 뒤로가기
        * 실행취소(undo) : 가장 나중에 실행된 것부터
        * 수식 괄호 검사 etc

    * 장점
        * 구현이 쉽다
        * 원하는 데이터의 접근 속도가 빠르다 -> 즉, 원하는 데이터가 3번째 배열에 위치하면 arr[2]로 한번에 접근 가능하다.

    * 단점
        * 데이터 최대 갯수를 미리 정해야 한다.
        * 데이터의 삽입과 삭제에 있어 매우 비효율적이다.

2. 큐(Queue)- front(head) , rear(tail)
* 정해진 top만 바라보는 stack과 달리 한쪽에서는 삽입(rear), 다른 쪽에서는 삭제(front) 작업이 이뤄어진다.
* 데이터가 들어올 때는 rear로 들어오고, 나갈때는 front로 나간다.
* 접근 방법은 갖아 첫 원소로만 가능하다.
* 가정 먼저 들어온 front원소가 가장 먼저 삭제가 되는 FIFO 선입선출 방식이다.
### 활용 사진
![큐사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FZBrXO%2FbtqXZIVVnPa%2FOvNyNlnYN5BYa7groK8j2K%2Fimg.png)
* 큐과정(위 참조)

    * 장점
        * 데이터가 입력도니 시간 순서대로 처리해야 할 필요가 있는 상황에 유리하다.

    * 단점
        * 크리가 제한적이다.
        * 큐의 앞 부분이 비어도 데이터를 삽입할 수 없다.
        * 큐가 비어있어도 not empty로 판단할 수 있다 (rear가 맨뒤)

3. 덱(Deque) - Double Ended Queue
* 삽입과 삭제가 리스트의 양쪽 끄텡서 모두 발생할 수 있는 자료구조이다.
* Double Ended Queue로 불리기도 하며 Stack과 Queue의 장점만 따서 구성한 것이다.

### 활용 사진
![덱사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcmeI9l%2FbtqXXVBQpiX%2FdaMMS25opJgUQa5Qx3XLH1%2Fimg.png)
* 덱과정(위 참조)

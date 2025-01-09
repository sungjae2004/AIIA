# Universal Approximation Theorem
- MLP는 행렬 곱하고 벡터 더하고 activation, ~이런 함수다
- 이런 형태면 히든 레이어 딱 한 층만 있어도 어떤 연속 함수든 나타 낼 수 있기 때문
- 다시 말해, 어떤 연속 함수든 다 표현할 수 있다.
  - 즉, train loss를 딱 0으로 만들어 버릴 수 있다.
  - cos(x)도 노드만 많으면 얼마든지
- 그럼 왜 DNN을 쓸까?-> 효율적으로 나타내기 위해

# Gradient descent의 문제
- 1. 너무 신중하게 방향 선택
- 2. local minimum

## Gradient descent

## SGD
- 랜덤하게 데이터 하나씩 뽑아서 loss 만듦(랜덤이여서 stochastic)
- 즉, 하나만 보고 빠르게 방향 결정(왜 gradient가 +를 향하지 않을까?-> 전체 데이터인 등고선에서 하나만 보고 빠르게 결정하기 때문)
- 비복원추출 & 다 뽑고 다시 주머니로 넣고 반복
- local minimum으로부터 탈출 할 가능성도 있음
  
## mini-batch SGD
- SGD는 하나씩만 보니까 너무 성급하게 방향 결정
  ->mini-batch는 n개씩 본다
- 무작정 batch-size를 키우진 말고 최대 8k정도 까지만 키우자 왜냐면
  - 1) learning rate도 같이 키우고(Linear scaling Rule: BS 두배하면 LR 두배 해라)
    2) warmup도 해야 그나마 작은 batch-size일 때의 성능을 얻을 수 있기 때문!
       (BS를 키울수록 성능이 안좋아지더라 <-랜덤하게 시작한 위치에서 가까운 local min으로 빠지므로)

## Epoch & Bach size
- -총 Epoch 수 : 전체 데이터를 몇 번 반복해서 볼거냐
- Batch size : 몇 개씩 볼거냐
- Learning rate : 얼만큼 갈거냐
등등을 hyperparameter라고 한다.

## parameter vs hyperparameter
- 파라미터(AI가 스스로 알아내는 변수)
    - weights
    - bias(weight라고 부르기도 함)
    - 등등
-하이퍼 파라미터(내가 정해줘야 하는 변수)
   - Ephoch, batch size
   - lnital weight 값
   - learning rate & learning rate scheduilng
   - model architecture(layer 수, node 수, activation 함수 등)
   - loss 함수 뭐 쓸지
   - 최적화 기법 뭐 쓸지
## Momentum
- 그라디언트를 누적함으로써 관성을 가지게 함

## RMSprop
- Learning rate를 각 파라미터 별로 다르게 준 셈(평준화를 통해 공평하게 탐색)
  경사보고 가파른쪽은 조심하고 완만한 쪽은 과감하게

## Adom
- 방향은 관성을 가지게
- 보폭은 가파른 쪽은 조심조심 완만한 쪽은 과감하개
- 어차피 모든게 element-wise라서 각각에 대한 편미분만 보면 됨

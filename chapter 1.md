#혁펜하임 정리

AI: 인간의 지능을 인공적으로 만든 것
  규칙 기반 알고리즘

ML: 결정 트리, 선형 회귀, 퍼셉트론, SVM

DL: CNN, RNN, GAN, 트랜스포머

CNN(Convolutional Neural Network): 이미지 데이터

3차원 행렬

size = 3x5x5
3 = RGB
5x5 = 배열의 size

RNN(Recurrent Neural Network): 연속적인 데이터

 지도학습: 정답을 알고 있는 채로 학습하는 것 (사람이 입력에 대한 정답을 미리 만들어 놓은 것!)
ex) 회귀, 분류

classification : 분류

classification + Localization : 회귀 + 분류

Object Detection : 더 많은 회귀 + 분류

Instance Segmentation : 픽셀마다 분류

자기지도 학습: 데이터 안에서 self로 만든 정답을 학습하는 방법

pretext tast: 가짜 문제 pre-training: 사전 학습 downstream task: 진짜 문제 transfer learning: 

1. pretext task를 학습해서 pre-training
2. downstream tastk를 풀기 위해 transfer learing 함

## Contrastive learning(대조 학습)
출처가 같은 사진은 비슷한 값이 나오게 하고 다른 사진은 다른 값이 나오는게하는 학습 모델

## 강화 학습

Agent : 강아지(행동의 주체)
Action: 손(강화하고 싶은 것)
Reward: 간식(보상)
Environment: 주인 (설계된 환경)
State: 위치(현재 상태)
Q- function: 이동하는 곳의 기대값(기대값)
Episode: n번째 여친
Q-learnig: 이전 state의 기대값 부여
Expleration: 입실론 그리드 방식(->0.1정도는 일탈을 하는 방식)(새로운 길을 찾게 해줌)
discount factor: (좋고 나쁨을 얘기해줌)



# Training vs Test(vs Validation)
- 처음엔 정답 알려주면서 훈련, 그 다음애 처음보는 데이터를 보여주면서 잘하나 테스트
- 일단, Test 데이터가 학습때 사용하면 안됨
  - AI가 처음 보는 data에 대해서도 잘하는지 봐야하기 때문
- 그런데, train 데이터만으로 학습하자니 몇 epoch에서 학습을 멈취야 할지 모른다
  - train loss를 계속 줄이는게 능사가 아님 그래서 validation(모의 test)
- (data 관점에서 바라보면)
  파라미터 학습을 위한 data vs 최종적으로 학습된 모델 테스트용 data
  (vs 하이퍼파라미터 선택을 위한 data)

# K-Fold Cross Validation
![image](https://github.com/user-attachments/assets/ba57ae90-1e6f-43aa-9397-bd040420a442)

- training data가 적어서 일부를 vaildation으로 쓰게 곤란할 때 (5-fold로 해봄)
- 왜 곤란? 편항된 validation 데이터 => 각기 다른 train, validation 조합의 데이터로 5개 모델을 만들자
- 평균 val loss를 구하자! => 가장 val loss 평균이 작은 hyperparameter set를 고르는 데 사용 가능
- 선택된 set으로 training data 전체에 대해서 새롭게 학습시키거나,
  학습했던 5개 모델의 출력 결과를 하나로 합치기도 함( ex) majority vote)

  # MLP
  ![image](https://github.com/user-attachments/assets/f464e686-a0d0-41a0-b629-52ea09571847)
- 행렬 곱하고 벡터 더하고 activation의 반복이네
- 깊게 깊게 만들면 엄청 복잡한 함수도 나타낼 수 있겠네
  -linear activation만 쓰면 아무리 깊게 만들어도 FC layer 한층 그 이하의 표현역만 가짐
  ->깊어지는 효과를 누리지 못함
  - xW + b 로는 입력과 출력 간의 선형적 관계만을 나타냄
- 따라서, non-linear activation은 중요하다
  (입력, 출력간의 비선형 관계도 나타낼 수 있고 깊을수록 복잡한 함수 표현 가능)
- linear activation를 쓰는 곳?
  - 출력층에 -무한대부터 무한대까지 뽑기 위해
  - 정보 손실을 막기 위해

  # Backpropagation
  - 깊은 곳 weight에 대한 편미분은 cain rule로 구한다
  - 미분이 뒤로 전달되니까 backpropagation
  - path 전부 고려해서 더해줘야 함
  - 액웨액웨액웨 액나
  - foward propagation 한번 해서 값들을 구해 놓고
    backpropagation을 통해 미분 값을 구한다 -> 그리고 SGD 사용하면 끝
  
  

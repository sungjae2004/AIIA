# vanishing gradient
- layer가 많으면 입력 층에 가까울수록 미분이 사라진다
  - back propagation =  액웨액웨액웨..액나
- 기울기 소실이 일어나는 주범은 sigmoid(최대 기울기 = 1/4)
  - 앞에서 줄 잡고 흔들어 봤자 뒤까지 전달이 안된다. (미분을 직관적으로 표현)
- gradient 소멸 -> update X -> 앞단에 이상한 weight -> 깊은게 오히려 독이 됨
- 직관: 앞에서 입력 데이터를 망쳐놓으면 뒤에서 손 쏠 방법이 없다.
- 데이터가 다가가지 못하면 underfiting

# RELU function
![image](https://github.com/user-attachments/assets/2a0b7641-2713-41e5-bf03-9e079cce0d8a)
- 다양한 RELU 변형을 써서 학습을 시킬려고 해봄
  
# Batch Normalization 배치 정규화
- 어디로 재배치 시킬지를 학습, 어디에 얼만큼 세게 뿌릴지를 학습
- 해당 node에 대해 nonliearity를 얼마나 살리면서 vanishing gradient을 얼마나 해결할지 AI가 알아내는것
- 이 행위를 할 layer에다 BN을 추가하는 식으로 적용 (주로 activation 전)
- Training때와 Test때 다르게 동작함
- Batch size에 따라 영향을 받는다는 단점이 있다.
- 이미지 데이터 작업에서 주로 사용

# Layer Nprmalization
- 레이어의 각 노드들에 들어가는 값들에 대한 평균과 분산을 계산한다.
  - Batch size에 대한 영향을 받지 않는다.

# Loss landscape가 꼬불해지는 문제
![image](https://github.com/user-attachments/assets/70f3bff6-88a9-4538-9833-1612027ab017)
-> 층이 너무 깊어도 학습이 안되는 문제가 발생함 
![image](https://github.com/user-attachments/assets/105982ef-35b2-4809-ad25-75aa04cfd5bb)
-> ResNet이 대표적인 해결방안 

- 깊게 만들수록 loss 모양이 이상해짐
- ResNet의 skip-connection이 대표적인 해결 방안 중 하나


# overfitting (과적합)
1. 입력과 출려 간의 관계를 복잡하게 생각했다. -> 경량화를 시켜 과적합을 막는다.
2. 데이터가 적을 때 -> data augumentation를 통해 다시 학습 시킨다
![image](https://github.com/user-attachments/assets/819b860e-92c9-4dfd-8b54-022ce0b7d409)

# Drop out
: 랜덤하게 노드 가려보면서 학습
- 적용시키고 싶은 layer에 dropout 적용, 살릴 확률 p는 hyperparameter
- 네트워크에 통과 시킬 때마다 살릴 노드 다시 고름 (데이터때마다 다시 정함)
test 땐 전원 살림
- 노드가 필요 이상으로 많다면 -> loss를 잘 줄이지만 기계적으로 정답을 맞힐 뿐 -> overfitting -> 몇 명 연차 보내가며 훈련 -> 각 노드가 의미 있는 특징을 뽑음


# overfitting 방지 - Regularization
: loss에 weight의 크기를 더해서 같이 고려하려 함
> - $L$ 대신 $L + \lambda \| \mathbf{w} \|_p^p$를 loss로 사용
p가 1이면 l1-regularization, p가 2면 l2-regularization
- weight를 줄일려고 하는 이유
  - loss 줄이는 데 별 영향 없는 weight는 0으로 => 모델 경량화 (큰 weight는 더 복잡한 모델을 의미)
  - 어느정도 수렴하고 나서도 계속 학습시켜보니 weight가 자꾸 커지더라
- 처음엔 L을 많이 고려하다가 L을 어느정도 줄였으면 L이 도로 너무 커지지 않는 선에서 lP를 줄임
- 직관 : weight 크기도 같이 고려해서 쓸데없이 큰 애들은 망치로 두들겨 줌
- l2의 경우 : 작은 애들은 살살 때리고, 큰 애들은 팍팍 때린다.
- l1의 경우 : 기울기가 일정 => 크건 작건 다 똑같은 힘으로 두드려 -> 몇개 connection을 없애는 효과 ( 중요한 connection만 살리는 느낌)

# MAP(Maximum A Posteriori)의 수학적 해석
- likelihood만 고려하던 것에서 prior distribution까지 고려하는 것
    - l1이면 라틀라시안을 prior distribution
    - l2이면 가우시안을 prior distribution
 

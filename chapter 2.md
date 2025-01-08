# chapter 2 - 인공 신경망과 선형 회귀
## 인공 신경
- 노드와 엣지로 이루어져있다.
- 웨이트(중요도) 곱하고 바이어스(민감도)와 함께 더하고, 엑티베이션(활성화 함수)
- 여러가지 액티베이션이 존재, 강좌에서 설명하고 있는 건 unit step function
- 주어진 입력에 대해 원하는 출력이 나오도록 웨이트, 바이어스를 잘 정해줘야 한다.
- 근데 AI가 적절한 웨이트, 바이어스를 알아낸다

 바이어스 (민감도) : 역치 조정

 웨이트 (중요도) : 10

 ## 인공 신경망
 - 곱하고 더하고 activation, 곱하고 더하고 activation, ,,, 반복
 - weight + bias 세는법
   - 2*3+3

### Input layer, hiden layer, output layer
![image](https://github.com/user-attachments/assets/12791343-1ae5-4fec-ae90-291acbfbb40d)
- FC(fully-connected) layer: 전부 연결된 노드
- 모든 layer가 FC layer인 신경망을 multilayer perceptron(MLP)라고 부른다.

## 선형 회귀
- 입력과 출력 간의 관계를 알아내는 것
  - 처음 보는 입력에 대해서도 적절한 출력을 얻기 위함
- 조회수와 수익의 관계를 ax+b로 놓고 a,b를 알아내서 새로운 값에 대해 추정하는 것
  - 분류와는 아웃풋이 다름

## 최적의 a,b 찾기
- loss를 최소화 하는 a,b가 바로 최적의 a,b
- loss라는 것은 내가 풀고 싶은 문제에 맞게 잘 정의하는 것

## Gradient descent 
- 일단 처음 a,b는 아무렇게나 정한 다음,
- 현재 a,b 위치에서 L을 줄이는 방향으로 나아가자
- 마침 Gradient는 항상 가장 가파른 방향을 향한다.
- Initial weight는 랜덤하게 0 근처로 잡자
![image](https://github.com/user-attachments/assets/7aa5be80-3c83-4f49-914a-1c075d1425df)

  - LeCun
  - Kaiming (ReLU 사용하는 신경망)
  - Xavier(분산이 Kaiming 방식보다 작아 sigmoid/tanh 사용하는 신경망에 적합)

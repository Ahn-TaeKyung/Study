back propagation 과 딥러닝으로 작년에 노벨상 받은 교수님 두분 있다고 했지? 인생이 그래 살면서 조금씩 하면돼 오늘 족므하고 내일 조금하고 그러면 돼 호숫가에 조약돌 한웅큼 던져봐 리플현상이 마아아악 일어나다가 나중가서 머지하잖아 그런거야
앞으로 100년이나 남았어 고민하지마 그냥 하면돼 지금은 물리적 개요가 먼저야 수학적인 공식은 나중이야 그냥 맏아들이고 의문을 가져 모르는건 gpt한테 물어봐 그리고 이해해 수학적인 공식은 나중이야 요즘은 트리구조로 공부해야해 탑다운 방식으로 그래서 gpt를 잘써야해
y(n) = x(n) - ax(n-1)
x(n)은 레퍼런스
ex) 사람들은 다 각자의 키가 있어 근데 바닥은 다를 수 있어 n이 현재위치야 n-1은 뭘까 n이 현재위치가 n-1은 내 옆이야 근데 왜 n-1일까 무슨 의미 일까 내 옆 위치에서 내 위치로 이동했으니까 과거란 뜻으로 - 야 그럼 왜 1일까
아날로그 데이터를 디지털 데이터로 바꾸는 개념중에 샘플링이란게 있어 딱딱딱딱 자르는거야 그럼 어느 단위로 잘라 아주 작은 단위로 짤라야해 전화를 하면 말하는걸 바로바로 전환해서 보내야하니까 아주 많은 데이터를 빠르게 처리해야한단말이야
1초에 8000개의 데이터를 처리해 그럼 -1은 뭐야 1/8000 초 전에 위치라는 거야
x(n-2)는? 2/8000 초 전이라는 거야
이걸 왜 공부 할까? 이걸 모르면 나중에 CNN할때 이 개념을 모르면 그냥 산수만 하는거야 의미를 이해하지 못하게되는거야
내가 수업할때도 간혹가다 점프해서 얘기할거야 왜? 미리미리 생각을 하라고

<img src="https://github.com/user-attachments/assets/7dc61d31-d9ee-4c75-9866-704a1dabf61e" width="500"> 



# 몬테카를로 트리 탐색(MCTS) - 딥한 설명

## 개요
몬테카를로 트리 탐색(MCTS, Monte Carlo Tree Search)은 **확률적 탐색 알고리즘**으로, **게임 트리**에서 최적의 결정을 찾기 위해 사용됩니다. MCTS는 특히 게임 AI에서 사용되며, **전체 게임 트리**를 탐색하기 어려운 경우 유용합니다. 이 알고리즘은 **반복적인 시뮬레이션**을 통해 가장 유망한 결정을 선택하는 방식으로 동작합니다.

## 핵심 용어

### 1. 게임 트리(Game Tree)
- **게임 트리**는 게임의 모든 가능한 상태를 나타내는 트리 구조입니다.
- **루트 노드**는 게임의 시작 상태를 의미하고, 그 하위 **자식 노드**들은 각 플레이어가 선택할 수 있는 가능한 **이동**을 나타냅니다.
  
### 2. 상태 공간(State Space)
- **상태 공간**은 게임의 **모든 가능한 상태**를 의미합니다.
- 예: 체스에서는 **각각의 기물 배치**가 상태가 되고, 바둑에서는 **각각의 돌의 위치**가 상태입니다.

### 3. 상태(State)
- **상태**는 게임에서 **현재 진행 중인 상황**을 나타냅니다. 
- 예: 체스에서는 **각각의 기물 배치**가 상태이고, 바둑에서는 **각각의 돌의 위치**가 상태입니다.

---

## MCTS의 4가지 단계

### 1. 선택 (Selection)
- 트리 구조에서 현재 가장 **탐색이 잘 진행되고 있는 노드**를 선택하는 단계입니다.
- 이때 **UCT (Upper Confidence Bounds for Trees)** 공식을 사용해 노드를 선택합니다.

#### UCT (Upper Confidence Bound for Trees)
- **UCT**는 **탐색 알고리즘**에서 노드를 선택하는 방법 중 하나로, **보상**과 **탐색되지 않은 정도**를 고려한 **평균값**을 계산합니다.
- 공식:
  \[
  UCT = \frac{W_i}{N_i} + C \cdot \sqrt{\frac{\ln N_p}{N_i}}
  \]
  - **W_i**: 해당 노드에서의 승리 횟수
  - **N_i**: 해당 노드를 방문한 횟수
  - **N_p**: 부모 노드를 방문한 횟수
  - **C**: 상수 (일반적으로 **√2** 사용)

### 2. 확장 (Expansion)
- 현재 선택한 노드에서 **새로운 자식 노드**를 추가하는 과정입니다.
- 게임에서 새로운 **상태**를 만들기 위해 가능한 **행동**을 취하고 그에 따른 **새로운 게임 상태**를 확장합니다.

----------

### 🔓 Open / 🔒 Close 노드 (MCTS 관련)

MCTS에서 노드를 관리할 때, "Open"과 "Close" 상태로 나누어 생각할 수 있습니다.

| 상태 | 설명 | 역할 |
|------|------|------|
| 🔓 Open Node | 확장되었지만 아직 시뮬레이션되지 않은 노드 | 후보 노드로 대기 중 |
| 🔒 Close Node | 시뮬레이션 + 백업 완료된 노드 | 더 이상 직접 시뮬레이션되지 않음 (혹은 확률적으로 낮음) |

#### 📌 언제 등장하나?
- **Expansion 단계**에서 새로운 노드를 생성하면 Open Node.
- 시뮬레이션 → Backpropagation을 거치면 해당 노드는 Close 상태가 됨.

-------------

### 3. 시뮬레이션 (Simulation)
- **시뮬레이션**은 선택한 노드에서 **무작위로 게임을 진행**하는 단계입니다.
- 게임을 **끝까지 진행**하여, **게임 종료 상태**(승리, 패배 등)를 구하고, 이를 바탕으로 해당 노드의 **승리 확률**을 계산합니다.

#### 몽타카를로 방법 (Monte Carlo Method)
- **몽타카를로 방법**은 **랜덤 샘플링**을 통해 확률적 문제를 해결하는 기법입니다. 시뮬레이션에서 이 방법을 사용해 게임의 결과를 추정합니다.
- 게임에서 각 수를 두고 나서 **랜덤으로** 게임을 진행하고, 결과를 통해 **예상**을 구하는 방식입니다.

### 4. 백업 (Backpropagation)
- **백업**은 시뮬레이션 결과를 **부모 노드들로 전달**하는 과정입니다.
- 시뮬레이션 결과에 따라, 해당 노드의 **승리 횟수**와 **방문 횟수**를 갱신합니다. 이렇게 트리 상의 각 노드는 **더 정확한 승리 확률**을 가지게 됩니다.

---

## 게임 이론과 MCTS의 관계
- **게임 이론(Game Theory)**은 **최적 전략**을 찾기 위한 **수학적 모델링**을 제공합니다.
- MCTS는 게임 이론에서 유래한 알고리즘으로, **미래의 게임 진행 상황을 예측**하며 **최적의 수**를 찾으려고 합니다.
- **완전 정보 게임**에서는 **완전 탐색**(브루트포스 방법)을 통해 최적의 수를 찾을 수 있지만, **불완전 정보 게임**에서는 MCTS와 같은 **확률적 탐색** 방법을 사용해 해결할 수 있습니다.

---

## MCTS의 장점과 단점

### 장점
1. **부분 탐색**: MCTS는 **전체 게임 트리**를 탐색하지 않고 **유망한 경로**만 탐색하기 때문에 **시간 효율적**입니다.
2. **적응성**: 게임의 특성에 맞게 점차적으로 **탐색 전략을 개선**하기 때문에 매우 유연하게 적용할 수 있습니다.
3. **단계적 학습**: 반복적인 시뮬레이션을 통해, **게임을 계속할수록 더 잘하는 AI**를 만들 수 있습니다.

### 단점
1. **계산 자원 소모**: 시뮬레이션을 많이 해야 하므로 **계산 비용**이 높고, **실시간 게임**에서는 적합하지 않을 수 있습니다.
2. **시뮬레이션 정확도**: 시뮬레이션이 무작위로 진행되기 때문에, **정확도가 떨어질 수** 있습니다.
3. **탐색 범위 제한**: **복잡한 게임**에서는 트리의 크기가 너무 커져서 **전체 상태를 다 탐색**할 수 없을 수 있습니다.

---

## 결론
몬테카를로 트리 탐색(MCTS)은 **게임 AI**에서 매우 중요한 알고리즘으로, **확률적 방법**을 통해 유망한 결정을 선택하는 방식입니다. 게임의 복잡성에 따라 MCTS는 **효율적**이고 **유연한** 탐색을 가능하게 합니다. 하지만 여전히 **시간 소모**와 **정확도**에서 한계가 있을 수 있으므로, 게임에 맞는 탐색 방법을 적절히 선택하는 것이 중요합니다.



# 🤖 선형 회귀에서의 Gradient Descent 학습 원리

---

## 📌 목표: 손실 최소화를 위한 파라미터 업데이트

머신러닝 모델의 핵심은 **손실 함수(Loss Function)** 를 최소화하는 것!  
이를 위해 우리는 **가중치(weight, w)** 와 **편향(bias, b)** 를 반복적으로 업데이트해야 해.  
이 과정에서 **Gradient Descent(경사하강법)** 이 사용된다.

---

## 🔧 모델 수식: 선형 회귀 (Linear Regression)

모델이 예측하는 값은 다음과 같아:

\[
\hat{y}_i = wx + b
\]

- \( w \): 가중치 (weight)
- \( b \): 편향 (bias)
- \( x \): 입력 데이터
- \( y_i \): 실제 정답(label)

---

## 📉 손실 함수 (Loss Function)

우리는 **예측값과 실제값의 차이**를 최소화하고 싶어.  
가장 기본적인 손실 함수는 **Mean Squared Error (MSE)**:

\[
L = \frac{1}{n} \sum_{i=0}^{n-1} (wx + b - y_i)^2
\]

---

## 📐 손실 함수에 대한 기울기 (Gradient)

손실을 줄이기 위해선, 손실 함수를 **w에 대해 미분**해서  
"어느 방향으로 얼마나 파라미터를 바꿀지" 결정해야 해.

\[
\frac{\partial L}{\partial w} = \frac{2}{n} \sum_{i=0}^{n-1} (wx + b - y_i) \cdot x
\]

예를 들어, \( n = 3 \) 이면:

\[
\frac{2}{3} \sum_{i=0}^{2} (wx + b - y_i) \cdot x
\]

✅ 이 수식은 **손실 함수의 기울기(gradient)** 로, 가중치가 얼마나 손실에 영향을 주는지를 나타낸다.

---

## ⚙️ 경사하강법 (Gradient Descent) 업데이트 규칙

기울기를 알았으니, 이제 **파라미터를 업데이트** 해보자!

\[
w(t+1) = w(t) - \eta \cdot \frac{\partial L}{\partial w}
\]

- \( \eta \): 학습률 (learning rate), **하이퍼파라미터**로 조절하는 값
- \( \frac{\partial L}{\partial w} \): 손실 함수의 **기울기**

이때 학습률은 작을수록 천천히 학습하고, 클수록 빠르게 학습하지만  
너무 크면 발산할 수도 있다.

---

## 🔁 요약

| 구성 요소 | 설명 |
|-----------|------|
| \( wx + b \) | 모델의 예측값 |
| \( (wx + b - y_i)^2 \) | 샘플별 제곱 오차 |
| \( \sum (wx + b - y_i)^2 \) | 전체 손실 함수 (MSE) |
| \( \frac{\partial L}{\partial w} \) | 손실 함수의 기울기 |
| \( \eta \) | 학습률 (Learning Rate) |
| \( w(t+1) = w(t) - \eta \cdot \frac{\partial L}{\partial w} \) | 파라미터 업데이트 공식 |

---

## 🧠 직관적으로 이해하자

> 기울기란?  
> 손실 함수 그래프에서 "내리막 방향"이 어디인지 알려주는 값.

> 학습률이란?  
> 내리막을 **얼마나 크게 한 걸음씩 내려갈지**를 정해주는 값.

---

## 🧪 시각화 예시 (선택 사항)

- 손실 함수의 곡선 그래프 위에서,
- 기울기 벡터와 학습률을 곱한 만큼 이동하면서,
- 파라미터가 점점 최적값에 가까워지는 모습

*(이건 나중에 시각화 코드로 따로 만들어볼 수도 있어.)*

---


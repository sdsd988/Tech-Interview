## 자료구조
### 혹시 코딩테스트를 원한다면... [이쪽](https://github.com/VSFe/Algorithm_Study)은 어떠신가요? ~~제껍니다...~~

<details>
  <summary><h3>1. 시간복잡도와 공간복잡도에 대해 설명해 주세요.</h3></summary>

### 시간 복잡도 (Time Complexity)

시간 복잡도는 알고리즘이 문제를 해결하는 데 걸리는 시간과 입력 크기의 관계를 나타내는 지표입니다. 일반적으로 실제 실행 시간을 측정하는 대신, 연산의 수행 횟수를 기준으로 분석합니다. 입력 크기가 증가함에 따라 알고리즘의 실행 시간이 얼마나 증가하는지를 파악하는 데 유용합니다.

### 공간 복잡도 (Space Complexity)
공간 복잡도는 알고리즘이 문제를 해결하는 데 사용하는 메모리 공간과 입력 크기의 관계를 나타내는 지표입니다. 여기에는 입력 데이터를 저장하는 공간뿐만 아니라 알고리즘 실행 중에 추가적으로 사용하는 공간 (변수, 자료 구조 등)이 포함됩니다.

<ul>

<li> Big-O, Big-Theta, Big-Omega 에 대해 설명해 주세요.</li>

점근적 표기법 (Asymptotic Notation): 시간 복잡도를 표현할 때는 주로 점근적 표기법을 사용합니다. 이는 입력 크기가 충분히 커질 때 알고리즘의 실행 시간 증가율을 간결하게 나타내기 위함입니다. 주요 점근적 표기법은 다음과 같습니다.

- 빅오 표기법 (Big-O Notation, O(n)): 최악의 경우의 시간 복잡도를 나타냅니다. 알고리즘 실행 시간이 상한으로 이 정도 성능은 보장한다는 의미입니다.
- 빅오메가 표기법 (Big-Omega Notation, Ω(n)): 최선의 경우의 시간 복잡도를 나타냅니다. 알고리즘 실행 시간이 하한으로 최소 이 정도 성능은 보장한다는 의미입니다.
- 빅세타 표기법 (Big-Theta Notation, Θ(n)): 평균적인 경우의 시간 복잡도를 나타냅니다. 최악의 경우와 최선의 경우의 시간 복잡도가 비슷할 때 사용됩니다. 
<li> 다른 것을 사용하지 않고, Big-O를 사용하는 이유가 있을까요?</li>

실질적인 성능 예측: 최악의 경우를 분석하여 실제 시스템 운영 환경에서의 성능 저하 가능성을 예측하고 대비할 수 있습니다.
확장성 평가: 입력 크기가 증가함에 따른 성능 변화 추세를 파악하여 알고리즘의 확장성을 평가할 수 있습니다.
간결하고 핵심적인 정보 제공: 상수항과 낮은 차수항을 무시하여 알고리즘의 핵심적인 성능 특성을 명확하게 보여줍니다.
표준화된 소통 방식: 컴퓨터 과학 분야에서 알고리즘 효율성을 논의하는 공통 언어 역할을 합니다.
<li> O(1)은 O(N^2) 보다 무조건적으로 빠른가요?</li>
대부분의 실질적인 상황에서, 입력 크기가 어느 정도 이상이라면 O(1) 알고리즘은 O(N²) 알고리즘보다 훨씬 빠릅니다.
"무조건적으로" 빠르다고 단정할 수는 없지만, 이는 매우 예외적인 경우이며, 입력 크기가 커질수록 O(1)의 우월성은 명확해집니다.
알고리즘의 효율성을 비교할 때는 **점근적 복잡도(Big-O)**를 기준으로 하는 것이 일반적이며, 이는 입력 크기가 커질 때의 성능 추세를 잘 나타냅니다.
</ul>
</details>

<details>
  <summary><h3>2. 링크드 리스트에 대해 설명해 주세요.</h3></summary>
  링크드 리스트는 데이터를 **노드(Node)**라는 단위로 저장하고, 각 노드가 **다음 노드를 가리키는 포인터(또는 참조)**를 통해 서로 연결되어 있는 선형 자료 구조입니다. 배열과는 달리 메모리 상에 연속적으로 저장되지 않아도 되며, 데이터의 삽입과 삭제가 효율적이라는 장점을 가집니다.
<ul>
<li> 일반 배열과, 링크드 리스트를 비교해 주세요.</li>
  | 특징             | 노드 (Node)                                  | 배열 (Array)                                     |
|-----------------|----------------------------------------------|-------------------------------------------------|
| **구조** | 데이터 + 다음 (or 이전) 노드 포인터          | 연속된 메모리 공간에 동일 타입 데이터 순차 저장 |
| **메모리 할당** | 동적 할당 및 해제 가능                        | 생성 시 고정 크기 할당 (동적 배열은 조절 가능)    |
| **접근 방식** | 순차 접근 (O(n))                             | 직접 접근 (인덱스 사용, O(1))                   |
| **삽입/삭제** | 효율적 (위치 알면 O(1))                       | 비효율적 (데이터 이동, O(n))                    |
| **크기 변경** | 유연                                         | 초기 크기 제한, 변경 시 복사 필요 (동적 배열 amortized O(1)) |
| **메모리 연속성** | 불연속적일 수 있음                           | 연속적                                          |
| **추가 공간** | 포인터 저장 공간 필요                         | 추가 공간 거의 불필요                             |
| **탐색** | O(n)                                         | 인덱스 알면 O(1), 모르면 O(n)                    |
| **주요 활용** | 연결 리스트, 트리, 그래프 등 동적 구조 기본 단위 | 순차 데이터 저장, 빠른 임의 접근                 |
<li> 링크드 리스트를 사용해서 구현할 수 있는 다른 자료구조에 대해 설명해 주세요.</li>
  - 스택, 큐, 덱, 해시테이블이 있습니다.
</ul>
</details>

<details>
  <summary><h3>3. 스택과 큐에 대해서 설명해 주세요.</h3></summary>
<ul>
<li> 스택 2개로 큐를, 큐 2개로 스택을 만드는 방법과, 그 시간복잡도에 대해 설명해 주세요.</li>
<li> 시간복잡도를 유지하면서, 배열로 스택과 큐를 구현할 수 있을까요?</li>
<li> Prefix, Infix, Postfix 에 대해 설명하고, 이를 스택을 활용해서 계산/하는 방법에 대해 설명해 주세요.</li>
<li> Deque는 어떻게 구현할 수 있을까요? </li>
<li> (C++ 한정) Deque의 Random Access 시간복잡도는 O(1) 입니다. 이게 어떻게 가능한걸까요? </li>
</ul>
</details>

<details>
  <summary><h3>4. 해시 자료구조에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 값이 주어졌을 때, 어떻게 하면 충돌이 최대한 적은 해시 함수를 설계할 수 있을까요?</li>
<li> 해시값이 충돌했을 때, 어떤 방식으로 처리할 수 있을까요?</li>
<li> 본인이 사용하는 언어에서는, 어떤 방식으로 해시 충돌을 처리하나요?</li>
<li> Double Hashing 의 장점과 단점에 대해서 설명하고, 단점을 어떻게 해결할 수 있을지 설명해 주세요.</li>
<li> Load Factor에 대해 설명해 주세요. 본인이 사용하는 언어에서의 해시 자료구조는 Load Factor에 관련한 정책이 어떻게 구성되어 있나요?</li>
<li> 다른 자료구조와 비교하여, 해시 테이블은 멀티스레드 환경에서 심각한 수준의 Race Condition 문제에 빠질 위험이 있습니다. 성능 감소를 최소화 한 채로 해당 문제를 해결할 수 있는 방법을 설계해 보세요.</li>
</ul>
</details>

 <details>
  <summary><h3>5. 트리와 이진트리, 이진탐색트리에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 그래프와 트리의 차이가 무엇인가요?</li>
<li> 이진탐색트리에서 중위 탐색을 하게 되면, 그 결과는 어떤 의미를 가지나요?</li>
<li> 이진탐색트리의 주요 연산에 대한 시간복잡도를 설명하고, 왜 그런 시간복잡도가 도출되는지 설명해 주세요.</li>
<li> 이진탐색트리의 한계점에 대해 설명해주세요.</li>
<li> 이진탐색트리의 값 삽입, 삭제 방법에 대해 설명하고, 어떤식으로 값을 삽입하면 편향이 발생할까요?</li>
<li> 이진탐색트리와 동일한 로직을 사용하면, 삼진탐색트리도 정의할 수 있을까요? 안 된다면, 그 이유에 대해 설명해 주세요.</li>
</ul>
</details>   

 <details>
  <summary><h3>6. 힙에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 힙을 배열로 구현한다고 가정하면, 어떻게 값을 저장할 수 있을까요?</li>
<li> 힙의 삽입, 삭제 방식에 대해 설명하고, 왜 이진탐색트리와 달리 편향이 발생하지 않는지 설명해 주세요.</li>
<li> 힙 정렬의 시간복잡도는 어떻게 되나요? Stable 한가요?</li>
</ul>
</details>   

 <details>
  <summary><h3>7. BBST (Balanced Binary Search Tree) 와, 그 종류에 대해 설명해 주세요.</h3></summary>
<ul>
<li> Red Black Tree는 어떻게 균형을 유지할 수 있을까요?</li>
<li> Red Black Tree의 주요 성질 4가지에 대해 설명해 주세요.</li>
<li> 2-3-4 Tree, AVL Tree 등의 다른 BBST 가 있음에도, 왜 Red Black Tree가 많이 사용될까요?</li>
</ul>
</details>   

 <details>
  <summary><h3>8. 정렬 알고리즘에 대해 설명해 주세요.</h3></summary>
<ul>
<li> Quick Sort와 Merge Sort를 비교해 주세요.</li>
<li> Quick Sort에서 O(N^2)이 걸리는 예시를 들고, 이를 개선할 수 있는 방법에 대해 설명해 주세요.</li>
<li> Stable Sort가 무엇이고, 어떤 정렬 알고리즘이 Stable 한지 설명해 주세요.</li>
<li> Merge Sort를 재귀를 사용하지 않고 구현할 수 있을까요?</li>
<li> Radix Sort에 대해 설명해 주세요.</li>
<li> Bubble, Selection, Insertion Sort의 속도를 비교해 주세요. </li>
<li> 값이 <strong>거의</strong> 정렬되어 있거나, 아예 정렬되어 있다면, 위 세 알고리즘의 성능 비교 결과는 달라질까요? </li>
<li> 본인이 사용하고 있는 언어에선, 어떤 정렬 알고리즘을 사용하여 정렬 함수를 제공하고 있을까요? </li>
<li> 정렬해야 하는 데이터는 50G 인데, 메모리가 4G라면, 어떤 방식으로 정렬을 진행할 수 있을까요? </li>
</ul>
</details>   

 <details>
  <summary><h3>9. 그래프 자료구조에 대해 설명하고, 이를 구현할 수 있는 두 방법에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 각 방법에 대해, "두 정점이 연결되었는지" 확인하는 시간복잡도와 "한 정점에 연결된 모든 정점을 찾는" 시간복잡도, 그리고 공간복잡도를 비교해 주세요.</li>
<li> 정점의 개수가 N개, 간선의 개수가 N^3 개라면, 어떤 방식으로 구현하는 것이 효율적일까요? </li>
<li> 사이클이 없는 그래프는 모두 트리인가요? 그렇지 않다면, 예시를 들어주세요.</li>
</ul>
</details>   

 <details>
  <summary><h3>10. 그래프에서, 최단거리를 구하는 방법에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 트리에서는 어떤 방식으로 최단거리를 구할 수 있을까요? (위 방법을 사용하지 않고) </li>
<li> 다익스트라 알고리즘에서, 힙을 사용하지 않고 구현한다면 시간복잡도가 어떻게 변화할까요? </li>
<li> 정점의 개수가 N개, 간선의 개수가 N^3 개라면, 어떤 알고리즘이 효율적일까요?</li>
<li> A* 알고리즘에 대해 설명해 주세요. 이 알고리즘은 다익스트라와 비교해서 어떤 성능을 낼까요? </li>
<li> 음수 간선이 있을 때와, 음수 사이클이 있을 때 각각 어떤 최단거리 알고리즘을 사용해야 하는지 설명해 주세요. </li>
</ul>
</details>   

 <details>
  <summary><h3>11. 재귀함수에 대해 설명해 주세요.</h3></summary>
- 재귀 함수는 자기 자신을 호출하는 함수입니다. 주어진 문제를 더 작은 문제로 나누어 해결할 수 있을 때 유용하게 사용.

기본 구조

 ``` java
public int recursiveFunction(int n) {
    if (n <= 0) return; // 종료 조건 (Base Case)
    recursiveFunction(n - 1); // 자기 자신을 호출 (Recursive Case)
}

public int factorial(int n) {
    if (n == 1) return 1; // Base Case
    return n * factorial(n - 1); // Recursive Case
}

public int fibonacci(int n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

```

Base Case (종료 조건): 재귀 호출을 멈출 조건을 지정. 없으면 무한 루프 발생.

Recursive Case (재귀 조건): 문제를 더 작은 문제로 나누어 자기 자신을 호출.

항목 | 재귀 | 반복
코드 간결성 | 간결함 |  복잡할 수 있음
성능 |  느릴 수 있음 | 빠름
메모리 사용 |  스택 사용 |  효율적
이해도 |  수학적 사고 적합 |  직관적
<ul>
<li> 재귀 함수의 동작 과정을 Call Stack을 활용해서 설명해 주세요.</li>

# 재귀 함수와 Call Stack

## Call Stack이란?
- 함수 호출 시 **함수의 실행 정보를 저장하는 메모리 영역**
- 재귀 호출은 **자기 자신을 계속 호출하므로 Call Stack에 쌓임**
- 호출이 끝나면 **마지막에 호출된 함수부터 차례로 종료**

---

## 예제: 팩토리얼 계산


```java
public int factorial(int n) {
    if (n == 1) return 1;
    return n * factorial(n - 1);
}
```

### factorial(4)를 호출하면?

1. 호출 단계

factorial(4) 호출 → factorial(3) 호출 → factorial(2) 호출 → factorial(1) 호출

**Call Stack 상태 (위 → 아래)**

| factorial(1) |
| factorial(2) |
| factorial(3) |
| factorial(4) | ← 가장 먼저 호출된 함수 (가장 아래에 위치)


**2. 반환 단계 (Call Stack에서 빠짐)**
factorial(1) → 1 반환
factorial(2) → 2 * 1 = 2 반환
factorial(3) → 3 * 2 = 6 반환
factorial(4) → 4 * 6 = 24 반환

호출 순서:
```
factorial(4)
 └─ factorial(3)
      └─ factorial(2)
           └─ factorial(1)
                └─ return 1
```
반환 순서:

factorial(1) → 1
factorial(2) → 2 * 1 = 2
factorial(3) → 3 * 2 = 6
factorial(4) → 4 * 6 = 24

Call Stack 주의 사항
재귀 호출이 너무 깊어지면 StackOverflowError 발생

Java에서는 일반적으로 1,000~2,000 레벨 이상의 깊은 재귀 호출 시 오류 발생

반복문 사용이 가능한 경우에는 재귀 대신 반복문 사용을 고려

최적화 기법: 꼬리 재귀(Tail Recursion) 또는 메모이제이션(Memoization)


<li> 언어의 스펙에 따라, 재귀함수의 최적화를 진행해주는 경우가 있습니다. 어떤 경우에 재귀함수의 최적화가 가능하며, 이를 어떻게 최적화 할 수 있을지 설명해 주세요.</li>

# Java에서의 재귀 함수 최적화

##  재귀 함수 최적화란?

재귀 호출을 사용할 때, **호출 스택을 줄이거나 제거**하여 **메모리 낭비를 막고 성능을 개선**하는 기법입니다.

---

##  꼬리 재귀 (Tail Recursion)

###  정의

> **재귀 호출이 함수의 마지막 동작인 경우**, 이를 **꼬리 재귀(Tail Recursion)** 라고 합니다.

즉, **재귀 호출 뒤에 더 이상 실행할 코드가 없을 때** 발생합니다.

### 일반 재귀

```java
public int factorial(int n) {
    if (n == 1) return 1;
    return n * factorial(n - 1); // 재귀 호출 후 곱셈이 있음 → 꼬리 재귀 아님
}
```

### 꼬리 재귀

```java
public int factorialTail(int n, int acc) {
    if (n == 1) return acc;
    return factorialTail(n - 1, n * acc); // 마지막에 재귀 호출만 있음 → 꼬리 재귀
}

```
 
 꼬리 재귀 최적화 (Tail Call Optimization, TCO)
- 일반적으로 꼬리 재귀는 컴파일러가 최적화하여 스택 프레임을 새로 쌓지 않고, 현재 스택 프레임을 재사용할 수 있습니다.

하지만, Java에서는?

Java는 꼬리 재귀 최적화를 지원하지 않습니다.

JVM(Java Virtual Machine) 사양에서는 명시적으로 꼬리 재귀 최적화가 금지되어 있음

이유: 디버깅, 스택 트레이스 유지 등 JVM의 설계 철학 때문

항목 | 설명
꼬리 재귀 | 재귀 호출이 함수의 마지막 동작일 때
Java의 TCO 지원 | ❌ 미지원
최적화 방법 | 반복문으로 변환하거나 직접 스택 사용
추천 방식 | 반복문 (가독성, 성능 모두 우수)


** Kotlin 에서의 꼬리 재귀 최적화 **

```kotlin
tailrec fun factorial(n: Int, acc: Int = 1): Int {
    return if (n == 1) acc else factorial(n - 1, acc * n)
}

```

factorial(5)
→ 컴파일 타임에 루프로 변환
→ Stack 사용 없이 반복문처럼 동작

</ul>
</details>   

 <details>
  <summary><h3>12. MST가 무엇이고, 어떻게 구할 수 있을지 설명해 주세요.</h3></summary>
<ul>
<li> Kruskal 알고리즘에서 사용하는 Union-Find 자료구조에 대해 설명해 주세요.</li>
<li> Kruskal 과 Prim 중, 어떤 것이 더 빠를까요?</li>
<li> Kruskal 과 Prim 알고리즘을 통해 얻어진 결과물은 무조건 트리인가요? 만약 그렇다면 증명해 주세요. 그렇지 않다면, 반례를 설명해 주세요. </li>
</ul>
</details>   

 <details>
  <summary><h3>13. Thread Safe 한 자료구조가 있을까요? 없다면, 어떻게 Thread Safe 하게 구성할 수 있을까요?</h3></summary>

   # 🔒 Thread Safe 한 자료구조란?

## 📌 정의

> 여러 스레드가 동시에 접근하더라도 **데이터의 정합성과 일관성을 보장**하는 자료구조

---

## Java에서 제공하는 Thread Safe 자료구조

### 🔹 java.util.concurrent 패키지 

| 자료구조                        | 설명 |
|-------------------------------|------|
| `ConcurrentHashMap`           | 병렬 처리를 지원하는 HashMap |
| `CopyOnWriteArrayList`        | 읽기 위주 작업에 최적화된 List |
| `ConcurrentLinkedQueue`       | 비동기 Queue (Lock-Free) |
| `ConcurrentSkipListMap`       | 정렬된 Map, ConcurrentHashMap의 TreeMap 버전 |
| `BlockingQueue` (예: `ArrayBlockingQueue`) | 생산자-소비자 패턴 구현에 적합 |

### 🔹 동기화 래퍼 (기존 컬렉션을 Thread Safe하게 변환)

```java
List<String> syncList = Collections.synchronizedList(new ArrayList<>());
Map<String, String> syncMap = Collections.synchronizedMap(new HashMap<>());
```
<ul>
<li> 배열의 길이를 알고 있다면, 조금 더 빠른 Thread Safe 한 연산을 만들 순 없을까요?</li>
  # ⚡ 배열 길이를 알고 있는 경우, 더 빠른 Thread Safe 연산 만들기

## 📌 기본 아이디어

> 배열의 크기가 고정되어 있다면, **락을 분할하거나 락 없이 병렬 처리**하는 전략을 사용할 수 있습니다.

---

## ✅ 전략 1: 요소 단위 락 (Fine-Grained Locking)

### 개념

- 배열의 각 요소마다 **별도의 락 객체를 두어**, 병렬 처리 시 **락 경합 최소화**

### 예시

```java
public class AtomicArray {
    private final int[] data;
    private final Object[] locks;

    public AtomicArray(int size) {
        data = new int[size];
        locks = new Object[size];
        for (int i = 0; i < size; i++) {
            locks[i] = new Object();
        }
    }

    public void add(int index, int value) {
        synchronized (locks[index]) {
            data[index] += value;
        }
    }

    public int get(int index) {
        synchronized (locks[index]) {
            return data[index];
        }
    }
}
```
<li> 사용하고 있는 언어의 자료구조는 Thread Safe 한가요? 그렇지 않다면, Thread Safe 한 Wrapped Data Structure 를 제공하고 있나요?</li>

# ❓ Java의 자료구조는 Thread Safe 한가요?

## 📌 기본적으로 Java의 `java.util` 컬렉션은 **Thread Safe 하지 않습니다.**

| 자료구조      | Thread Safe 여부 | 비고 |
|---------------|------------------|------|
| `ArrayList`   | ❌               | 멀티스레드에서 사용하면 동기화 필요 |
| `HashMap`     | ❌               | 멀티스레드 환경에서 ConcurrentModificationException 발생 가능 |
| `HashSet`     | ❌               | 내부적으로 HashMap 사용 |
| `LinkedList`  | ❌               | 동기화되지 않음 |

---

## ✅ Thread Safe 한 Wrapped 자료구조 제공

Java는 기본 컬렉션을 Thread Safe 하게 **감싸는 래퍼 클래스**를 제공합니다.

### 📦 `Collections.synchronizedXXX()`

```java
List<String> syncList = Collections.synchronizedList(new ArrayList<>());
Map<String, String> syncMap = Collections.synchronizedMap(new HashMap<>());

</ul>
</details>  

 <details>
  <summary><h3>14. 문자열을 저장하고, 처리하는 주요 자료구조 및 알고리즘 (Trie, KMP, Rabin Karp 등) 에 대해 설명해 주세요.</h3></summary>
<ul>
</ul>
</details>  

 <details>
  <summary><h3>15. 이진탐색이 무엇인지 설명하고, 시간복잡도를 증명해 보세요.</h3></summary>
<ul>
<li> Lower Bound, Upper Bound 는 무엇이고, 이를 어떻게 구현할 수 있을까요?</li>
<li> 이진탐색의 논리를 적용하여 삼진탐색을 작성한다고 가정한다면, 시간복잡도는 어떻게 변화할까요? (실제 존재하는 삼진탐색 알고리즘은 무시하세요!)</li>
<li> 기존 이진탐색 로직에서 부등호의 범위가 바뀐다면, (ex. <= 라면 <로, <이라면 <= 로) 결과가 달라질까요?</li>
</ul>
</details>  

 <details>
  <summary><h3>16. 그리디 알고리즘과 동적 계획법을 비교해 주세요.</h3></summary>
<ul>
<li> 그렇다면, 어떤 경우에 각각의 기법을 사용할 수 있을까요?</li>
<li> 그렇다면, 동적 계획법으로 풀 수 있는 모든 문제는 재귀로 변환하여 풀 수 있나요?</li>
</ul>
</details>  

# 델리게이트


**델리게이트**(메서드 대리자)를 다른 메서드에 매개변수로 전달하여, <br> 델리게이트를 매개변수로 받는 메서드에서 델리게이트를 실행한다.<br> 이렇게 델리게이트로 전달되는 메서드를 콜백 메서드라고 한다.<br> 어떤 메서드를 델리게이트 객체로 전달하느냐에 따라 메서드의 동작을 다르게 할 수 있다.<br><br>*델리게이트를 다른 메서드에 넘겨주려면 델리게이트와 형태가 같은 메서드를 만들어야한다.*


### 예시
1. **델리게이트 정의 방법**
```
// 델리게이트 (대리자) 정의
// 이 메서드는 항상 정수형 2개 매개변수를 받게 됨.
delegate int Dele(int a, int b);

// 델리게이트로 다른 메서드에 넘겨줄 메서드
static int Plus(int a, int b)
{
    return a + b;
}
```
2. **델리게이트 사용 방법**
```
static void Main(string[] args)
{
    // 델리게이트를 매개변수로 하는 메서드를 호출
    Calc(1, 2, Plus);
    Calc(4, 3, Minus);
    Calc(5, 6, Multy);

    Console.ReadLine();
}
static void Calc(int a, int b, Dele dele)
{
    Console.WriteLine(dele(a, b));
}
```
<br>
WindowForm project에서도 컨트롤에 이벤트를 추가할 때 델리게이트를 사용한다.<br>이벤트가 발생시 실행되도록 설정하는 메서드는 델리게이트 객체를 통해 전달되는 콜백 메서드이다.


상속    
부모 클래스가 가진 특성(변수)과 행동(메서드)을 자식 클래스가 물려받는 것을 의미한다.  

class Parent {
    void sayHello()() {
        System.out.println("hello")
    }
}
class Child extends Parent { // Child 클래스는 sayHello 메서드를 상속받음
}

오버라이딩(Overliding)   
상속받은 메서드를 자식 클래스에서 재정의하는 것   
```bash
class Child extends Parents {
    void sayHello() {
        System.out.println("hello child");
    }
}
```
Child 클래스는 Parents의 sayHello메서드를 오버라이딩해서 hello child라는 새매시지를 출력하도록 바뀜  

오버로딩(Overloading)   
같은 이름의 메서드를 여러 개 가지되, 매개변수의 유형이나 개수를 다르게 하는 것을 말한다. 이렇게 하면 같은 일을 하는 메서드라도 조금씩 다르게 사용할 수 있다.
```bash
class MathOperations {
    int sum(int a, int b) {
        return a + b;
    }
    int sum(int a, int b, int c) {
        return a + b + c;
    }
}
// 2개는 sum이라는 메서드로 이름이 동일하다, 하지만 매개변수가 다르기 떄문에 서로 다른 버전으로 존재가 가능하다.
```

23년도 3회 기출
```bash
public class main {
    public static void main(String[] args) {
        A b = new B(); // 변수 b의 자료형은 A 여기서 실제로 만들어진 객체는 B --> 변수 타입은 A / 실제 객체는 B : 다형성
        // 여기서 메서드 호출시 중요 규칙은 오버라이딩된 메서드는 변수 타입이 아니라 실제 객체 타입을 기준으로 실행된다.
        // 즉, b의 타입은 A지만, 실제 객체는 B이므로 오버라이딩된 메서드를 호출하면 B의 메서드가 실행된다.
        b.paint();
        b.draw();
    }
}

class A {
    public void paint() {
        System.out.print("A");
        draw();
    }

    public void draw() {
        System.out.print("B");
        draw();
    }
}

class B extends A { // B 클래스가 A 클래스를 상속한다. -> A는 부모클래스 / B는 자식클래스
    public void paint() {
        super.draw(); // super은 부모 클래스 -> 부모 클래스는 A 즉, A의 draw()를 호출
        System.out.print("C");
        this.draw(); 
    }

    public void draw() {
        System.out.print("D");
    }
}
정답
BDCDD
```
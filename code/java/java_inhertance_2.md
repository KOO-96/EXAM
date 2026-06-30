this 키워드   
현재 객체, 즉 메서드나 생성자를 호출하는 객체를 가리키는데 사용한다.   
같은 이름의 클래스 변수와 메서드 매개변수가 충돌할 때 이를 구별하기 위해 사용

```bash
class Flower {
    private String name;
    
    Flower(String name) {
        this.name = name; //'this.name'은 클래스 변수, 'name'은 생성자의 매개변수를 가리킨다.
    }
    void printName() {
        System.out.println(this.name); // 'this'로 클래스 변수 'name'에 접근한다.
    }
}
```
여기서 this.name은 클래스의 name 변수를 참조하고 단순히 name은 생성자로 전달된 매개변수를 참조한다.

super 키워드  
부모 클래스를 가리키는데 사용되며, 부모 클래스의 변수나 메서드, 생성자에 접근할 때 사용한다.  
자식 클래스에서 오버라이드한 메서드가 부모 클래스의 메서드를 호출하고 싶을 때, super을 사용한다.

```bash
class Plant {
    String type = "Plant";
    
    void printType() {
        System.out.println(this.type); // 'this'로 자신의 types 변수에 접근한다.
    }
}

class Flower extends Plant {
    String type = "Flower";
    
    void printType() {
        super.printType(); // 'super'로 부모 클래스의 printType 메서드를 호출한다.
        System.out.println(this.type); // 'this'로 자신의 type변수에 접근한다.
    }
}
```
Flower 클래스에서 super.printType()은 Plant클래스의 printType 메서드를 호출하고 this.type은 Flower 클래스 자신의 type 변수를 참조한다.


20년 2회 기출
```bash
Class A {
    private A(int a) {
        this.a = a;
        }
    public void display() {
        System.out.println("a=" + a);
    }
}

class B extends A {
    public B(int a) {
        super(a);
        super.display();
    }
}

public class  Main {
    public static void main (String[] args) {
        B obj = new B(10);
    }
}
정답
a=10
```

21년 2회 기출
```bash
public class Ovr1 {
    public static void main(String[] args) {
        Ovr1 a1 = new Ovr1();
        Ovr2 a2 = new Ovr2();
        System.out.print;n(a1.sum(3,2) + a2.sum(3,2));
    }
    int sun(int x, int y) {
        return x+y;
    }
}

class Ovr2 extends Ovr1 {
    int sun(int x, int y)} {
        return x - y + super.sun(x,y);
    }
}
정답
11
```

23년 1회 기출
```bash
class Parent {
    int x = 1000;
    
    Parent() {
        this(3000);
    }
    
    Parent(int x) {
        this.x = x;
    }
}

class Child extends Parent {
    int x = 4000;
    
    Child() {
        this(5000);
    }
    
    Child(int x) {
        this.x = x;
    }

    int getX() {
        return x;
    }
}

public class Main {
    public static void main(String[] args) {
        Child obk = new Child();
        System.out.println(obk.getX());
    }
}
정답
5000
```

23년 3회 실기
```bash
class Parent {
    int compute(int num) {
        if(num <= 1)
            return num;
        return compute(num-1) + compute(num-2);
    }
}

class Child extends Parent {
    int compute(int num) {
        if(num <= 1)
            return num;
        return compute(num-1) + compute(num-3);
    }
}

public class main {
    public static void main(String args[]) {
        Parent obj = new Child(); // 제일 중요한 부분 --> 참조 변수가 Parent 근데 실제 객체는 Child
        System.out.print(obj.compute(7)); // 결국 Child.compute(7)
    }
}
// Child의 compute만 사용함
compute(-1) = -1
compute(0) = 0
compute(1) = 1
compute(2) = compute(1) + compute(-1) = 1 - 1 = 0
...
compute(7) = compute(6) + compute(5) = 1 + 1 = 2

정답
2
```

20년 4회 기출
```bash
class Parent {
    public int compute(int num) {
        if(num <= 1) return num;
        return compute(num-1) + compute(num-2);
    }
}

class Child extends Parent {
    public int compute(int num) {
        if(num <= 1) return num;
        return compute(num-1) + compute(num-3);
    }
}

class Main {
    public static void main(String[] args) {
        Parent obj = new Child();
        System.out.print(obj.compute(4));
    }
}
// 23년도 3회 실기와 숫자만 다르다.
정답
1
```

20년도 2회 기출
```bash
// 밑줄에 들어갈 키워드
class Parent {
    public void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    public void show() {
        System.out.println("Child");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent pa = ____ Child(); // pa라는 참조 변수 실제 객체는 없는 상태에서 new Child()라는 실제 객체를 만든다.
                                // new는 객체를 생성하라는 뜻 즉, Child()r가 pa를 가리킨다.
                                // 변수 타입은 Parent 실제 객체(인스턴스)는 Child
        pa.show();
    }
}
정답
new
```

24년 1회 기출
```bash
// 실행 순서 적기
// {5} -> {} -> {} -> {} -> {}
class Parent {
    int x, y;

    Parent(int x, int y) { (1)
        this.x = x;
        this.y = y;
    }

    int getT() { (2)
        return x * y;
    }
}

class Child extends Parent {
    int x;

    Child(int x) { (3)
        super(x + 1, x);
        this.x = x;
    }

    int getT(int n) { (4)
        return super.getT() + n;
    }
}

class Main {
    public static void main(String[] args) { (5)
        Parent parent = new Child(3); (6)
        System.out.println(parent.getT()); (7)
    }
}
정답
6 -> 3 -> 1 -> 7 -> 2
```

24년 1회 기출
```bash
class classOne {
    int a, b;

    public classOne(int a, int b) {
        this.a = a;
        this.b = b;
    }

    public void print() {
        System.out.println(a + b);
    }
}

class classTwo extends classOne {
    int po = 3;

    public classTwo(int i) {
        super(i, i + 1);
    }

    public void print() {
        System.out.println(po * po);
    }
}

public class Main {
    public static void main(String[] args) {
        classOne one = new classTwo(10);
        one.print();
    }
}
정답
9
```

24년 3회 기출
```bash
public class Main {
    public static void main(String[] args) {
        Base a = new Derivate();
        Derivate b = new Derivate();

        System.out.print(a.getX() + a.x + b.getX() + b.x);
    }
}
// a.getX() --> Derivate
// a.x --> 3 그 이유는 메서드는 오버라이딩 하지만 변수는 오버라이딩되지 않는다
class Base {
    int x = 3;

    int getX() {
        return x * 2;
    }
}

class Derivate extends Base {
    int x = 7;

    int getX() {
        return x * 3;
    }
}
정답
52
```

25년 1회 기출
```bash
public class Main {
    public static void main(String[] args) {
        new Child(); // 자식 객체를 만들때, 부모 객체부터 만들어진다.
                    // show는 오버라이딩된 자식 메서드가 호출된다.
        System.out.println(Parent.total);
    }
}

class Parent {
    static int total = 0;
    int v = 1;

    public Parent() {
        total += (++v);
        show();
    }

    public void show() {
        total += total;
    }
}

class Child extends Parent {
    int v = 10;

    public Child() {
        v += 2;
        total += v++;
        show();
    }

    @Override
    public void show() {
        total += total * 2;
    }
}
// 풀이 순서
total = 0, v = 1
total = 1 + 1 = 2
Child 객체 오버라이딩
total = total + (2 * 2) = 6

v = 10 -> 12
total + v = 18

total = total + (total * 2) = 18 + 18 *2 = 54
```

25년 2회 기출
```bash
public class Main {

    public static class Parent {

        public int x(int i) {
            return i + 2;
        }

        public static String id() {
            return "P";
        }
    }

    public static class Child extends Parent {

        public int x(int i) {
            return i + 3;
        }

        public String x(String s) {
            return s + "R";
        }

        public static String id() {
            return "C";
        }
    }

    public static void main(String[] args) {
        Parent ref = new Child();
        System.out.println(ref.x(2) + ref.id());
    }
}
정답
5P
```
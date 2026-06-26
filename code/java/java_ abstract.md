abstract란?  
추상 클래스란, 완전하지 않은 '미완성 설계도'. 직접적으로 객체를 만들 수는 없지만, 다른 클래스들이 상속받아 완성해야 하는 기본 틀을 제공한다.  
이 추상 클래스는 추상 메서드를 포함할 수 있다. 추상 메서드는 실행할 구체적인 코드가 없고, 그저 메서드의 이름, 입력값, 반환 타입만 정의돼있다.   
상속받는 클래스는 이 추상 메서드들을 반드시 구현(완성)해야 한다.  

EX_
모든 차에는 주행 기능이 있지만, 각기 다른 차의 주행 방식은 조금씩 다를 수 있다. 이 떄, "차"를 추상 클래스로 생각하고 "주행" 기능을 추상 메서드로 두면, 각 차는 자신의 방식대로 "주행" 메서드를 구현하게 된다.

```bash
abstract class Car {
    abstract void drive(); // 추상 메서드: 어떻게 주행할지 여기서 정의한다.
    
    void startEngine() {
        System.out.println("엔진 ON"); // 일반 메서드: 모든 차가 공통적으로 사용
    }
}

class Sedan extends Car {
    void drive() {
        System.out.println("매끄럽게 도로 주행");
    }
}

class Truck extends Car {
    void drive() {
        System.out.println("짐을 실고 주행");
    }
}
```

23년도 1회 기출
```bash
abstract class Vehicle {
    String name;
    abstract public String getName(String val);

    public String getName() {
        return "Vehicle name:" + name;
    }
}

class Car extends Vehicle {
    private String name;
    public Car(String val) {
        name = super.name=val;
    }
    public String getName(String val) {
        return "Car name:" + val;
    }
    public String getName(byte vla[]) {
        return "Car name:" + val;
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle obj = new Car("Spark");
        System.out.print(obj.getName());
    }
}
```

20년도 3회 기출 (23년도 1회 기출과 동일)
```bash
abstract class Vehicle {
    private String name;

    abstract public String getName(String val);

    public String getName() {
        return "Vehicle name:" + name;
    }

    public void setName(String val) {
        name = val;
    }
}

class Car extends Vehicle {
    public Car(String val) {
        setName(val);
    }

    public String getName(String val) {
        return "Car name : " + val;
    }

    public String getName(byte val[]) {
        return "Car name : " + val;
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle obj = new Car("Spark");
        System.out.print(obj.getName());
    }
}
```
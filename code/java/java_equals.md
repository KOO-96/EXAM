연산자 (==)  
기본 데이터 타입을 비교할 떄 자주 사용한다. 두 값이 같은지 확인하려면 == 을 사용한다.  
같은 메모리 주소를 가리키고 있는지 확인한다. 즉, 두 변수가 같은 객체를 참조하는지 보는 것.  

EX)
```bash
String text1 = new String("hello");
String text2 = new String("hello");
System.out.println(text1 == text2); // false, 이유는 메모리 주소가 다르다.
```
-> text1, text2는 같은 내용의 문자열이다. 하지만 각기 다른 객체 이므로 연산자는 false를 반환한다.

---

equals 메서드
객체의 내용이 같은지를 확인하는데 사용된다.  

EX)
```bash
String text1 = new String("hello");
String text2 = new String("hello");
System.out.println(text1.equals(text2)); // true, 내용이 같다.
```
-> 여기서 text1, text2의 내용은 같기 떄문에 equals 메서드는 true를 반환한다.

결론적으로 == 는 두 객체가 실제로 같은 객체인지, 같은 메모리 상에 위치를 참조하는지 확인하는 반면에, equals는 논리적으로 동등한지를 비교한다.

23년도 2회 기출
```bash
public class Main{
    public static void main(String[] args) {
    
        String str1 = 'Programming';
        String str2 = 'Programming';
        String str3 = new String('Programming');

        println(str1==str2)
        println(str1==str3)
        println(str1.equals(str3))
        println(str2.equals(str3))
    }
}
정답
true / false / true / true
```
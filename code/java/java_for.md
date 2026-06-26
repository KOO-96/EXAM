for 문  
일정한 규칙에 따라 반복해서 명령을 실행할 때 사용한다.  
보통 세 부분으로 구성되어 있다.

초기화  
-> 반복을 시작하기 전에 처음에 설정하는 부분   
조건 
-> 반복을 계속할지 말지 결정하는 조건      
증감   
-> 반복할 때마다 실행되는 부분
```bash
for(unt i = 0; i < 5; i++) {
    System.out.println(i);
}
// 0
// 1
// 2
// 3
// 4

// int i = 0; 반복을 시작하기 전에 변수 i를 0으로 초기화  
// i가 5보다 작은 동안 반복
// i++ 매 반복마다 i 값을 증가
```

20년도 1회 기출
```bash
public class Main {
    public static void main(String[] args) {
        int i;
        int a[] = {0, 1, 2, 3};
        for(i=o; i<4; i++) {
            System.out.println(a[i] + " ");
        }
    }
}

정답
0 1 2 3
```

22년도 3회 기출
```bash
class Test {
    static int[] mkarr() {
        int[] tmpArr = new int[4];
        for (int i = 0; i < tmpArr.length; i++) {
            tmpArr[i] = i;
        }
        return tmaArr;
    }

    public static void main(String[] args){
        int[] arr;
        arr = mkarr();
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
}

정답
0123
```

22년도 2회 기출
```bash
class Main {
    public static void main(String[] args) {
        Cond obj = new Cond(3); // Cond 3
        obj.a = 5; // 5로 바뀜
        int b = obj.func();
        System.out.print(obj.a + b);
    }
}

class Cond {
    int a;

    public Cond(int a) {
        this.a = a; // a=5
    }

    public int func() {
        int b = 1;
        for (int i = 1; i < a; i++) {
            b += a * i; // b + (1*5) + (2*5) + (3*5) + (4*5) --> 1 + 50 = 51
        }
        return a + b; // func = a + b = 5 + 51 = 56
        // obj.a + b = 5 + 56 = 61
    }
}

정답
61
```

22년 3회 기출 
```bash
class Exam {
    public static void main(String[] args) {
        int a = 0;

        for (int i = 1; i < 999; i++) {
            if (i % 3 == 0 && i % 2 == 0)
                a = i;
        }

        System.out.print(a);
    }
}
정답
996
```

24년도 3회 기출
```bash
public class Main {
    static String[] s = new String[3];
// 1차 실행
// 길이가 3인 배열 생성
// s[0] = null, s[1] = null, s[2] = null 
    static void func(String[] s, int size) {
        for (int i = 1; i < size; i++) {
            if (s[i - 1].equals(s[i])) {
// 3차 실행                
//s[1-1].equals(s[1]) --> O
//s[2-1].equals(s[2]) --> O               
                System.out.print("O");
            } else {
                System.out.print("N");
            }
        }

        for (String m : s) {
            System.out.print(m);
// 4차 실행
// s = 3
// AAA
        }
    }

    public static void main(String[] args) {
        s[0] = "A";
        s[1] = "A";
        s[2] = new String("A");
// 2차 실행
// s[0] = A, s[1] = A, s[2] = A 이지만 s[2]는 객체의 위치가 다르다.
        func(s, 3);
    }
}
정답
OOAAA
```

22년도 3회 기출
```bash
public class Test {
    public static void main(String[] args) {
        int result[] = new int[5];

        int arr[] = { 77, 32, 10, 99, 50 };
// result = {0, 0, 0, 0, 0}
// arr = {77, 32, 10, 99, 50}
        for (int i = 0; i < 5; i++) {
            result[i] = 1;

            for (int j = 0; j < 5; j++) {
                if (arr[i] < arr[j]) {
                    result[i]++;
                }
            }
        }

        for (int k = 0; k < 5; k++) {
            System.out.print(result[k]);
        }
    }
}
정답
24513
```

21년 1회 기출
```bash
public class Main {
    public static void main(String[] args) {
        int i, j;
        for(j=0, i=0; i <= 5; i++) {
            j+=i;
            System.out.print(i);
            if(i==5){
                System.out.print("=");
                System.out.print(j);
            } else {
                System.out.print("+");
            }
        }
    }
}
정답
0+1+2+3+4+5=15
```
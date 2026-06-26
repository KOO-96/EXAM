단순 while 문  
특정 조건이 참인 동안 계속해서 코드 블록을 실행한다.  
조건이 거짓이 된다면 그 순간 멈춘다.

EX_
```
int i = 0;
while( i < 5) {
    System.out.println(i)
    i++;
}
```

continue  
반복문의 현재 반복을 즉시 종료하고 다음 반복으로 넘어간다.
이번 단계는 여기까지만 하고, 다음 단계로 넘어간다는 의미이다.

break   
반복문을 완전히 끝내는 역할
EX_
``bash
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        continue;
    }
    if (i == 8) {
        break;
    }
}
```

20년도 3회 기출
```bash
public class Main {
    public static void main(String[] args) {
        int i = 0;
        int sum = 0;
        while (i < 10) {
            i++;
            if (i%2 == 1)
                continue;
            sum += i;
        }
        System.out.println(sum);
    }
}
정답
30
```
---
title: "[Algorithm] 피보나치 수열"
date: 2022-02-08 +0800
categories: [Algorithm]
tags: [java, algorithm, number]
---


### **Question**

- #### description

    1) 피보나키 수열을 출력한다. 피보나치 수열이란 앞의 2개의 수를 합하여 다음 숫자가 되는 수열이다.<br>
    2) 입력은 피보나치 수열의 총 항의 수 이다. 만약 7이 입력되면 1 1 2 3 5 8 13을 출력하면 된다.

- #### input
    첫 줄에 총 항수 N(3<=N<=45)이 입력된다.

- #### output
    첫 줄에 피보나치 수열을 출력합니다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`10` |
| 출력 |`1 1 2 3 5 8 13 21 34 55` |


### **Source**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
  
public class Main {
  private static int[] memo = new int[0];

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int firstNum = Integer.parseInt(br.readLine());

        memo = new int[firstNum];
        fibo(firstNum-1);

        StringBuffer sb = new StringBuffer();
        for (int n : memo) {
            sb.append(n).append(" ");
        }
        System.out.println(String.valueOf(sb).trim());

    }
    private static int fibo(int k) {
        if (memo[k] == 0) { // 처음 계산되는 값
            if (k <= 1) { // 1번 항과 2번 항은 1로 초기화
                memo[k] = 1;
            } else { // 3번째 항 부터는 계산
                memo[k] = fibo(k - 1) + fibo(k - 2);
            }
        }
        return memo[k];
    }
}
```

### **explanation**
재귀함수 사용 :)
---
title: "[Algorithm] 피보나치 수열"
date: 2022-02-08 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, number]
---

### **Question**

#### description
1) 피보나치 수열은 앞의 두 수를 더해 다음 수를 만드는 수열입니다.  
2) 입력은 총 항의 수 N이며, 예를 들어 N=7이면 `1 1 2 3 5 8 13`을 출력합니다.

#### input
첫 줄에 N(3 ≤ N ≤ 45)

#### output
피보나치 수열을 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력 | `10` |
| 출력 | `1 1 2 3 5 8 13 21 34 55` |

---

### **Source**

```java
import java.io.*;

public class Main {
  static int[] memo;

  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    int n = Integer.parseInt(br.readLine());
    memo = new int[n];
    fibo(n - 1);

    for (int num : memo) System.out.print(num + " ");
  }

  static int fibo(int k) {
    if (memo[k] == 0) {
      if (k <= 1) memo[k] = 1;
      else memo[k] = fibo(k - 1) + fibo(k - 2);
    }
    return memo[k];
  }
}
```
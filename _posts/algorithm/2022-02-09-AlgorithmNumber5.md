
---

### ✅ [Algorithm] 소수 (에라토스테네스의 체)

```markdown
---
title: "[Algorithm] 소수(에라토스테네스의 체)"
date: 2022-02-09 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, number]
---

### **Question**

#### description
자연수 N이 주어지면 1부터 N까지의 **소수 개수**를 출력하세요.  
예) 20 → 소수는 2,3,5,7,11,13,17,19로 총 8개.

#### input
첫 줄에 자연수 N(2 ≤ N ≤ 200,000)

#### output
소수의 개수를 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력 | `20` |
| 출력 | `8` |

---

### **Source**

```java
import java.io.*;

public class Main {
  public static int solution(int n) {
    int[] check = new int[n + 1];
    int count = 0;

    for (int i = 2; i <= n; i++) {
      if (check[i] == 0) {
        count++;
        for (int j = i * 2; j <= n; j += i) {
          check[j] = 1;
        }
      }
    }
    return count;
  }

  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    int n = Integer.parseInt(br.readLine());
    System.out.println(solution(n));
  }
}
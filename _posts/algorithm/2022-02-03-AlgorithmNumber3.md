---
title: "[Algorithm] 가위 바위 보"
date: 2022-02-03 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, number]
---

### **Question**

#### description
A와 B가 N번의 가위바위보 게임을 합니다.  
가위(1), 바위(2), 보(3)로 표현되며,  
각 라운드의 결과를 A, B, D(무승부)로 출력합니다.

#### input
첫째 줄: 게임 횟수 N(1 ≤ N ≤ 100)  
둘째 줄: A의 선택  
셋째 줄: B의 선택

#### output
각 라운드 결과를 한 줄씩 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력(1) | `5` |
| 입력(2) | `2 3 3 1 3` |
| 입력(3) | `1 1 2 2 3` |
| 출력 | `A B A B D` |

---

### **Source**

```java
import java.io.*;
import java.util.StringTokenizer;

public class Main {
  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    int n = Integer.parseInt(br.readLine());
    int[] A = parse(n, br.readLine());
    int[] B = parse(n, br.readLine());

    for (int i = 0; i < n; i++) {
      System.out.println(compare(A[i], B[i]));
    }
  }

  static int[] parse(int n, String line) {
    StringTokenizer st = new StringTokenizer(line);
    int[] arr = new int[n];
    for (int i = 0; i < n; i++) arr[i] = Integer.parseInt(st.nextToken());
    return arr;
  }

  static String compare(int a, int b) {
    if (a == b) return "D";
    if ((a == 1 && b == 3) || (a == 2 && b == 1) || (a == 3 && b == 2)) return "A";
    return "B";
  }
}
```
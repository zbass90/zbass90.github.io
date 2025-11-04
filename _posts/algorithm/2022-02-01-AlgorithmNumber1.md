---
title: "[Algorithm] 큰 수 출력하기"
date: 2022-02-01 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, number]
---

### **Question**

#### description
N개의 정수를 입력받아 **자신의 바로 앞 수보다 큰 수만 출력**하는 프로그램을 작성하세요.  
(첫 번째 수는 무조건 출력합니다.)

#### input
첫 줄에 자연수 N(1 ≤ N ≤ 100)

#### output
자신의 바로 앞 수보다 큰 수를 한 줄로 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력(1) | `6` |
| 입력(2) | `7 3 9 5 6 12` |
| 출력 | `7 9 6 12` |

---

### **Source**

```java
import java.io.*;
import java.util.StringTokenizer;

public class Main {
  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    int n = Integer.parseInt(br.readLine());
    StringTokenizer st = new StringTokenizer(br.readLine());
    int[] arr = new int[n];

    for (int i = 0; i < n; i++) arr[i] = Integer.parseInt(st.nextToken());

    StringBuilder sb = new StringBuilder();
    sb.append(arr[0]).append(" ");

    for (int i = 1; i < n; i++) {
      if (arr[i] > arr[i - 1]) sb.append(arr[i]).append(" ");
    }

    System.out.println(sb.toString().trim());
  }
}
```
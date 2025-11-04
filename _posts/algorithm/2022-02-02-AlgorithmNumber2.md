
---

### ✅ [Algorithm] 보이는 학생

```markdown
---
title: "[Algorithm] 보이는 학생"
date: 2022-02-02 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, number]
---

### **Question**

#### description
N명의 학생을 일렬로 세웠을 때,  
앞에 서 있는 사람보다 **더 큰 학생만 보이는** 학생의 수를 구하는 프로그램을 작성하세요.

#### input
첫 줄에 정수 N(5 ≤ N ≤ 100,000)  
다음 줄에 N명의 학생 키가 주어집니다.

#### output
보이는 학생의 수를 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력(1) | `8` |
| 입력(2) | `130 135 148 140 145 150 150 153` |
| 출력 | `5` |

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

    int max = arr[0], count = 1;
    for (int i = 1; i < n; i++) {
      if (arr[i] > max) {
        count++;
        max = arr[i];
      }
    }

    System.out.println(count);
  }
}
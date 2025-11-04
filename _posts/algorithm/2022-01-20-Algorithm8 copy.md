---
title: "[Algorithm] 숫자만 추출"
date: 2022-01-20 00:00 +0900
categories: [Algorithm]
tags: [java, algorithm, string]
---

### **Question**

#### description
문자와 숫자가 섞여있는 문자열이 주어지면,  
그 중 **숫자만 추출하여 순서대로 자연수를 만드는 프로그램**을 작성하세요.  
예를 들어 `"tge0a1h205er"`에서 숫자만 추출하면 `0, 1, 2, 0, 5` → `1205`가 됩니다.  
추출하여 만들어지는 자연수는 **100,000,000을 넘지 않습니다.**

#### input
첫 줄에 숫자가 섞인 문자열이 주어집니다. 문자열의 길이는 100을 넘지 않습니다.

#### output
첫 줄에 자연수를 출력합니다.

---

### **Example**

| 항목 | 값 |
|:---|:---|
| 입력 | `g0en2T0s8eSoft` |
| 출력 | `208` |

---

### **Source**

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    String words = sc.nextLine();

    if (words.length() > 100) return;

    StringBuilder sb = new StringBuilder();

    for (int i = 0; i < words.length(); i++) {
      char ch = words.charAt(i);
      if (Character.isDigit(ch)) {
        sb.append(ch);
      }
    }

    System.out.println(Integer.parseInt(sb.toString()));
  }
}
```
---
title: "[Algorithm] 소수(에라토스테네스 체)"
date: 2022-02-09 +0800
categories: [Algorithm]
tags: [java, algorithm, number]
---


### **Question**

- #### description

    자연수 N이 입력되면 1부터 N까지의 소수의 개수를 출력하는 프로그램을 작성하세요.<br>
    만약 20이 입력되면 1부터 20까지의 소수는 2, 3, 5, 7, 11, 13, 17, 19로 총 8개입니다.

- #### input
    첫 줄에 자연수의 개수 N(2<=N<=200,000)이 주어집니다.

- #### output
    첫 줄에 소수의 개수를 출력합니다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`20` |
| 출력 |`8` |


### **Source**

```java
import java.io.BufferedReader; 
import java.io.IOException; 
import java.io.InputStreamReader;
public class Main {
      public static int solution(int n) { 
        int[] arr = new int[n+1];
        int count = 0; 
        for (int i = 2; i <= n; i++) { 
          if (arr[i] == 0) { 
            count++; 
            for (int j = i*2; j <= n; j+=i) { 
              arr[j] = 1; 
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
```

### **explanation**
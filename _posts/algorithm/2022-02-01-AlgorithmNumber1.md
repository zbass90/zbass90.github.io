---
title: "[Algorithm] 큰 수 출력하기"
date: 2022-02-01 +0800
categories: [Algorithm]
tags: [java, algorithm, number]
---


### **Question**

- #### description

    N개의 정수를 입력받아, 자신의 바로 앞 수보다 큰 수만 출력하는 프로그램을 작성하세요.<br>
    (첫 번째 수는 무조건 출력한다)

- #### input
    첫 줄에 자연수 N(1<=N<=100)

- #### output
    자신의 바로 앞 수보다 큰 수만 한 줄로 출력한다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`6` |
| 두번째 입력 | `7 3 9 5 6 12` |
| 출력 |`7 9 6 12` |


### **Source**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;
public class Main {
  public static void main(String[] args) throws IOException {
   BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int firstNum = Integer.parseInt(br.readLine());
        StringTokenizer secondNums = new StringTokenizer(br.readLine());

        StringBuffer sb = new StringBuffer();

        int[] intList = new int[firstNum];
        int cnt = 0;
        while(secondNums.hasMoreTokens()){
            intList[cnt++] = Integer.parseInt(secondNums.nextToken());
        }

        for(int i=0; i < firstNum; i++){
            if(i == 0 ){
                sb.append(intList[i]).append(" ");
            }
            if(i > 0 && intList[i] > intList[i-1]){
                sb.append(intList[i]).append(" ");
            }
        }

        System.out.println(String.valueOf(sb).trim());
  }
}
```

### **explanation**
...
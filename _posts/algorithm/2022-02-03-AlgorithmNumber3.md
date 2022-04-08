---
title: "[Algorithm] 가위 바위 보"
date: 2022-02-03 +0800
categories: [Algorithm]
tags: [java, algorithm, number]
---


### **Question**

- #### description

    A, B 두 사람이 가위바위보 게임을 합니다. 총 N번의 게임을 하여 A가 이기면 A를 출력하고, B가 이기면 B를 출력합니다.<br>
    비길 경우에는 D를 출력합니다.<br>
    가위, 바위, 보의 정보는 1:가위, 2:바위, 3:보로 정하겠습니다.<br>
    예를 들어 N=5이면 두 사람의 각 회의 가위/바위/보 정보가 주어지면 각 회를 누가 이겼는지 출력 프로그램을 작성하세요.

- #### input
    첫 번째 줄에 게임 횟수인 자연수 N(1<=N<=100)이 주어집니다.<br>
    두 번째 줄에는 A가 낸 가위, 바위, 보 정보가 N개 주어집니다.<br>
    세 번째 줄에는 B가 낸 가위, 바위, 보 정보가 N개 주어집니다.

- #### output
    각 줄에 각 회의 승자를 출력합니다. 비겼을 경우는 D를 출력합니다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`5` |
| 두번째 입력 | `2 3 3 1 3` |
| 세번째 입력 | `1 1 2 2 3` |
| 출력 |`A`<br>`B`<br>`A`<br>`B`<br>`D` |


### **Source**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

  
public class Main {
  public static void main(String[] args)  throws IOException  {
     BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int firstNum = Integer.parseInt(br.readLine());
        Main m = new Main();
        int[] firstArr = m.tokenList(firstNum, br.readLine());
        int[] secondArr = m.tokenList(firstNum, br.readLine());

        for(int i=0; i < firstNum; i++){
            System.out.println(m.compareValue(firstArr[i], secondArr[i]));
        }
  }
  
   public int[] tokenList(int firstNum, String br){
        StringTokenizer numberToken = new StringTokenizer(br);
        int[] intList = new int[firstNum];
        int cnt = 0;
        while(numberToken.hasMoreTokens()){
            intList[cnt++] = Integer.parseInt(numberToken.nextToken());
        }
        return intList;
    }

    public String compareValue(int a, int b) {
        //가위, 바위, 보의 정보는 1:가위, 2:바위, 3:보로 정하겠습니다
        if(a == b) return "D";
        else if(a == 2 && b == 1) return "A";
        else if( a == 3 && b == 2) return "A";
        else if( a == 1 && b == 3) return "A";
        else return "B";
    }
}
```

### **explanation**
...
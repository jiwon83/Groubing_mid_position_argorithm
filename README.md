# 다각형의 중점 알고리즘

﻿

원리

x,y 좌표 점 여러개들 중 y좌표가 가장 적은 점을 기준으로 각도를 계산해서 다각형리스트를 만든다.

다각형을 여러 개의 삼각형으로 분할

기준점인 한 점으로부터 양 옆의 인접한 두 점을 제외한 점들과 모두 연결

![다각형 삼각형으로 분할](https://user-images.githubusercontent.com/88698607/175563164-17d08a39-225c-4277-9f8e-04dd06a82980.png)

-- ![다각형_삼각형으로_분할2](https://user-images.githubusercontent.com/88698607/175563380-b48e4f1a-555d-403a-8b12-9a9ce0f6cf87.png)
<img src="https://user-images.githubusercontent.com/88698607/175563380-b48e4f1a-555d-403a-8b12-9a9ce0f6cf87.png"  width="700" height="370">


3. 각 삼각형의 중점을 구한다.

각 빗변의 중점을 구하고 중점들을 연결하여 작은 삼각형을 만든다.

삼각형이 아주 작아질때까지 반복한다.

삼각형의 두 점을 유클리디안 거리 공식으로 구하여 이 거리가 매우 작아지면, 한 점의 좌표가 중점에 수렴.



![삼각형의중점](https://user-images.githubusercontent.com/88698607/175563425-19512d6f-44b4-460d-8ff3-fef3a846203c.png)


4. 그렇게 나온 중점이 3개 이상일 경우 2~3번 과정을 반복, 2개일 경우 산술평균으로 하나의 중점을 구하고, 1개일 경우 그 점이 중점이 된다.




알고리즘 개요

![알고리즘구조](https://user-images.githubusercontent.com/88698607/175563458-438860c8-97a1-47db-8519-c32a937731ee.png)


input: x,y Point객체로 이루어진 리스트

output: 중점 x,y Point 객체



코드


- Point.java : x, y 좌표 클래스


- Triangle.java


- Ploygon.java

매서드들의 실행 순서는 다음과 같다.


1. getPloygonMidPoint()

2. pointToMidPoint()

3. init()

4. coputeAngle()

5. divideToTriangle()

6. getMidPoint()



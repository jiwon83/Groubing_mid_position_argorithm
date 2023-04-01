# 다각형의 중점 알고리즘

﻿

## 알고리즘 개선 과정



<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

## 원리

+ x,y 좌표들 중 y좌표가 가장 적은 점을 기준으로 각도 계산을 통한 다각형 리스트 생성

+ 생성된 다각형을 여러 개의 삼각형으로 분할 (기준점으로부터 양 옆의 인접한 두 점을 제외한 점들과 모두 연결)

+ 삼각형의 수렴 점을 계산

+ 해당 과정을 반복


<img src="https://user-images.githubusercontent.com/88698607/175563164-17d08a39-225c-4277-9f8e-04dd06a82980.png"  width="650" height="660">

----------


![다각형_삼각형으로_분할2](https://user-images.githubusercontent.com/88698607/175563380-b48e4f1a-555d-403a-8b12-9a9ce0f6cf87.png)

----------

<img src="https://user-images.githubusercontent.com/88698607/175563425-19512d6f-44b4-460d-8ff3-fef3a846203c.png"  width="550" height="500">




<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

## 알고리즘 개요

<img src="https://user-images.githubusercontent.com/88698607/175563458-438860c8-97a1-47db-8519-c32a937731ee.png" width="600" height="600"


input: x,y Point객체로 이루어진 리스트

output: 중점 x,y Point 객체



관련 CLASS


- Point.java : x, y 좌표 클래스


- Triangle.java


- Ploygon.java

     
매서드들의 실행 순서


1. getPloygonMidPoint()

2. pointToMidPoint()

3. init()

4. coputeAngle()

5. divideToTriangle()

6. getMidPoint()



# 다각형의 중점 알고리즘

﻿3. 중간 배송지 알고리즘 원리 및 구현
![그림24](https://user-images.githubusercontent.com/76260153/182795170-088fa3e4-6e09-4074-981f-4ac26bdda60b.png)
- 공동 구매 거래자들의 주소를 활용해 최적의 중간 지점과, 중간 지점과 가까운 편의점 찾기
- 다각형의 각 변의 이등분 선으로 점점 더 작은 다각형을 만들어 수렴하도록 하는 방법

![그림21](https://user-images.githubusercontent.com/76260153/182794962-27b15a48-7932-442d-922f-5923fdb7de95.png)
- 카카오 맵 API의 service.Geocoder 객체의 addressSearch(), coord2Address() 함수를 활용하여 지번주소를 위경도로 변환

![그림22](https://user-images.githubusercontent.com/76260153/182794978-905668a1-9c52-4802-85da-6e060c4ba38c.png)
- 유클리디안 거리를 활용

![그림23](https://user-images.githubusercontent.com/76260153/182794987-cbd6333f-5cb8-4bbd-b027-6234ee14b31d.png)

##### 구현 결과
<img width="963" alt="그림25" src="https://user-images.githubusercontent.com/76260153/182795907-95d0cd0f-ad77-446a-b6fa-606cd7a64da4.png">

## 고민 과정
+ 처음으로, 산술평균을 계산했지만 무게 중심 때문에 (예를 들어, 서울 부산, 강원에 유저가 있다면 부산에 거주하는) 특정 사용자에게 지나치게 멀다는 문제가 발생했습니다.
+ 두번째로, 외심을 이용한 방법을 생각했지만 모두에게 동일한 거리를 제공할 수 있지만 아래 그림의 왼쪽처럼 효율성이 다소 떨어지는 위치가 도출될 수 있다는 문제가 있습니다.
+ 따라서 물론 각 사용자간 거리의 편차는 존재하지만 합리적인 중간 위치를 제공하기 위해 아래 그림의 오른쪽의 방식으로 구현하도록 했습니다.

<img src="https://user-images.githubusercontent.com/88698607/229268722-6e7aed7e-484c-4c34-a9a4-e3e7e540d33f.png"  width="1000" height="560">

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

<img src="https://user-images.githubusercontent.com/88698607/175563458-438860c8-97a1-47db-8519-c32a937731ee.png" width="600" height="600">


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



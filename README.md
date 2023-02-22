<h1 align="center"> 
시각장애인을 위한 편의점 음료 인식 어플<br/>
A Beverage Detection Application for Visually Impaired
<br> 
<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white">
<img src="https://img.shields.io/badge/YOLO-00FFFF?style=flat&logo=SVG&logoColor=white">
</h1>

![ppt1표지](https://user-images.githubusercontent.com/115054956/220268178-d7f2dbec-c6bd-4029-88db-6fbc8210d557.png)

## 개요 Overview
### 1. 다양한 시각장애인의 시야 Various Eyesights of Visually Impaired
* 비장애인은 흔히 시각장애인이 모두 전맹이라고 생각하지만, 실제 시각장애인의 시야는 다양합니다.
![2023-02-22 13 26 41](https://user-images.githubusercontent.com/115054956/220521854-f1d5d730-2d1c-4155-996d-0e0dab184237.png)

### 2. 시각장애인이 편의점에서 음료를 고르는 방법 The Way Visually Impaired Select Products in Retails
* 대부분의 음료에 점자가 없거나 '음료'라고만 되어 있어 시각장애인이 상품 선택 시 어려움을 겪습니다.

(한솔 영상 움짤로 올라갈 예정)
![2023-02-22 13 30 34](https://user-images.githubusercontent.com/115054956/220522326-1bebd7f5-a008-4ddb-a7a1-69050e631fb1.png)

### 3. 쇼우나우 어플 소개 Introduction Of ShowNow Application
<div align="center"> <img src="https://user-images.githubusercontent.com/115054956/220498305-a9a433ed-435e-49ab-a435-8c6cb0d3ac5c.png" width="800"> </div>


### 4. 시각장애인이 어플을 사용하는 방법 The Way Visually Impaired Use Phone and Applications
* 시각장애인도 핸드폰과 어플을 사용할 수 있습니다.

(우령 영상 움짤로 올라갈 예정)
![2023-02-22 13 32 01](https://user-images.githubusercontent.com/115054956/220522515-370c12f0-7c77-487e-a0da-591d83953a70.png)


## 데이터 출처, 규모, 정제 Dataset
* 데이터는 아래와 같이 세 가지로 나뉩니다.
  - 편의점에서 직접 촬영한 데이터 약 700장
  - AI Hub에서 다운로드 받은 데이터 약 800장
  - 웹크롤링 데이터 약 1800장
![2023-02-22 13 46 19](https://user-images.githubusercontent.com/115054956/220524488-33979103-ee42-43b6-b85e-d9cefdefe387.png)
* 전처리 작업은 [Roboflow](https://app.roboflow.com/mainproject)에서 진행하였습니다. 
![2023-02-22 13 46 25](https://user-images.githubusercontent.com/115054956/220524498-a5f79f4e-b9fc-4e30-8aea-17ba3b6f6c8a.png)

## YOLOv5 nano 모델 선정 이유
![2023-02-22 13 46 33](https://user-images.githubusercontent.com/115054956/220524502-aa87561b-4876-46a2-9f51-6736c379f56f.png)
![2023-02-22 13 55 09](https://user-images.githubusercontent.com/115054956/220525699-3909b544-2acf-4a4a-82e5-7d6c66889cc1.png)
![2023-02-22 13 55 13](https://user-images.githubusercontent.com/115054956/220525705-4850cb91-5048-4b39-9966-430fc1e7576c.png)

* YOLOv5 nano는 CPU와 GPU에서 모두 가장 빠른 모델입니다.

![2023-02-22 13 43 32](https://user-images.githubusercontent.com/115054956/220524241-ffd09189-c4f9-420a-be9c-a51a544ca96d.png)
![2023-02-22 13 44 21](https://user-images.githubusercontent.com/115054956/220524246-fa161b0f-9227-4d07-bb81-04e37928c55d.png)

* 실제 데이터셋으로 비교하였을 떄에도 YOLOv5 nano가 뛰어난 성능을 보였습니다.
![2023-02-22 13 52 40](https://user-images.githubusercontent.com/115054956/220525350-5671879c-ca04-4776-8080-b74136b879a3.png)

## 모델 개선
![2023-02-22 13 57 09](https://user-images.githubusercontent.com/115054956/220526292-c49d5261-213f-483c-a35c-51529c85657e.png)
![2023-02-22 13 57 37](https://user-images.githubusercontent.com/115054956/220526299-60161cac-1925-43d0-b442-5f48dd34de8d.png)
![2023-02-22 13 58 49](https://user-images.githubusercontent.com/115054956/220526300-e1cf4d03-c8b7-4344-8e21-0dea250d9d86.png)
![2023-02-22 13 58 59](https://user-images.githubusercontent.com/115054956/220526303-a06f82be-5eab-4be5-8d1c-e44aadb17ffe.png)
![2023-02-22 13 59 35](https://user-images.githubusercontent.com/115054956/220526305-78d0ed0d-d8c8-40b1-b146-fde0e630ae4a.png)


## 어플 구현 과정
![2023-02-22 14 08 38](https://user-images.githubusercontent.com/115054956/220527743-5d4e9cb0-f43a-43db-b3c3-1a9f17d72ca7.png)

* 어플 시작 → 상품 인식 → TTS로 안내
![2023-02-22 14 02 21](https://user-images.githubusercontent.com/115054956/220527755-73d6132e-8344-4ed1-87c9-d053f8da5841.png)
![2023-02-22 14 02 37](https://user-images.githubusercontent.com/115054956/220527759-9511ad1f-4f84-4d6d-91fb-cf43938f04a2.png)

## 어플 시연 영상
![2023-02-22 14 09 55](https://user-images.githubusercontent.com/115054956/220527975-04b09f70-9769-4669-ba2a-8f432699f570.png)

## 어플 등록 현황
<div align="center"> <img src="https://user-images.githubusercontent.com/115054956/220528400-21bb28d4-8df9-4292-8764-421e20b3b004.jpg" width="500"> </div>


## 한계점과 확장 방안
![2023-02-22 14 17 50](https://user-images.githubusercontent.com/115054956/220529370-b3c34826-0151-4d15-bf91-908d1e85e6fc.png)
![2023-02-22 14 24 01](https://user-images.githubusercontent.com/115054956/220530363-180ce32f-e488-409f-bf07-20df112d8fb6.png)


---
![2023-02-22 14 19 25](https://user-images.githubusercontent.com/115054956/220529615-25e767ff-00f5-4624-8d5f-38a37da90f29.png)


## Authors
이창재 [박성혜](https://www.linkedin.com/in/%EB%B0%95%EC%84%B1%ED%98%9Clea/) 임보라 정유석

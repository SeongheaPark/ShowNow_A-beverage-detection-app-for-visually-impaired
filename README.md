<h1 align="center"> 
시각장애인을 위한 편의점 음료 인식 어플<br/>
A Beverage Detection Application for Visually Impaired
<br> 
<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white">
<img src="https://img.shields.io/badge/YOLO-00FFFF?style=flat&logo=SVG&logoColor=white">
</h1>

![ppt1표지](https://user-images.githubusercontent.com/115054956/220268178-d7f2dbec-c6bd-4029-88db-6fbc8210d557.png)
![ppt3시야](https://user-images.githubusercontent.com/115054956/220268183-7a6efba2-56e2-4b55-8d47-a6efbe45e5ea.png)
![ppt4한솔](https://user-images.githubusercontent.com/115054956/220269133-94e65b70-e067-49d2-9e0c-5396c00dbb3a.png)
![ppt5소개1](https://user-images.githubusercontent.com/115054956/220268190-35e0e3b0-fe98-4fa9-b9a1-81589fdfbe57.png)
![ppt6소개2](https://user-images.githubusercontent.com/115054956/220268196-f5c8266a-440a-43a1-88a1-587267cab3d1.png)
![ppt7소개3](https://user-images.githubusercontent.com/115054956/220268198-88844f12-7d79-4a5e-b33b-2d0832633621.png)
![ppt8소개4](https://user-images.githubusercontent.com/115054956/220268200-ba583d80-22e5-4360-9350-94b72e1f0df8.png)
![ppt9팀구성](https://user-images.githubusercontent.com/115054956/220268206-4d221cbc-4a4a-4f47-a945-38ee177604e8.png)
![ppt10수행일정](https://user-images.githubusercontent.com/115054956/220268209-d16b1f4d-a48c-474c-9816-e487a990210f.png)
![ppt11데이터1](https://user-images.githubusercontent.com/115054956/220268211-6ad1ce51-ca10-4730-81d9-1ea13668056e.png)
![ppt12데이터2](https://user-images.githubusercontent.com/115054956/220268214-fea3e49e-7035-4007-aee8-fdf1b6410cb5.png)
![ppt13모델1](https://user-images.githubusercontent.com/115054956/220268216-99d72cbc-d8c5-4ee7-85c8-94ce4448bb71.png)
![ppt14모델2](https://user-images.githubusercontent.com/115054956/220268220-8990e42c-9cb1-4a5a-8503-7df14fb4df35.png)
![ppt15](https://user-images.githubusercontent.com/115054956/220268221-27b536ae-f354-4b6b-bf76-7d78c0842cfb.png)
![ppt16](https://user-images.githubusercontent.com/115054956/220268226-48d46141-f63f-4ef0-8f0a-ea40b42ebc13.png)
![ppt17](https://user-images.githubusercontent.com/115054956/220268229-d8ba53bd-cae0-4530-8941-4391b08b320c.png)
![ppt18](https://user-images.githubusercontent.com/115054956/220268232-fa0fad0d-9fab-4890-8fbf-a0f1f3fb5b5d.png)
![ppt19](https://user-images.githubusercontent.com/115054956/220268237-2b0c80a3-db3c-41a1-9ae5-9cf2b965c4c3.png)
![ppt20](https://user-images.githubusercontent.com/115054956/220268239-50bce379-140b-4c2d-9429-1dd33da7fa85.png)
![ppt21](https://user-images.githubusercontent.com/115054956/220268240-72d7340a-b0c3-4210-933b-110d5abd25da.png)
![ppt22](https://user-images.githubusercontent.com/115054956/220268241-a27a4530-6268-4a28-a728-67a1f19d4d4f.png)
![ppt23](https://user-images.githubusercontent.com/115054956/220268246-f85f6fad-45ce-4622-ab0f-75144ad41fae.png)
![ppt24](https://user-images.githubusercontent.com/115054956/220268248-d1cb0147-57f5-40d8-bb6e-7825138a9154.png)
![ppt25](https://user-images.githubusercontent.com/115054956/220268252-ed6c22f9-9135-43fa-b23f-cb2bd36e63a7.png)
![ppt26](https://user-images.githubusercontent.com/115054956/220268255-729b1f99-b10c-4c8f-b0d4-08c896b9f374.png)
![ppt27](https://user-images.githubusercontent.com/115054956/220268257-218d0592-beca-49ef-bd27-fcbaff293358.png)
![ppt28](https://user-images.githubusercontent.com/115054956/220268259-80833fec-4746-4385-a533-af8cce9f200f.png)


## 📌 Background of the Project
![background](https://user-images.githubusercontent.com/58678384/173717085-f20d9ad1-375b-474a-91e9-bdd60b4f6676.png)
* 일반적인 소매점에서 과자나 식료품 및 기타 상품에는 점자가 표기 되어 있지 않은 경우가 대부분임
* 점자가 표기되어 있는 캔 음료의 경우이더라도, 탄산과 그 외의 음료로만 구분 가능
* 촉각을 통해 상품에 대한 정보를 얻고자 물건을 집어 들어도, 물건을 다시 제자리에 다시 두는 것도 어려운 상황
* 시각장애인은 다른 사람의 도움 없이는 개인의 선호나 필요에 따라 상품을 구매하기 어려운 실정
**→ 사진으로 각 상품들을 인식하여 을 음성으로 이에 대한 정보를 제공해주는 구매 보조 시스템을 제안**

## 📌 Process of the System
![image](https://user-images.githubusercontent.com/58678384/173717407-855012b8-6b09-4393-9a06-602ded3c6c8b.png)
1. 소매점 내 제품을 촬영한 이미지(정지영상) 입력
2. 입력된 영상에서 객체 인식 수행 : YOLO 모델 사용
	2-1. **입력 화면 내 상품 객체 찾기** : 상품 정보를 인식하여 이에 대한 정보를 제공하기 위함
	2-2.**입력 화면 내 손 객체 찾기** : 화면 내 수많은 상품 정보가 동시에 인식 될 때 하나를 지정하여 차례로 정보를 제공하기 위함
3. **손 객체 영역과 중첩된 상품 객체 찾기** : 화면에 인식되는 많은 제품 중 하나를 선택하기 위함
4. 가장 많은 영역이 중첩된 상품 객체의 이름과 영양정보(칼로리, 영양성분 등)를 불러오기
5. 불러온 정보를 TTS 로 출력 

##  📌 Install

* OpenCV : Hand Detection에 사용하기 위함
* Pandas : 텍스트로 저장되는 상품 인식 영역 좌표 정보를 불러오기 위함
* Gtts : 인식된 정보를 음성으로 안내해주기 위함

	    pip install opencv-python pandas gttse


## 📌 How to Use
[<h3> 1️⃣ Learning_Product_Detect_(colab).ipynb</h3>](https://github.com/DyeonPark/Product-Detection-for-Visually-Impaired/blob/master/Learning_Product_Detect_(colab).ipynb)

* Yolov5 모델을 사용하여 학습을 진행합니다.
* Colab으로 실행하는 것을 권장하며, 데이터셋은 자동으로 연결됩니다.
* 새로운 학습 모델을 만들고자 하는 경우만 실행하며, 그렇지 않을 때는 2️⃣부터 시작하도록 합니다.

[<h3> 2️⃣ Classify_Product.ipynb</h3>](https://github.com/DyeonPark/Product-Detection-for-Visually-Impaired/blob/master/Classify_Product.ipynb) 

* 학습된 모델을 불러와 **손 영역 검출**과 **제품 영역 검출**을 수행합니다.
* (1) 처리하고자 하는 이미지는 /datasets/images/에 넣어주도록 합니다
* (2) 해당 이미지의 경로(**IMAGE_FILENAME**)를 코드에서 꼭 바꿔주는 것에 유의합니다
	* `img_file_name = "IMAGE_FILENAME"` --- 3rd Cell 1st Line
	* `!python yolov5/detect.py --weights weights/best_10class_150.pt --img 416 --conf 0.3 --source datasets/images/IMAGE_FILENAME.jpg --line-thickness 4 --save-txt` --- 5th Cell 1st Line
* (3) 각 상품 인식 결과와 음성 설명은 datasets/results/IMAGE_FILENAME/ 경로에 저장됩니다


## ✅ Dataset & Model Learning & Result

### 1. Datasets
![image](https://user-images.githubusercontent.com/58678384/173721348-a2845ef9-b976-47ff-ae1a-c527d9f9dd31.png)
1. AI Hub에서 '[상품 이미지](https://aihub.or.kr/aidata/34145)' 데이터셋 저장 (일부 10가지 항목의 제품만 프로젝트에 사용)
![image](https://user-images.githubusercontent.com/58678384/173722692-de82b161-ec8c-4ece-8601-956309653108.png)


2. [RoboFlow](https://roboflow.com/)를 사용하여 Annotation & Augmentation수행
	* Train : Valid : Test = 70 % : 20 % : 10 % (896장 / 250장 / 144장)
	* 원본 총 1290장에 대해서 Annotation 수행 → 다양한 전처리 및 증강작업 수행 → 3082장으로 증강

### 2. Model (Yolov5)  Leanring
![image](https://user-images.githubusercontent.com/58678384/173720902-e5421695-6539-4571-a62a-72cc8150bb6f.png)

![image](https://user-images.githubusercontent.com/58678384/173720954-d26156b8-8e86-4474-835b-8b5341457a4d.png)

![image](https://user-images.githubusercontent.com/58678384/173721124-dde5777a-8259-4429-9240-f883798974f3.png)

### 3. Result
#### 3-1. Hand Detection
![image](https://user-images.githubusercontent.com/58678384/173722580-cbc648fc-d9d3-44d0-8082-b023553ce623.png)
#### 3-2. Product Detection
![image](https://user-images.githubusercontent.com/58678384/173722239-38877255-d7ea-4789-bd91-91117a5c1dec.png)
![image](https://user-images.githubusercontent.com/58678384/173722352-b9865354-5b14-4fa7-85a2-5da492887fdd.png)
![image](https://user-images.githubusercontent.com/58678384/173722547-81e588e3-60ee-4095-b458-bc3888014e5c.png)

## 💬 References
* [시각장애인에겐 요만큼만… 점자 정보 인색한 사회](https://m.hankookilbo.com/News/Read/201906121483734269)
* [시각장애인 유투버 한솔의 편의점 내 제품 구매 영상 콘텐츠](https://www.youtube.com/watch?v=fq5xQaWaMO0)
* 공개SW 문제해결 프로젝트 ‘[시각장애인을 위한 음료수를 판별하는 iOS 어플 만들기](https://www.sosslab.kr/social_problem/%EC%8B%9C%EA%B0%81%EC%9E%A5%EC%95%A0%EC%9D%B8%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%8E%B8%EC%9D%98%EC%A0%90-%EC%9D%8C%EB%A3%8C-%EC%95%88%EB%82%B4-%EC%84%9C%EB%B9%84%EC%8A%A4-BeYerage)'
* 배민경, 서현아, 이영우. (2021), OCR 기반 시각장애인을 위한 편의점 음료 구입 보조 시스템. 한국콘텐츠학회 종합학술대회 논문집, pp. 11-12.

## 👩‍💻 Authors
[Dong-Yeon Park](https://github.com/DyeonPark) | 📧 yeon0729@sookmyung.ac.kr

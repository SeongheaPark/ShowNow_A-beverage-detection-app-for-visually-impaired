# ShowNow_A-beverage-detection-app-for-visually-impaired
This is an application which can detect beverage products in retail stores using YOLOv5 nano.


<h1 align="center"> 
시각장애인을 위한 소매점 내 제품 구매 보조 시스템<br/>
Product Purchase Assistance System for the Visually Impaired in Retail Store
<br> 
<img src="https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=Jupyter&logoColor=white">
<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white">
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=NumPy&logoColor=white">
<img src="https://img.shields.io/badge/YOLO-00FFFF?style=flat&logo=SVG&logoColor=white">
<h3 align="center">일상생활 속 시각장애인의 독립적이고 자유로운 소매점 이용을 위한 음성 구매 보조 시스템</h3>
</h1>

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

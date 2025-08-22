# BalanceTeam

**GDSC DAU Headington(2023-11-06~10)**
**Team: Balance**
**Collaborators:[EunByu1](https://github.com/EunByu1), [seonae-j](https://github.com/seonae-j), [w1shope](https://github.com/w1shope), [wjdheesp44](https://github.com/wjdheesp44)**
![헤딩톤 2등 이미지](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/8d39af24-76e6-4228-9077-ef9a01021e2d)

---

# UP

![UP 텍스트 이미지](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/e7a226ae-c831-4086-a79b-390ef0cc3100)
![University Plogging 텍스트 이미지](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/e89e2350-24c2-4ee2-bb2f-b1b8326a430a)

---

## 📱 앱의 용도

### 문제인식

![3  Good health and well-being](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/4c001aa2-8559-457f-aea3-ca6d33a99cbd)
![15 life on earth](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/16f6cf6d-5289-4611-8226-09827c36c0af)

- 현대 사회 사람들이 운동부족 문제에 대면하고있다.
- 길거리에 쓰레기가 돌아다니고 있고 버리는 사람 따로 줍는사람 따로있는 안타까운 현실이다.
- 특히 한국에서는 담배꽁초문제가 심각하다.
- 이 둘을 합친 플로깅이라는 아이디어를 고안해내어 운동을 하면서 쓰레기도 주울 수 있고 이로 대학생들끼리 서로 경쟁도 하는 앱을 고안한다.

### 개발 동기 (Reason for Development)

- 플로깅을 통해 쓰레기 줍기를 실천하며 환경을 지키는 활동이 부산 지역에서 활발하게 일어나고 있습니다.
- 플로깅을 대학생들이 **손쉽게 접근하여 실천해 볼 수 있는 앱이 없을까?** 하는 생각에 개발하게 되었습니다.

### Plogging이란?
- **스웨덴어 "plocka upp"(이삭 줍다) + 영어 "jogging"(달리기)**  
- 즉, **“쓰레기를 줍는 달리기”**  
- 건강도 챙기고, 환경도 지키는 **착한 운동**

---

## 🎥 사용 장면

- [영상링크](https://drive.google.com/drive/folders/1Qj8Hbqxmx40U6Zst6BogJ6FRQPai3m8j)
- 아래 구현 화면 참고

---

## 🛠 사용 기술

- **[Figma](https://www.figma.com/)** : UI/UX 기획 및 디자인  
- **[Flutter](https://flutter.dev/)** : Cross-platform 앱 개발 (Android & iOS 지원)  
- **[Google Map](https://developers.google.com/maps)** : 사용자 경로 추적 및 위치 기반 서비스  
- **[Firebase](https://firebase.google.com/)** : 사용자 정보 및 이미지 데이터 저장  
- **[YOLOv8 → TensorflowLite](https://github.com/ultralytics/ultralytics)** : 쓰레기 사진 인식 및 점수 반영  

---

## 구현과정

![20231112_220611](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/457eaec4-990d-4e62-baac-a92084b19d2e)
![20231112_220748](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/71db0191-4134-4cc8-aba7-91e46a193b38)

---

## 📲 구현화면

### 초기 Figma 디자인

<img width="616" alt="피그마 이미지" src="https://github.com/BOJ-ios/BalanceTeam/assets/44316764/b3cbcd71-d5fb-4059-867c-9bc75dc29676">

### Google Map

1. **경로 표시**
2. **걸음 수 표시**
   ![경로 걸음 수 표시](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/f486c254-155c-4ae4-9d56-2c553b934d9f)

3. **사진 찍은 위치에 Marker 표시**
   ![걸음 수 표시](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/3a84912f-c0d3-4e9f-bdbc-7e0f71e88769)

### Firebase DB 구조

![DB1](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/3204aa8b-bf72-4f99-9d18-dc036b0bcc98)
![DB2](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/bfc48c60-c6b4-48cd-a377-8084015041f3)

## 🤖 YOLOv8 → TensorflowLite 모델

[사용한 데이터셋](https://universe.roboflow.com/projectverba/yolo-waste-detection)
epoch :100회
base : yolov8s.pt

#### 인식 가능한 labels

Aerosols, Aluminum can, Aluminum caps, Cardboard, Cellulose, Ceramic, Combined plastic, Container for household chemicals, Disposable tableware, Electronics, Foil, Furniture, Glass bottle, Iron utensils, Liquid, Metal shavings, Milk bottle, Organic, Paper bag, Paper cups, Paper shavings, Paper, Papier mache, Plastic bag, Plastic bottle, Plastic can, Plastic canister, Plastic caps, Plastic cup, Plastic shaker, Plastic shavings, Plastic toys, Postal packaging, Printing industry, Scrap metal, Stretch film, Tetra pack, Textile, Tin, Unknown plastic, Wood, Zip plastic bag
![Train에 사용된 사진](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/4859e5c8-5ce1-4d82-937f-7845b0f03bc5)

#### **학습과정(epoch100)**

- train 시작, epoch 1
  ![trainStart](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/2737f618-974f-4699-a7cb-7e82a7bf9e61)
- train 종료, epoch 100
  ![mAP](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/1bf1280e-7a6e-483a-b306-bd5808d38ff0)

#### **학습결과**

- mAP
  ![20231113_180038](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/c3f4be72-4dc7-44ee-a55a-adddefc8213a)
- epoch : 50
  ![epoch50](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/490d2fad-b326-4a12-9d09-63cb4fd1d7c3)
- epoch : 100
  ![epoch100](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/18075566-d604-4a96-af32-11532ad8c2a9)
- **train/box_loss** : 0.60062 -> 0.51776
- **train/cls_loss** : 0.31526 -> 0.28401
- **train/dfl_loss** : 1.0677 -> 1.0847
- **val/box_loss** : 1.2177 -> 1.2549
- **val/cls_loss** : 1.048 -> 1.1558
- **val/dfl_loss** : 1.4304 -> 1.7433


→ 검증 단계에서는 loss 증가 → **Overfitting 가능성** 또는 **데이터 분포 불균형** 추측  

---

## 📸 앱 테스트 결과

### 테스트 1
- 입력: 캔 이미지  
![캔사진](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/e4b851b8-04eb-48da-b9a1-8f5443daa03d)  
- 결과: 인식 성공  
![인식된 이미지](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/b511d056-21ac-4d05-89b5-b6d535da7828)  

### 테스트 2
- 입력: 봉투 이미지  
![봉투](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/56c743c7-fd0c-4a52-b981-d02a47bb4aab)  
- 결과: 인식 성공  
![인식된 이미지2](https://github.com/BOJ-ios/BalanceTeam/assets/44316764/1aea07be-e9d8-4452-b26e-130a4420bdc2)  


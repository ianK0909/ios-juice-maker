# 주스만들기 프로그램

: SeSAC 토이 프로젝트 - 주스 만들기 프로그램
> 
> 프로젝트 기간: 2023.12.04 ~ 2023.12.22

<table>
  <tr align="center">
    <th>Yuni</th>
    <th>이안</th>
  </tr>
  <tr align="center">
    <td><img src="https://avatars.githubusercontent.com/u/133867430?v=4" width="80"></td>
    <td><img src="" width="80"></td>
  </tr>
  <tr align="center">
    <td><a href="https://github.com/Jin0Yun">@Jin0Yun</a></td>
    <td><a href="https://github.com/ianK0909">@ianK0909</a></td>
  </tr>
</table>

## 구현내용

### Step 1: 주스 메이커 타입 정의

- FruitStore는 다음의 조건을 충족해야 합니다.
    - FruitStore가 관리하는 과일의 종류 : 딸기, 바나나, 파인애플, 키위, 망고
    - 각 과일의 초기 재고 : 10개
    - 각 과일의 수량 n개를 변경하는 기능이 있습니다.
- JuiceMaker 타입을 정의합니다.
    - FruitStore의 과일을 사용해 과일쥬스를 제조합니다.
        - 딸기쥬스 : 딸기 16개 소모
        - 바나나쥬스 : 바나나 2개 소모
        - 키위쥬스 : 키위 3개 소모
        - 파인애플 쥬스 : 파인애플 2개 소모
        - 딸바쥬스 : 딸기 10개 + 바나나 1개 소모
        - 망고 쥬스 : 망고 3개 소모
        - 망고키위 쥬스 : 망고 2개 + 키위 1개 소모
    - 과일의 재고가 부족하면 과일쥬스를 제조할 수 없습니다.
    - JuiceMaker는 FruitStore를 소유하고 있습니다.

### Step2: 초기화면 기능 구현

- '재고 수정' 버튼을 터치하면 '재고 추가' 화면으로 이동합니다.
- 각 주문 버튼 터치 시
    - 쥬스 재료의 재고가 있는 경우 : 쥬스 제조 후 `“*** 쥬스 나왔습니다! 맛있게 드세요!”` 얼럿 표시
    - 쥬스 재료의 재고가 없는 경우 : `“재료가 모자라요. 재고를 수정할까요?”` 얼럿 표시
        - ‘예' 선택시 재고수정 화면으로 이동
        - ‘아니오' 선택시 얼럿 닫기
    - 과일쥬스를 제조하여 과일의 재고가 변경되면 화면의 적절한 요소에 변경사항을 반영합니다.

### Step3: 재고 수정 기능 구현

- 화면 제목 '재고 추가' 및 '닫기' 버튼 구현
    - 닫기를 터치하면 이전화면으로 복귀
- 화면 진입시 과일의 현재 재고 수량 표시
- , + 를 통한 재고 수정
- iPhone 15 외에 다른 시뮬레이터에서도 UI가 정상적으로 보일 수 있도록 오토레이아웃 적용

## 프로젝트 핵심 경험
- 타입의 캡슐화/은닉화
- 내비게이션 바 및 버튼 아이템의 활용
- 얼럿 컨트롤러 활용
- Modality의 활용
- 과일 재고 데이터 전달 및 표시
- 오토레이아웃 적용해보기

## 폴더구조
```
📦 JuiceMaker
+-- 🗂 Controller
|    +-- 🗂 AppDelegate
|    +-- 🗂 SceneDelegate
|    +-- 🗂 OrderJuiceViewController
|  	 +-- 🗂 FruitInventoryViewController
+-- 🗂 Model
|    +-- 🗂 JuiceMaker
|    +-- 🗂 FruitStore
|    +-- 🗂 Fruit
|    +-- 🗂 Juice
|    +-- 🗂 JuiceMakerError
+-- 🗂 Extension
|    +-- 🗂 Alert
+-- 🗂 View
|    +-- 🗂 Main
|    +-- 🗂 Assets
|    +-- 🗂 LaunchScreen
```


  </tr>
</table>
  
## 트러블슈팅
- 레시피랑 과일을 enum을 사용하여 정의되어있는것은 struct로 변경
  -> SOLID의 OCP원칙(개방폐쇄원칙) ENUM으로 구현되어있으면 과일이 추가,변경에 따라 하나라도 변경되면 연쇄적으로 다 수정을 해줘야함 그걸 struct 로 구현하면 좀 더 유연하게 사용할수있음.

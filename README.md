# 🧃 주스만들기 프로그램

> SeSAC 토이 프로젝트3 - 과일 재고를 관리하고 신선한 쥬스를 만들어보세요!
> 
> 프로젝트 기간: 2023.12.04 ~ 2023.12.22
>
> 기여자: <td><a href="https://github.com/Jin0Yun">@Jin0Yun</a></td>, <td><a href="https://github.com/ianK0909">@ianK0909</a></td>
>
> 리뷰어: <td><a href="https://github.com/ryan-son">@ryan-son</a></td>

## 📱 시연영상

https://github.com/ianK0909/ios-juice-maker/assets/133867430/2af08f05-aef6-4f53-a208-08665c35a280

## 🏆 PR 모음
- <td><a href="https://github.com/tasty-code/ios-juice-maker/pull/116">STEP3</a></td>
- <td><a href="https://github.com/tasty-code/ios-juice-maker/pull/100">STEP2</a></td>
- <td><a href="https://github.com/tasty-code/ios-juice-maker/pull/83">STEP1</a></td>

## 📂 폴더구조
```
📦 JuiceMaker
+-- 🗂 Controller
|    +-- 🗂 AppDelegate
|    +-- 🗂 SceneDelegate
|    +-- 🗂 OrderJuiceViewController
|    +-- 🗂 FruitInventoryViewController
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

## 📝 프로젝트 핵심 경험
- 타입의 캡슐화/은닉화
- 내비게이션 바 및 버튼 아이템의 활용
- 얼럿 컨트롤러 활용
- Modality의 활용
- 과일 재고 데이터 전달 및 표시
- 오토레이아웃 적용해보기
    
## 🤔 트러블슈팅
- 레시피랑 과일을 enum을 사용하여 정의되어있는것은 struct로 변경
  -> SOLID의 OCP원칙(개방폐쇄원칙) ENUM으로 구현되어있으면 과일이 추가,변경에 따라 하나라도 변경되면 연쇄적으로 다 수정을 해줘야함 그걸 struct 로 구현하면 좀 더 유연하게 사용할수있음.

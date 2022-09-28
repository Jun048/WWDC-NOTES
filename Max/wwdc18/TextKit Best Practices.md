TextKit Best Practices
============================

1. TextKit 이란?

TextKit은 사용했던 다른 프레임워크와 조금 다르다

UIKIt및 AppKit의 텍스트 컨트롤은 TextKit 위에 구축된다 -> 레이블, 텍스트 필드 또는 텍스트 보기를 사용한 적이 있다면 실제로 TextKit을 사용한 것임

TextKit은 Core Text, Core Graphics과 같은 기술을 결합하여 앱이 텍스트를 표시하는 것을 간단하고 매끄럽게 만든다


![TextKit](https://user-images.githubusercontent.com/111475243/191688026-fc6e5e85-f101-4872-a589-4dcc697c2954.png)

2. 올바른 컨트롤 선택

다양한 유형의 텍스트에 대해 적절한 텍스트 컨트롤을 선택해야 한다

- UIKit 선택 경로


![ui](https://user-images.githubusercontent.com/111475243/192683784-a4442c88-3614-4dae-b621-c86969f3cac9.png)


- AppKit 선택 경로


![appkit](https://user-images.githubusercontent.com/111475243/192684118-fd78b3ae-82bc-4745-879a-cd3ef0dc066d.png)



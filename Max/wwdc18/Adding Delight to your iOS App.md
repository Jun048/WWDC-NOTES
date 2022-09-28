Adding Delight to your iOS App
====================

1. 외부 디스플레이 지원




외부 디스플레이용 어플을 설계할떄 고려해야 할 몇가지 핵심 사항

- 아이폰은 개인용이라 디스플레이에 표시하는 정보의 종류를 비공개로 해야 한다. 반면에 외부 디스플레이는 거실의 TV등과 같이 많은 사람들이 볼 수 있는 환경에 위치한다 -> 여기 표시된 정보는 공개된 것으로 가정해야 한다

- 아이폰 및 아이패드에 내장된 디스플레이는 대화형이지만 외부 디스플레이는 그렇지 않다. 따라서 외부 디스플레이에 UI요소 또는 기타 상호 작용 가능한 컨트롤을 표시하지 않아야 한다


외부 디스플레이 지원 방법

![1](https://user-images.githubusercontent.com/111475243/191682035-048ac24e-a251-45ae-ab52-d29b912087e4.png)

- 연결 처리

연결 설정 방법 : 

  ```
  if let externalScreen = UIScreen.screens.last {
  externalWindow = UIWindow()
  externalWindow.screen = externalScreen
  configureExternalWindow(externalWindow)
  externalWindow.isHidden = false
} 
```

연결 끊김 받을때 :

 ```
 externalWindow.isHidden = true
 externalWindow = nil
 ```


앱 동작 변경 : 

```
// In our Collection view selection callback
if inSingleDisplayMode {
    photoViewController.photo = photo
    navigationController?.pushViewController(photoViewController, animated: true)
   } else {
     showOnExternalDisplay(photo)
 }
```

 
 2. 레이아웃 기반 UI

```
class MyView: UIView { 
  // ... 
  let coolView = CoolView()
  var feelingCool = true {         // UI에 영향을 주는 상태 찾기 및 추적
    didSet { 
      setNeedsLayout()             // 상태가 setNeedsLayout()과 함께 변할때 더티 레이아웃?
    }
  }

  override func layoutSubviews() { 
    super.layoutSubviews()
    coolView.isHidden = !feelingCool   // 업데이트
  }
}
```

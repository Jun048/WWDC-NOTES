Using Grouped Notifications

https://developer.apple.com/videos/play/wwdc2018/711/








![11](https://user-images.githubusercontent.com/111475243/191216759-526ca3fe-6063-41d6-8864-ffaece06dfce.jpeg)

iOS 11까지는 notification들이 시간순서대로 플랫폼상관없이 배치되었고,  그렇기때문에 특정 notification을 찾는게 힘들 수 있다. 

업데이트 후 앱별로 그룹화

![33](https://user-images.githubusercontent.com/111475243/191217790-5d469cb7-f399-4af9-80c0-196dea5f6eab.jpeg)




- notification이 도착했을때, thread identifier가 없다면 app group과 그룹핑

  만약 thread identifier와 함께 왔다면, 같은 thread ID를 갖는 같은 앱으로부터 온 notification과 같이 그룹핑됨.

![다운로드](https://user-images.githubusercontent.com/111475243/191398443-ef754ee8-ade2-40e8-b4ea-ac11814a1d9a.jpeg)


- 하나의 앱은 여러개의 그룹을 가질 수 있다.

![ss](https://user-images.githubusercontent.com/111475243/191398768-7f70490b-5d12-466e-ad7e-e6b48ea1b900.jpeg)


ex) 메시지 앱

하나의 메시지앱에서, 사람별로 나누어져서 그룹 형성


![다운로드 (1)](https://user-images.githubusercontent.com/111475243/191399029-b0baef96-1975-4223-a48b-437b9486a249.jpeg)


시스템 설정에서 그룹 설정을 할 수 있다.

grouped notifications에 대한 3가지 세팅 (설정 > 해당 앱으로 이동 > 알림 > 알림 그룹 설정)

- 자동 : 기본적인 설정으로 각 앱에 대해 smart notification groups를 가질 수 있다. title, content, what it say, 메일 앱의 경우 sender(보낸 사람)기준으로 한다.
- 앱별로 정리 : 기본적으로 모든 notification은 title, content, sender 별로 구분되지 않고, 앱별로 단일 그룹으로 누적.
- 끔 : 각 앱에 대한 각 notification이 개별적으로 보여지는 ios12 이전의 방식


notification content extension

기존 notification보다 더 다양한 정보들을 제공

설정하는 방법 : target을 새로 만들고 UNNotificationContentExtension을 채택



![nce](https://user-images.githubusercontent.com/111475243/192700499-365d585d-f4eb-499b-90c8-18402e3ff61d.jpeg)



![333](https://user-images.githubusercontent.com/111475243/191634797-4e733a15-83b5-458d-90ea-49c1d6a928dc.jpeg)




action을 설정하는 방법

- action을 만들고 그 액션들을 담는 identifier를 가지는 category를 만든다 -> catgory를 set해준다

![ㅁㅁ](https://user-images.githubusercontent.com/111475243/191634954-34ce1d27-ccbf-4014-b2b0-89a35bc7f423.jpeg)

![set](https://user-images.githubusercontent.com/111475243/191635092-378b406c-e916-42b0-bd4a-8d081143391a.jpeg)




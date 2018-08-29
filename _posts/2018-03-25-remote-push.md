---
layout: post
title: push
---

### 로컬 작업 내역을 원격 저장소에 올리기: push

로컬 저장소에서 진행했던 많은 commit들이 있을 것이다. 이러한 commit들을 협업 등을 위해 원격 저장소에 업로드 해야한다. 그때 push를 사용한다.

원격 저장소에 로컬 저장소의 브랜치와 같은 이름의 브랜치가 있다면 해당 브랜치를 변경하고 없다면 새 브랜치를 원격 저장소에 만든다. 이 때, 같은 이름의 브랜치가 있는데 서로 내역이 다르다면 푸시가 거부된다.



이제 push를 해보면, 로컬의 모든 브랜치를 push하는 --all 옵션을 주어 push 한다.

```
git push origin --all
```

![img](https://lh5.googleusercontent.com/4LObOtfQLT0DXOVB6y5LOxMB_lt5qfo_rxxg9dpgHKctNLTVffttAQ3RfeE3Oiqfoqz_9lLiA1vtxRFuYXuFICLEKOD-Tzsc1LwfVjj17350LcZXwyQMr3Z4sxtNfbrvvphW65KqkUI)



![img](https://lh5.googleusercontent.com/2quXIe6kK10olAobts8-hNm0v9xZS7XMjPx0eSW5LiIBYpLFnwnd-UNlA9FjFQ6RrCjkVZrb3hgHGttfyWXPhmqvGtbAbdZU1siqCo4pSuHoRgpW5gJ--zKzLRq_Unw1_etKKnH0RKw)

![img](https://lh4.googleusercontent.com/ffcvThOgQHwt2aBFxefO6UDHPtXk5bc8anfWBah1EHCGSnvN2ddLivnYpIoZhUK5ZRbHs045qrUsQGCVg2I92IIkY696th41UDjrFtbrJwJMDCesQmElYTe4gdHopROtqVEf1X8POjM)

master와 hotfix 브랜치 모두 원격 저장소에 올라간 것을 볼 수 있다.

---

#### push 에러

원격 저장소로 push할 때, 같은 이름의 브랜치가 존재하지만 서로의 내역이 다르다면 push 할 수 없다. 

예를 들어 내가 로컬 저장소에서 작업하는 도중 다른 협업자가 원격 저장소의 내용을 변경했을 경우이다. 이 경우 push를 하면 error가 뜨기 때문에 fetch 혹은 pull을 하여 원격 저장소 내용을 로컬 저장소로 가져온 후 적절히 수정 및 commit 한 후 push하여 원격 저장소에 다시 업로드 하여야 한다.

아래는 이러한 경우에 push error 메세지이다.

![img](https://lh3.googleusercontent.com/0V2nLnDH7tM04nWXM8_hGUKp-NMk_wYsVKj8C5GSjx940UI41X4nm6fyvwqO_PZcT5g4p2eh08FtOdMv4uYwuxLMsrd5OIC-oypZJpXIjlnuFZQ4zN_Jc0kg8Rpi6yAY8S7FSU01rsA)

이 때의 문제 해결방법인 fetch 및 pull은 다음 글에 나와있다.
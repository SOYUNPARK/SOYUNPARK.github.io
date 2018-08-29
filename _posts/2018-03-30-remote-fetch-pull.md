---
layout: post
title: fetch and pull
---

### 원격 저장소와 로컬 저장소의 간격 메꾸기: fetch와 pull

앞에서 설명 했듯이, 로컬 repo에서 작업하는 도중 다른 협업자가 원격 repo를 변경하면 push가 불가하다. 이 때 사용하는 명령어가 바로 fetch 혹은 pull이다.

fetch와 pull 모두 단어 뜻 그대로, 원격 repo를 로컬 repo로 끌어오는 명령어이다. 우선 pull은

* 현재 브랜치에 원격 repo의 정보를 끌어와, 자동으로 병합한다. 
* 즉, fetch와 merge를 수행한다. 

fetch는

* 현재 브랜치에 존재하지 않는 commit들을 로컬 repo에 끌어온다.
* 하지만 현재 브랜치와 병합하지 않고,  사용자가 수동으로 커밋들을 비교하며 merge해야 한다.



fetch를 사용하기 위해 먼저 원격 repo의 내용을 GitHib 웹사이트에서 수정 및 commit하였다. 후에 로컬 repo에서 push를 해보았다.

```
git push origin hotfix
```

![img](https://lh3.googleusercontent.com/0V2nLnDH7tM04nWXM8_hGUKp-NMk_wYsVKj8C5GSjx940UI41X4nm6fyvwqO_PZcT5g4p2eh08FtOdMv4uYwuxLMsrd5OIC-oypZJpXIjlnuFZQ4zN_Jc0kg8Rpi6yAY8S7FSU01rsA)

push하려는 브랜치의 변경 내역이 일치하지 않기 때문에 rejected 의 메세지와 pull을 하라는 힌트 메세지가 출력된다.

pull을 하지 않고 fetch를 사용하여 원격 repo 정보를 가져온다.

```
git fetch
```

`git branch`명령에 -a옵션을 주어 원격, 로컬 repo의 모든 브랜치를 나타낸다.

```
git branch -a
```

아래 그림을 보면 로컬 브랜치 hotfix, master와 원격 브랜치 ogrigin/hotfix, origin/master를 볼 수 있다. 

![branch](C:\Users\Software\Desktop\soyunpark.github.io\_posts\branch.PNG)

이제 작업중인 hotfix 브랜치에 origin/hotfix를 병합해보자.

우측 파란 글씨를 확인하여 hotfix 브랜치에서 merge한다.

```
git merge origin/hotfix
```

![merge](C:\Users\Software\Desktop\soyunpark.github.io\_posts\fetch-merge.PNG)

앞서 로컬 repo에서의 merge 예제와 마찬가지로 충돌을 해결하여준다.



`diff`명령어로 로컬 repo 브랜치와 원격 repo 브랜치 사이에 차이점을 출력한다.

```
git diff
```

![img](https://lh4.googleusercontent.com/ntkIIAvMq5GGOh50XN_Az_MC_UEQvlsKP8EZNSt-cOwtIHpUnQsa6IIxKQP5bxBlmuVUU-0YKzhs0NpZV_EhJly6lNul9jgQvcu98iQeTr-mWW7UKKC6gnR8IJvjcPIK6S41BheJs1o)

만약 git pull로 원격 repo를 끌어왔다면, 이러한 과정 없이 자동으로 페치 및 병합을 수행하기 때문에 어떤 변경 사항이 있는지 알기가 어렵다.

merge 시 충돌 발생 이후, 수정 및 commit하기 전까지 우측 상단에 작업중인 브랜치를 나타내는 파란 글씨는 (hotfix|MERGING) 상태이다. 

충돌이 발생한 파일을 수정 및 commit후에 원격 repo로 push를 하여준다.

```
git push origin hotfix
```

![img](https://lh3.googleusercontent.com/81M2K3YaL-W62DhnSol1D77wvMlKAvNAOIPGFSb65Ge5L9VPz9nB0_P_ZEOIzrl7n5rfPzzDGIdlpLnQkG8ut6Ni2WizICXvMeT0kG9xHRpswurCkZ7mC8kUjf-pwk326y2hJny76VA)



원격 repo에 알맞게 push되었는지 확인한다.

![img](https://lh5.googleusercontent.com/tXE7Tf_YdLzi4PQYXt9DcjZRvGSaMkbXvPs2UoyQRPfxnIaYUbi2Cb2NsHDeS_aIBNTtzUo9vMV8fznubA_80dZdVJbM931ue0MMtMtudZmAv3Jl9NsZ4PMG5v0UaWfofDOiDQvizrQ)

---

#### merge 에러

```
fatal: refusing to merge unrelated histories
```

merge 하려는 두 브랜치의 history가 unrelated하다는 에러

[해결]

(해결법...은 아닌 것 같지만)

`git pull origin master --allow-unrelated-histories`로 강제 pull한다.
---
layout: post
title: 브랜치 생성 및 이동
---



### 새로운 브랜치 생성 및 이동

브랜치 목록보기

```
git branch
```

브랜치 생성

```
git branch "브랜치명"
```

작업중인 브랜치 변경

```
git checkout "브랜치명"
```

![img](https://lh4.googleusercontent.com/-Fwpaj3dRkbzc7BDbpIczdtLUd3flEKtXsNtq4abeUMPddfm2WNhxahNtzLiPGNhWItq6t6dXTEQlDXr2P7AvxrcLRQH5o1MC9O2d6BO2VX-T8nrEfQq6hvFqcvBkSC_Ex1aDk3F1XA)

*hotfix* 브랜치를 생성 후 *hotfix*에서 작업하기 위해 checkout 명령어로 브랜치를 변경해주었다. 우측 하늘색 글씨의 괄호안에 문자가 현재 작업중인 브랜치를 나타낸다.

`git checkout hotfix`명령어 후에 현재 작업중인 브랜치가 *hotfix*로 바뀐걸 알 수있다.

각 브랜치는 서로 영향을 주지 않기 때문에 *hotfix*브랜치에서 수정을 하여도 *master* 브랜치에 영향을 끼치지 않는다. 이를 알기 위해 *hotfix* 브랜치에서 `hello.py`를 수정 하였다.

![img](https://lh3.googleusercontent.com/7VPR2I59z3fG_TP1W8qdsg_x_Mf47sEjgAFMbLg5llTcCUef6NiyBP2lBhH-ihed-zwHyo_X6IxLL2hYRZNP7PAAb3WM5xQ6Whvjb67OKX-gtJTl9ro3YWPsQK1eAznEs7xtpJRvHyo)

기존의 `Hello World!`의 출력 이후에 `Tell Your World~`를 출력하는 코드를 삽입하였다. 이제 변경사항을 커밋할 차례이다.



이전 커밋과 마찬가지로 `git add` 명령어를 사용하여 repository에게 변경사항 제출 후 커밋을 진행한다.

![img](https://lh5.googleusercontent.com/fKAWfNZpkro_uqJP07y0iwM-liVFcwrUvhLHh9fvw6EfV3swAuipsEpv2gKlxtadiDZvxDhvgLhEfReCr_AHKlT2aV2IML3KFM1sNcvBid7CskLBZeuo5xlsgA1qAgAGCzUPFbqa-WU)

`warning: LF will be replaced by CRLF in hello.py. The file will have its original line endings in your working directory.`에러를 무시하기 위해 그림 마지막에 보이는 명령어를 true로 실행하였다.

```
git config core.autocrlf true
```



---

### 브랜치의 독립성 확인

각 브랜치의 독립성을 확인하기 위해 hotfix 브랜치에서 hello.py를 수정했었다.

이제 master브랜치로 다시 돌아와서 동일한 hello.py를 수정한다.

```python
print("Hello World!")
print("			Bye my world----!")
```

![img](https://lh5.googleusercontent.com/355qI6p8VlWu9u0mN0hfqW_f6TZYiXfV2DiQm5HAL27YDbSYHkFRXdzNwmomxhFBe3zJvDtqx5Ex3ER7nwFT-VmE5bYZAChWA8FmoMi7v9fitNz-IvePy4c1MYD4R6Ewb4DjEN6yxnE)

올바르게 동작하는지 확인 하였으면 커밋을 진행한다.

![img](https://lh3.googleusercontent.com/vV0erkG0jOXHI8M7lu0DCwIDs1Xf4Hx2eU1r1r9k5hhABe57vVpnLBVRqMDDHbFCMIzGImlsS3Ri5gFHR6vDkPdxk7ORrGQ6RJ_yWMKg46GDUxJ1VQRw89PlClEy_2kVIQlsOq4VuF0)



이제 브랜치 병합을 하려 한다. 

다음 게시 글에서 hotfix 브랜치의 hello.py와

```python
% hello.py
print("Hello World!")
print("		Tell Your World~")
```

master브랜치의 hello.py

```python
% hello.py
print("Hello World!")
print("			Bye my world----!")
```

`git merge`를 사용하여 병합해보겠다.
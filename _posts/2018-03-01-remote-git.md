---
layout: post
title: 원격 저장소와 Git
---

### GitHub

앞서 Git에 대해 공부했다. 다음으로는 GitHub에 대해 공부할 것이다.

[GitHub](https://ko.wikipedia.org/wiki/%EA%B9%83%ED%97%88%EB%B8%8C)란  대표적인 무료 Git 저장소이며 Git 호스팅 기능 덕분에 현재 가장 강력한 협업 플랫폼이다.

홈페이지에 나와있는 GitHub의 장점으로는

+ World’s largest open source community
+ Great collaboration starts with communication
+ Friction-less development across teams
+ Do more with powerful integrations

가 있다고 한다.

---

### 원격 저장소에서의 Git

VCS의 사용 목적은 다른 사람과의 협업을 위해 분산 버전 관리를 하기 위함이다. 이를 효율적으로 도와 주는 원격 저장소 역할에 해당하는 것이 GitHub이다.

즉, 

+ 원격 저장소의 내용을 로컬 저장소로 가져오거나, 
+ 로컬 저장소를 원격 저장소와 연결하고 보내거나, 
+ 수정된 내역을 확인하고 병합하는 과정 등을 GitHub를 사용하여 진행한다.

아래는 원격 저장소에서 사용하는 주된 명령어들이다.

| 명령어     | 기능                                                         |
| :--------- | ------------------------------------------------------------ |
| git clone  | 원격 저장소의 모든 내용을 로컬 저장소로 복사                 |
| git remote | 로컬 저장소를 특정 원격 저장소와 연결                        |
| git push   | 로컬 저장소의 내용을 보내거나 로컬 저장소의 변경 사항을 원격 저장소로 보냄 |
| git fetch  | 로컬 저장소와 원격 저장소의 변경 사항이 다를 때 이를 비교 대조하고 gir merge명령어와 함께 최신 데이터를 반영하거나 충돌 문제 등을 해결 |
| git pull   | git remote 명령을 통해 서로 연결된 원격 저장소의 최신 내용을 로컬 저장소로 가져오면서 병합, git push와 반대 성격을 갖음 |


---
layout: post
title: 로컬 저장소와 원격 저장소 연결하기
---

### 로컬 저장소와 원격 저장소 연결하기: remote

현재 내 컴퓨터의 로컬 저장소를 원격 저장소와 연결하고 싶다면 git remote 명령어를 사용한다.



먼저 GitHub 웹 사이트 내에 빈 원격 저장소를 생성한 뒤, 로컬 저장소로 이동한다.

원격 저장소의 HTTPS clone URL 주소를 복사한 후 remote 명령어를 실행한다.

```
git remote add 저장소별칭 https://github.com/사용자이름/원격저장소이름.git
```

![img](https://lh6.googleusercontent.com/Td2Ls6yuS1gxeGoyjxfGZlXgVDI2eapGwZxH1wZH6_7RrId689Ccbl706gyW9pKUjQO5iSV17Vc2GDcsy5tR4Ty6RK8DHvFDr3MA9pmayPKcczoyvnG-GCUEhRyfV9lijTUvNyDzE4g)

위의 명령으로 로컬 저장소와 원격 저장소를 연결했다면 아래 명령으로 확인 가능하다.

```
git remote -v
```

![img](https://lh3.googleusercontent.com/9gUTP9c5j74p0tTZrcZaiSSFbsYhkQQmsEqdtsG_dspfK3BRbC95ASauqyLDPv4iWDBc3XUB3n0y6jnwPdkRJrGTKx9x8zc0Vq_9ZQPt3EYtubADzLbUx3T2ADTGo-cRn_v7fQo7EIA)



만약 원격 저장소를 삭제해야 한다면 아래 명령을 실행한다.

```
git remote rm <remote-name>
```




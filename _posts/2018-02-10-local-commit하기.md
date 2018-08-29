---
layout: post
title: commit하기
---



### 파일 커밋하기: git add와 git commit



`Hello World`를 출력하는 프로그램을 작성 후 커밋 해보았다.

우선, *git bash*에서 vim을 사용해 python파일을 생성하였다.

```python
% hello.py
print("Hello World")
```

생성한 python 파일이 정상 동작 하는지 실행 후 

repository의 상태를 알기 위해 `git status` 실행

```
git status
```



![creat_python_add](C:\Users\Software\Desktop\soyunpark.github.io\_posts\creat_python_add.PNG)

`changes not staged for commit`라는 메세지가 뜨며 커밋할 파일들을  `git add`를 사용하여 수정된 파일들을 repository에 제출한다.

```
git add hello.py
```

`git add "파일명"`으로 하나씩 add가 가능하지만 

```
git add .
git add -A
```

을 사용하여 새로 생성된 파일, 수정된 파일, 삭제된 파일 모두를 repository에 제출하여 준다. 



add 후 다시 `git status`를 해보면 `changes to be commited`라는 메세지라 출력된다. 이제 커밋을 실행한다. 

![add](C:\Users\Software\Desktop\soyunpark.github.io\_posts\add.png)

```
git commit
```

아무 옵션도 주지 않으면 커밋 메세지를 입력하도록 에디터가 실행된다. notepad++가 실행되었다. 

`create "Hello World" program` 이라는 커밋 메세지를 작성하였다.

![img](https://lh5.googleusercontent.com/wy9qrcuadYA92s24bGunwaU8Fa-ff3hKOqoQz1u6bWbfnczCKRiejr8UzYLvQrNABRq0vtcaONjuMXhTi1vUwtJt1aKQ0mGNLmkR1GfKp6j-8OCexQFhs9nVKaP5u85BQKpUVg6CSw4)

에디터 내의 커밋내용 수정 및 저장 후 에디터를 종료시키면 아래처럼, 완료된 커밋에대한 정보를 띄우며 커밋에 성공하게 된다.

![img](https://lh3.googleusercontent.com/ZMggMZCjWjWW1c529fQjTbBHr8aZCKdHTJE5yKcb5zT3rQCykle1sK02cAEtJfQ7pSKJIWlKCBFwkBVhJm63Xkf9ah_zFP0AZC2BLYy2J92HPD4oJ0ZT8bmAtaHFEjWZ5-FftCvs1Iw)

`git commit`명령어만 입력하여도 에디터를 사용하여 상세한 커밋메세지 입력이 가능하지만 번거롭기 때문에 메세지 입력을 동시에 해주는 아래 옵션으로 주로 실행한다.

```
git commit -m "커밋 메세지 입력"
```

전체 파일 모두를 커밋하려면

```
git commit -a
```










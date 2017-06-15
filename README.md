# WIZnet GitFlow

해당 레퍼지토리는 WIZnet의 버전관리체계(Version Control System, VCS)를 정의하고 교육하기 위한 용도이다.

<br>

## GitFlow
WIZnet의 VCS는 GitFlow라는 브랜치 전략을 따른다.

GitFlow 및 Git에 대해서는 아래 링크를 참조.

 - [Git for Eng.](https://git-scm.com/documentation)
 - [Git for Kor.](https://opentutorials.org/course/2708)
 - [GitFlow for Eng.](https://danielkummer.github.io/git-flow-cheatsheet/)
 - [GitFlow for Kor.](https://gist.github.com/ihoneymon/a28138ee5309c73e94f9)

---

## WIZnet의 룰

### Branch 룰
기본적으로 GitFlow를 따르나,
각 상황별 사용해야할 Branch(GitFlow에서 사용되는)는 아래와 같다.

|상황(용도)|레퍼지토리|
|:--:|:--:|
|공개|master|
|개발 - 일반적인 수정|develop|
|버그수정(긴급)|hotfix|
|새로운 기능 추가|feature|
|Develop에서 Master로 공개할 때|release|

위 테이블처럼 각 상황에 맞게 GitFlow를 운용해야 한다.

<br>

추가로, feature, hotfix, release의 이름을 지정할 때는 아래의 규칙을 따른다.<br>

 - **feature & hotfix**
 
|구분|접두어|예시|
|:--:|:--:|:--:|
|칩 레벨|칩명칭_기능명|W5500_WIZCHIP_READ|
|어플리케이션|어플명칭_기능명|DHCP_discover|
|일반|Common_기능명|Common_socket|
 
    * 함수가 아닌 전역변수의 수정이라면, 칩/어플/일반만 구분할 것.
 <br>
 
 - **release**
 
|구분|번호|예시|
|:--:|:--:|:--:|
|버그 수정|오른쪽(Maintenance)|0.0.1 -> 0.0.2|
|기능 추가|가운데(Minor)|0.0.1 -> 0.1.0|
|대폭 업데이트|왼쪽(Major)|0.0.1 -> 1.0.0|
    
    * 대폭 업데이트의 경우, 기능 추가로 인해 Minor가 올림되는 경우도 포함.
<br>

### Commit 룰 
Commit은 GitHub의 Issue를 기준으로 한다.
GitHub Repository에 Issue를 남기면, '#'과 함께 번호가 할당된다. ex) #23

이 때, 할당 된 번호를 Commit에 사용한다.

    ex1) Bug Fixed #44
    ex2) Modified #189
    ex3) Add #482
    ex4) Update #586

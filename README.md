 WIZnet GitFlow

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
<br>

## Process
#### Issue 발생
 - 어떠한 이슈이든 코드 수정이 필요하다면, 해당 레퍼지토리의 [Issues](https://github.com/Wiznet/WIZ_GitFlow/issues)에 등록한다.
 - (고객이 직접 Issue를 남기지 않았다면) Forum, 통화 등 모든 상황에 대해서 담당자가 직접 등록한다. (Template은 #1 참조)
 - 코드 수정 담당자가 별도로 있다면, Issue를 등록한 뒤 초대하여 Issue에 대응하도록 한다.
#### 코드 수정
 - Issue에 해당하는 내용에 대해서만 수정한다. (코드 관리 차원)
#### 레퍼지토리 업데이트
 - 수정한 코드 내용을 GitFlow 방식으로, 다음 절의 WIZnet 룰을 따라 레퍼지토리를 업데이트 한다.
 - 이 때, 반드시 Commit Message에 이슈번호를 사용한다. (WIZnet Rules 참조)
#### Issue 답변
 - 해당 Issue에 업데이트 결과에 대한 답변을 한다. (Template은 [#1](https://github.com/Wiznet/WIZ_GitFlow/issues/1) 참조)
#### Issue 닫기
 - Issue에 답변을 달고 최종 처리되었다면, 해당 Issue를 Close한다.

---
<br>

## WIZnet Rules

### Branch Rules
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
|주요 업데이트|왼쪽(Major)|0.0.1 -> 1.0.0|
     
<br>

### Commit Rules 
Commit은 GitHub의 Issue를 기준으로 한다.

GitHub Repository에 Issue를 남기면, '#'과 함께 번호가 할당된다. ex) [#1](https://github.com/Wiznet/WIZ_GitFlow/issues/1)

이 때, 할당 된 번호를 Commit에 사용한다.

    ex1) Bug Fixed #1
    ex2) Modified #189
    ex3) Add #482
    ex4) Update #586

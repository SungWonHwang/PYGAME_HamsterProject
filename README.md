# PYGAME - Hamster Project

웹파이선 TERM-PROJECT

주제 : 시간이 멈추는 슈팅게임 제작하기<br>

## 1. 주제선정 이유 및 공부할 점<br>
Pygame을 이용한 슈팅 게임을 구현. <br>
파이썬에서 어떠한 방식으로 Pygame 라이브러리가 사용되는지와 구동에 사용되는 함수들, 구현 방식을 개발 및 공부한다.<br>
게임의 기본이 되는 2D 슈팅 게임을 구현하며 장애물, 아이템, 조작, 공격 등의 개발 과정을 경험한다.<br>

## 2. 주제설명
<햄스터 프로젝트> - Hamster Project<br>
시간이 멈추는 2D 슈팅 게임<br>
#### 게임 설명: <br>
지구 최강의 햄스터를 뽑는 햄스터 프로젝트! <br>
우승을 한 햄스터는 우주햄스터로서 우주선에 탑승할 수 있는 기회가 주어집니다. <br>
어려서부터 우주선을 타는 것이 꿈이었던 햄스터는 이 프로젝트에 참가하게 되는데... <br>
게임을 클리어하여 우주로 가고 싶은 햄스터의 꿈을 이루세요!<br>

#### 조작법:(*필요에 따라 변경가능)<br>
방향키 : 상하좌우 <br>
ESC: 일시정지 <br>
장애물 : 로봇햄스터, 톱밥함정 <br>
아이템 : 해바라기씨<br>

#### 게임방법:
(1) 플레이어는 방향키로 햄스터를 조작합니다.<br>
(2) 스페이스를 누르면 일시정지를 할 수 있습니다.<br>
(3) 햄스터의 조작을 멈추면 게임의 모든 시간이 멈춥니다.<br>
(4) 햄스터는 레이저를 이용하여 자동으로 공격합니다. <br>
(5) 장애물을 제거하고 아이템을 먹으세요.<br>

#### 세부설명:
(1) 플레이어는 레이저를 이용해 로봇햄스터를 공격. 레이저를 맞으면 로봇 햄스터 사라짐.<br>
(2) 로봇 햄스터에서 공격을 받을시 게임 오버. (*게임의 난이도 및 재미에 따라 변경 가능성 있음)<br>
(3) 톱밥 함정에 빠지면 게임 오버.<br>
(4) 해바라기씨를 먹으면 점수 상승.<br>
(5) 일정 거리 돌파마다 점수 상승. (6) 일정 거리가 넘어가면 게임 오버시 Clear 영상이 뜸.<br>
(7) 일정 거리 이하에서 게임 오버시 Fail 영상이 뜸.<br>
(8) 일정 거리는 게임 화면에서 나오는 배경의 변화로 알 수 있음.<br>

## 3. 구현 내용<br>
#### <메인 화면> <br>
startButton(마우스로 클릭시 게임 시작)<br>
settingButton(음악 on/off, 간단 설명)<br>
#### <레벨 구현> <br>
레벨 변화는 배경화면의 변화로 구현. 게임의 난이도가 달라짐 (장애물의 갯수 및 속도 변화)<br>
특정한 레벨 표시는 없음, 일정 거리 도달시 자동으로 난이도 변화.<br>
#### <플레이어 움직임> <br>
방향키 입력 받을시 플레이 화면 내에서 등속으로 캐릭터 움직임 <br>
#### <공격> <br>
playerAttack(플레이어가 계속해서 일정 간격으로 레이저 발사) <br>
objectAttack(장애물이 계속해서 일정 간격으로 공격 발사) <br>
sawdustAttack(플레이어가 톱밥에 닿을시 게임 오버)<br>
#### <점수 구현> <br>
eatSunflower(해바라기씨 먹을시 5점 추가)<br>
runDistance(일정 거리 돌파시 거리에 따라 점수 추가. ex. +10, +20, +30)<br>
#### <일시정지> <br>
escButton(esc버튼을 입력받으면 게임 정지/다시 누르면 게임 재시작)<br>
#### <게임 오버 및 클리어 > <br>
장애물에게 닿을시/ 공격 받을 시 게임 오버<br>
게임 오버 화면은 총 2가지로 구성.<br>
(게임 오버 - 우주선 배경 이전 게임 오버 / 게임 클리어-우주선 배경 도달 이후 게임 오버)<br>

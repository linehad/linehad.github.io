# 게임명 : 랜덤 탄막 프로젝트
- 한 문장으로 말하면 : 운빨 망겜 슈팅게임

# [ 목차 ]
#### 1. [컨셉](#탄막)
#### 2. [관련 이미지와 동영상](#2)
#### 3. [대표 이미지](#3)
#### 4. [컨셉과 대표이미지 기반 작품 묘사](#4)
#### 5. [랜덤 탄막 프로젝트의 구성 요소](#5)
#### 6. [게임 시나리오](#6)
#### 7. [게임 시스템 디자인](#7)
  1. [게임 오브젝트 분해(구성 요소 분석)](#7-1)
  2. [파라미터(속성) 뽑아 보기](#7-2)
  3. [행동 뽑아 보기](#7-3)
  4. [상태 뽑아 보기](#7-4)
  5. [게임의 규칙](#7-5)
  6. [게임에서 사용될 공식](#7-6)
#### 8. [개발 요구사항& 흐름도](#8)
  1. [요구사항(6주차)](#8-1)
  2. [요구사항(1년차)](#8-2)
  3. [키보드 이벤트에 대한 흐름도](#8-3)
  4. [용어정리](#8-4)
#### 9. [개발 작업 일정](#9)
#### 10-1. [1주차 작업 결과](files/w01/w01.md)
#### 10-2. [2주차 작업 결과](files/w01/w02.md)
#### 10-3. [3주차 작업 결과](files/w01/w03.md)
#### 10-4. [4주차 작업 결과](files/w01/w04.md)
#### 10-5. [5주차 작업 결과](files/w01/w05.md)
#### 10-6. [6주차 작업 결과](files/w01/w06.md)

## 메인컨셉 : 탄막<a name='탄막'></a>

- 종 스크롤 형식의 탄막 슈팅게임을 만들 예정 1945나 동방 프로젝트와 같은 보스전을 포함함
- 난이도가 너무 어려우면 플레이어들이 흥미를 잃기 때문에 다른 부분에서 재미를 보완할 예정
- 장르 : 탄막, 슈팅

### 서브 컨셉 1 : 단순함

- 복잡한 게임이 아닌 단순한 게임을 만들어서 구현을 간편하게 하고 중독성 있게 함

### 서브 컨셉 2 : 패턴

- 랜덤이 아닌 정해진 패턴에 따라서 탄막이 쏘아지며 탄막게임에 익숙하지 않더라도 하다보면 공략이 보이게끔 함

### 서브 컨셉 3 : 벽

- 예전 모바일 게임 드래곤 플라이트를 참고하여 위에서 내려오는 탄막 뿐만 아닌 일정 데미지를 받으면 사라지는 오브젝트 제작
- 벽은 부서지는 벽과 안 부서지는 벽이 존재하며 벽을 빠르게 통과 후 탄막을 피해야함

### 서브 컨셉 4 : 강화

- 난이도를 낮추었음에도 어려움이 있을 수 있기 때문에 보스전이후 플레이어를 강화하여 조금 더 쉽게 다음 보스를 클리어 할 수 있게끔 함

### 서브 컨셉 5 : 뽑기(가챠)

- 강화를 할 때 난이도가 너무 낮아지는 것을 방지하기 위하여 강화 시스템중 뽑기를 추가할 것이며 잘못 뽑게 될 시 오히려 난이도가 어려워지게 끔 하여 재미를 부여함

<br><br>

# [관련 이미지 & 동영상]<a name='2'></a>

- 이미지1  
  <img src="https://user-images.githubusercontent.com/91234912/134452656-442e6582-f0bb-44f6-80ea-14b49b2cc314.png" width="50%">
  
### 1945

최초로 영감을 받은 게임은 1945이며 고전적인 탄막 슈팅게임입니다.<br>
스테이지마다 보스가 존재하며 보스를 격파하는게 목표입니다.<br>
탄막슈팅게임에 관심이 있지만 너무 어려워서 재밌게 하지 못했는데 다른 종류의 기믹들을 넣어서 난이도를 맞추고 초보자와 숙련자 모두<br>
재미있게 플레이 할 수 있게 만드는게 목표입니다. UI는 상단의 목숨이나 점수등 1945와 비슷하게 만들어 질 것 같습니다.<br>

  
- 이미지2  
  <img src="https://user-images.githubusercontent.com/91234912/134452655-ffec31b3-fe75-4115-9a12-942f3ee4f045.png" width="50%">  
  
### 드래곤 플라이트
  
두번째로 영감을 받은 게임은 드래곤 플라이트 입니다.<br>
단순히 위에서 드래곤이 나오는 것만으로 난이도를 올렸으며 굳이 탄막이 아니더라도 난이도를 줄 수 있는 방법이라고 생각합니다.
  
- 이미지3  
  <img src="https://user-images.githubusercontent.com/91234912/134452654-a648902e-ace6-4fee-9cd7-5a0f641ce68a.png" width="80%">  
  
### 하스스톤 모험모드
 
세번째 게임은 하스스톤 모험모드에 포함되어 있는 밥의 선술집입니다.<br>
하스스톤은 기본적으로 카드게임이며, 사람과 하는 대전이 기본인 게임이지만 혼자서 할 수 있는 모험모드라는 것이 있습니다.<br>
모험모드는 주어진 카드를 통해서 보스를 잡으면서 플레이어의 선택에 따라서 점점 강해지는 것이 특징인데<br>
특정 모험모드에는 밥의 선술집이라는 것이 존재합니다.<br>
항상 나오는 것은 아니고 확률적으로 나오는 것이나 보스를 잡고 강화하는 것보다 더 확실하게 강화를 할 수 있는 게 특징입니다.
  
- 동영상
- 
  [![관련동영상1](https://user-images.githubusercontent.com/91234912/134452656-442e6582-f0bb-44f6-80ea-14b49b2cc314.png)](https://www.youtube.com/watch?v=uJNMO_HAXyY)
  
  [![관련동영상2](https://user-images.githubusercontent.com/91234912/134452655-ffec31b3-fe75-4115-9a12-942f3ee4f045.png)](https://www.youtube.com/watch?v=EHPRsAqVQck)
  
  [![관련동영상3](https://user-images.githubusercontent.com/91234912/134452654-a648902e-ace6-4fee-9cd7-5a0f641ce68a.png)](https://www.youtube.com/watch?v=TPhdDffh0kA)
<br><br>

# [대표 이미지]<a name='3'></a>

![그림](https://user-images.githubusercontent.com/91234912/172499913-2be33eb6-02a0-4083-a5fc-d7e0be049ac0.PNG)

<br><br>

# [컨셉 & 대표이미지 기반 작품묘사]<a name='4'></a>

<img src="https://user-images.githubusercontent.com/91234912/134452658-49ab3563-55b8-43fa-8831-d05114e96271.png" width="100%">

> ### 대표이미지 & 컨셉 기반
> 
> 서브컨셉의 강화와 뽑기입니다.
> 강화를 위한 예상되는 수치들 입니다.
> 
> 보스체력 : 1000
> 
> 플레이어의 기본 스팩<br>
> 
> 기본 공격력 10<br>
> 이동속도 10<br>
> 공격속도 1<br>
> 
> 특수능력<br>
> 
> 에너지 실드 : 특정 시간마다 공격을 막아주는 실드 생성<br>
> 유도 총알 : 아무렇게나 쏴도 보스쪽으로 유도되는 총알 발사<br>
> 럭키샷 : 공격력 10 고정 10% 확률로 적 즉사 (단 보스의 경우 10%확률로 50 데미지)

<br><br>

# [랜덤 탄막 프로젝트 구성 요소]<a name='5'></a>

- 랜덤 탄막 프로젝트
- 주 제목 : rendom reinforcement project of fighter aircraft(랜덤 전투기 강화 프로젝트)
- 제목 선정 이유 : 상대적으로 관심이 덜 한 탄막 슈팅보다 흥미가 있을법한 서브 주제인 강화를 내세웠다.

<br>

## 1. 메커니즘

[도전 과제]

1. 적들이 쏘아내는 탄을 맞지 않고 적을 타격한다.
2. 적들을 없애고 보스 스테이지까지 진입한다.
3. 보스 스테이지 클리어 후 강화를 진행한다. 
4. 강화를 진행 할수록 탄막 패턴이 추가되고, 적의 체력이 많아진다.
5. 기록을 점수로 가시화한다.

[재미 요소]

1. 아슬아슬하게 피할 수 있는 탄막을 설계하여 게임에 긴장감을 준다.
2. 운이 좋다면 압도적으로 빠른 시간 안에 보스를 끝낼 수 있는 능력을 갖출 수 있다. 
3. 한 번 운이 좋았다고 지속해서 빨리 끝내버리면 재미가 없으므로 적의 능력치 또한 점점 상승한다. 
4. 운이 나쁘면 플레이어에게 단점을 부여하여 강화 전보다 게임을 어렵게 만든다. 
5. 위쪽에서 떨어지는 벽을 만들어 탄막을 아무리 잘 피해도 능력치가 낮다면 피하기 힘들게되므로 무작위 뽑기를 강제한다.

<br>

## 2. 이야기

[만들게 된 배경]  
바인딩 오브 아이작이나 엔터 더 건전 같은 게임을 좋아하여 졸업작품으로 비슷한 게임을 만들어 보고자 하였습니다.<br>
이 두 게임의 특징은 적당한 컨트롤이 필요하면서 운의 요소가 강하게 작용하는 게임이며
탄막 슈팅 게임에서 이러한 특징을 가진 게임을 본 적이 없고 탄막 슈팅이 적당한 컨트롤을 지향하는 게임에 부합하는 것 같아서 선정하게 되었습니다.<br><br>
보통 탄막 슈팅이라 하면 엄청나게 많은 탄들이 탄막을 이루기 때문에 난이도가 상당하나,
이 게임에서는 전체적인 난이도를 낮추고 행운 요소를 집어넣어 재미를 추구하기 때문에 하드 난이도의 탄막 슈팅 게임을 깰 정도로 컨트롤이 뛰어나지 않아도 
재미있는 게임을 만들 수 있을 것으로 생각합니다.

[카메라 관점]  
2D 환경의 종스크롤 게임을 지향합니다. 탄막 슈팅의 특성상 카메라가 플레이어를 따라가게 된다면 게임이 매우 어지러워질 가능성이 있으므로 삼인칭 전지적 관점에서 게임을 플레이하게 됩니다

<br>

## 3. 미적요소

[디자인][컬러]  
도트 그래픽을 사용하여 아기자기한 느낌을 줍니다.<br>
플레이어는 파란색으로 표기하고 그 이외의 색들로 적들을 표현하여 플레이하는 데 어려움이 없게끔 할 것입니다.<br>
적의 총알은 빨간색으로 표시가 되며 배경과 확연하게 대비가 되는 색으로 플레이어가 총알을 인지하는 데 어려움이 없게끔 하려고 합니다.

[음향]  
플레이어가 탄을 쏠 때마다, 적이 최초로 탄을 쏠 때, 혹은 거대한 탄을 쏘고 탄이 사방으로 퍼질 때 탄을 쏘는 음향을 넣습니다.<br>
또한 보스전 진입 시에 등장 음을 넣어서 긴장감을 줍니다.
<br>

## 4. 기술

유니티 2D환경에서 스프라이트를 활용하여 게임을 구현합니다.<br>
플레이어의 기본 능력치를 public으로 넣어서 강화시의 능력 추가를 용이하게 구현 할 것이고,<br>
전투기에 2d 리지드바디를 넣어서 전투기가 강화창에 충돌할 경우 이벤트를 구현하여 마우스를 사용하지 않더라도<br>
원활한 게임을 할 수 있게 개발할 것입니다.

# [게임 시나리오]<a name='6'></a>

+ **첫 화면**
<br><br>
 + 게임 시작시에 볼 수 있는 배경화면과 중앙에 시작버튼이 있다.<br>
 + 게임 시작버튼을 누르면 난이도를 선택하고 게임이 시작된다.<br>
 + 난이도 선택에는 4가지 목록이 있다. 1. 튜토리얼 2. 쉬움 3. 보통 4. 어려움<br>
 + 튜토리얼을 누르면 게임의 전반적인 설명을 해주는 튜토리얼 보스와 스테이지가 나타난다.<br>
 + 왼쪽 상단에 내 목숨을 나타내는 전투기 3개가 있고 오른쪽 상단에 점수 0이 있다.<br>
 + 보스는 상단 중앙에 위치하고 보스의 머리에는 1500의 체력을 나타내는 바 형식의 게이지가 있다.<br>
 + 위쪽 방향키를 눌러보세요 라는 텍스트가 출력되어 위쪽 방향키를 누르면 내가 보스쪽으로 전진한다.<br>
 + 아래쪽 방향키를 눌러보세요 라는 텍스트가 출력되어 아래쪽 방향키를 누르면 내가 아래쪽으로 후진한다.<br>
 + 왼쪽 방향키를 눌러보세요 라는 텍스트가 출력되어 왼쪽 방향키를 누르면 내가 몸을 틀어 왼쪽으로 움직인다.<br>
 + 오른쪽 방향키를 눌러보세요 라는 텍스트가 출력되어 오른쪽 방향키를 누르면 내가 몸을 틀어 오른쪽으로 움직인다.<br>
 + z키를 누르세요라는 텍스트가 출력되어 총알이 계속 발사된다.<br>
 + 보스가 위에서 아래로 내려오는 벽 패턴을 쓰고 노란색 벽을 부수세요. 라는 텍스트가 출력된다.<br>
 + x키를 누르세요. 라는 텍스트가 출력되어 폭탄이 발사되면서 보스가 죽는다.<br>
 + 그 뒤에 게임의 강화 시스템이 나타나고 이것은 전투기를 강화하는 시스템입니다. 라는 텍스트가 출력된다.<br>
 + 공격력 강화는 전투기의 총알 공격력을 강화하고 포신 추가는 전투기를 따라다니는 포신을 추가합니다. 라는 텍스트가 출력된다.<br>
 + 랜덤은 전투기를 매우 강하게 만들 수 있지만 약하게 만들 수도 있습니다. 라는 텍스트가 출력된다.<br>
 + 이후 공격력 강화를 눌러보라는 텍스트가 출력되고 나는 공격력 강화를 누른다.<br>
 + 공격력 강화를 누르자 튜토리얼이 끝났습니다. 라는 텍스트가 출력되고 1. 튜토리얼 2. 쉬움 3. 보통 4. 어려움이 보이는 난이도 선택 창으로 되돌아온다.<br>
<br>

- **게임 시작 화면**
<br><br>
 - 2번 쉬움 모드를 눌러서 게임을 시작한다. 게임이 시작하자 양 옆으로 무한히 이어지는 초원이 보인다. 그리고 왼쪽 상단에서 적이 나타났다.<br>
 - 왼쪽으로 가서 왼쪽 상단에 있는 적을 격추하고 점수를 획득한다. 이후 무작위로 나오는 적을 격추 하며 전진하는 것을 반복하면서 보스 스테이지에 진입한다.<br>
 - 보스 스테이지에 진입하자 여태까지의 적과는 다른 화면을 꽉 채우는 적이 화면 상단에서부터 내려온다. 그 후 보스의 체력 바가 보이고 내 쪽으로 샷건 형태의 탄막을 발사한다.<br>
 - 보스의 탄막을 오른쪽 방향키를 눌러 피하고 z키를 눌러 총알을 쏴 보스에게 데미지를 준다 총알 한 발당 50의 데미지가 들어갔다.<br>
 - 보스의 총알을 피할 수 없어 x를 눌러 폭탄을 발사하니 화면에 있는 모든 총알이 사라지고 보스에게 1000의 데미지가 들어가며 보스가 죽었다.
 - 보스를 클리어 하니 우측 상단에 10000점의 점수가 추가되고 화면이 검은 색으로 변하면서 좌측부터 공격력 증가, 포신 증가, 랜덤이라는 화면이 출력 된다.<br>
 - 공격력 증가를 누르고 다음 스테이지로 진입한다.<br>
 - 다음 스테이지로 진입하자 적들의 체력이 증가했다는 것이 느껴진다.<br>

# [게임 시스템 디자인]<a name='7'></a>

### 1. 게임 오브젝트 분해(구성 요소 분석)<a name='7-1'><br><br>

|연번|오브젝트 이름|오브젝트 이미지|
|:-----:|:-----:|:-----:|
|1|Player|<img src="https://user-images.githubusercontent.com/91234912/172500465-335e52c8-7d5e-4449-aaea-80f3bbb5f1b7.png" width="300">|
|2|Bullet&Boom|<img src="https://user-images.githubusercontent.com/91234912/172499970-783eb157-04f0-4030-9883-3367aeca40c5.png" width="300">|
|3|Background Bottom|<img src="https://user-images.githubusercontent.com/91234912/172499981-e7357c84-3221-4b10-a1f0-10ccfd8e3988.png" height="300">|
|4|Background Mid|<img src="https://user-images.githubusercontent.com/91234912/172500048-65edc6d5-78ba-4d50-8cb7-04c5085ac574.png" height="300">|
|5|Background Top|<img src="https://user-images.githubusercontent.com/91234912/172500040-cf24cfc5-f9d5-4c94-90e5-f79ecd103c40.png" height="300">|
|6|Enemies Boss|<img src="https://user-images.githubusercontent.com/91234912/172500000-2d21fc4c-39e2-4043-bc99-b8ffee9f2680.png" width="300">|
|7|Enemies|<img src="https://user-images.githubusercontent.com/91234912/172500015-b79f8509-6cdf-42c3-bacd-5bc00b6db226.png" width="300">|
|8|Items|<img src="https://user-images.githubusercontent.com/91234912/137956915-b2cf64b9-0f20-4b9d-89df-c6800cfa5977.png" width="300">|


<br><br>

### 2. 파라미터(속성) 뽑아 보기<a name='7-2'><br><br>

#### 1)오브젝트 이름 : Player<br>

|속성|입력 값|설명|비고|
|:-----:|:-----:|:-----:|:-----:|
|Life|3|플레이어의 목숨| |
|Score|default : 0|플레이어가 얻은 점수| |
|Power|default : 6|총알의 공격력| |
|Speed|1|플레이어의 속도| |
|Boom|2|위기에서 벗어나게 해주는 폭탄 시작 시 2개 소지함| |
|Bullet speed|default : 0.15|총알의 기본 스피드 아이템이나 선택에 따라 늘어남| |
|Hit|false|플레이어가 적 총알에 맞았는지 판단하는 파라미터| |
|Critical Hit|default : 10%|플레이어의 치명타 확률| |

<br>

#### 2)오브젝트 이름 : Enemies<br>

|속성|입력 값|설명|비고|
|:-----:|:-----:|:-----:|:-----:|
|Name|A, B, C, Boss|적의 이름에 따라서 스프라이트가 바뀜| |
|Enemy Score|1000, Boss : 10000|적을 죽였을 때 얻는 점수| |
|Speed|1.5|적의 이동 속도| |
|Health|default : 6, Boss default : 1000|적의 체력| |
|Size|1, Boss : 10|적의 크기 이름에 따라서 달라짐| |
|Bullet Pattern|A, B, C, D|탄막의 패턴 보통의 적이 쏘는 패턴과 보스가 쏘는 패턴이 구분됨| |
|Wall Speed|default : 3|벽이 내려오는 속도 스테이지에 따라 점점 빨라짐| |

<br>

#### 3)오브젝트 이름 : Bullet<br>

|속성|입력 값|설명|비고|
|:-----:|:-----:|:-----:|:-----:|
|Name|1, 2, 3|Bullet의 이름| |
|x|1|스프라이트의 x좌표 (가변)| |
|y|0|스프라이트의 y좌표| |

<br>

#### 4)오브젝트 이름 : Boom<br>

|속성|입력 값|설명|비고|
|:-----:|:-----:|:-----:|:-----:|
|Remove Enemy|true|보스를 제외한 일반 적 제거| |
|Remove Enemy Bullet|true|모든 적 총알 제거| |

<br>

#### 5)오브젝트 이름 : Selected<br>

|속성|입력 값|설명|비고|
|:-----:|:-----:|:-----:|:-----:|
|Select|1, 2, 3|공격력 강화, 포신 추가, 랜덤 중 선택| |
|Player Power up|1|플레이어의 공격력 업| |
|Player Speed up|0.3|플레이어의 스피드 업| |
|Player barrel up|1|플레이어의 포신 증가| |
|Player Critical Hit up|10%|플레이어의 치명타 확률 증가| |

<br><br>

### 3. 행동 뽑아 보기<a name='7-3'><br><br>

#### 1)오브젝트 이름 : Player<br>

|행동|설명|
|:-----:|:-----:|
|이동|방향키로 플레이어 이동|
|총알 발사|Z키로 총알 발사|
|폭탄 발사|X키로 폭탄 발사|

<br>

#### 2)오브젝트 이름 : Enemies<br>

|행동|설명|
|:-----:|:-----:|
|이동|위에서 아래로 이동|
|총알 발사|플레이어를 향해서 총알 발사|

<br>

#### 3)오브젝트 이름 : Selected<br>

|행동|설명|
|:-----:|:-----:|
|생성|보스를 잡으면 생성됨|
|충돌|플레이어와 충돌하면 모두 사라지고 그에 따른 이벤트가 생김|
|플레이어 강화|충돌한 오브젝트에 따라서 플레이어가 강화됨|

<br>

#### 4)오브젝트 이름 : Items<br>

|행동|설명|
|:-----:|:-----:|
|생성|적을 잡으면 높은 확률로 코인이, 낮은 확률로 아이템이 생김|
|충돌|플레이어와 충돌하면 사라지고 그에 따른 이벤트가 생김|
|플레이어 강화|충돌한 오브젝트에 따라서 플레이어가 강화됨|

<br><br>

### 4. 상태 뽑아 보기<a name='7-4'>

#### 1)오브젝트 이름 : Player<br>

|현 상태|전이상태|전이조건|
|:-----:|:-----:|:-----:|
|정상 상태|정상 상태|입력 없음, 앞, 뒤 방향키 눌림|
|정상 상태|좌 선회 상태|왼쪽 방향키 눌림|
|정상 상태|우 선회 상태|오른쪽 방향키 눌림|

<br>

#### 2)오브젝트 이름 : Enemies(Boss)

|현 상태|전이상태|전이조건|
|:-----:|:-----:|:-----:|
|페이즈 1|페이즈 2|체력이 30%만 남음|

<br><br>

### 5. 게임의 규칙<a name='7-5'>

#### 1) 핵심 규칙

1. 사방에서 날아오는 적의 탄환을 맞지 않고 적을 파괴해야 함.<br>
2. 일정 거리에 도달하면 보스 스테이지에 진입하며 마찬가지로 맞지 않고 보스를 잡아야 함.<br>
3. 스테이지 종료시 플레이어의 전투기를 강화할 수 있음
<br>

#### 2) 보조 규칙

1. 플레이어의 목숨은 3개이며 3번 다 죽으면 게임이 끝남.<br>
2. 탄막을 피할 수 없다는 생각이 들면 X 키를 눌러 폭탄을 사용해 맵에 있는 적의 총알을 전부 제거할 수 있음
<br><br>

### 6. 게임에서 사용될 공식<a name='7-6'>

1. 총 한발 당 데미지 - 50
2. 총 발사 속도 - 10
3. 폭탄 데미지 - 1000
4. 스테이지 넘어갈 때 적의 체력 - 현재 스테이지의 체력 * 1.5
5. 랜덤 강화시 확률 - 전설 1%, 유니크 3%, 에픽 6%, 레어 20%, 커먼 70%
6. 쉬움 스테이지 적의 기본 체력 - 기본 체력 * 0.5
7. 보통 스테이지 적의 기본 체력 - 기본 체력 * 1
8. 어려움 스테이지 적의 기본 체력 - 기본 체력 * 2

# [개발 요구사항 & 흐름도]<a name='8'></a>
## [요구사항(6주차)]<a name='8-1'></a>
  1. ~~시작화면, 튜토리얼 화면, 쉬움 게임화면, 보통 게임화면, 어려움 게임화면 총 5개의 화면이 있다.~~
  2. ~~시작화면에는 튜토리얼, 쉬움, 보통, 어려움 이라는 버튼 4개가 있다.~~
  3. ~~방향키 입력에 따라 좌 선회, 우 선회 상태를 왔다갔다 하게끔 스프라이트를 변경한다.~~
  4. ~~보통 게임 화면에는 좌측 상단에 플레이어의 목숨, 우측 상단에는 점수가 표시된다.~~
  5. ~~플레이어의 조작은 방향키와 총알발사 z, 폭탄발사 x로 한다.~~
  6. ~~적은 탄환을 발사하고 플레이어는 적이 쏜 탄환이나 적에게 부딪히면 목숨을 1개 잃는다.~~
  7. ~~적을 죽이면 3% 확률로 아이템이 드랍된다.~~
  8. ~~아이템은 플레이어의 충돌을 통하여 먹을 수 있다.~~
  9. ~~배경 스크롤링을 이용하여 무한 배경을 구현한다.~~
  10. ~~패럴랙스를 이용하여 배경에 원근감을 부여한다.~~
  11. ~~보스는 원 모양으로 총알을 뿌리는 패턴, 플레이어를 향해서 샷건을 쏘는 패턴, 상단에서 벽을 하단으로 떨어트리는 패턴, 부채모양으로 발사하는 패턴이 존재한다.~~
  12. ~~적은 텍스트 데이터를 이용하여 커스텀 배치를 이용해서 생성한다.~~
  13. ~~가비지 컬렉션을 없애기 위한 오브젝트 풀링을 적용한다.~~
  14. ~~화면의 상단과 좌우에서 사선형태로 적이 나온다.~~
  15. ~~일반적인 적과 보스는 적의 종류별로 다른 점수를 준다.~~
  16. ~~적은 탄환을 발사하고 플레이어는 적이 쏜 탄환이나 적에게 부딪히면 목숨을 1개 잃는다.~~
  17. ~~쉬움, 보통, 어려움 게임 화면에는 무한히 이어지는 맵이 있으며 화면의 상단과 좌우에서 사선형태로 적이 나온다.~~
  
## [요구사항(1년차)]<a name='8-2'></a>

1. ~~시작화면, 튜토리얼 화면, 쉬움 게임화면, 보통 게임화면, 어려움 게임화면 총 5개의 화면이 있다.~~
2. 튜토리얼 클릭 시 튜토리얼 화면으로 이동한다.
3. 쉬움 클릭 시 쉬움 게임화면으로 이동한다.
4. ~~보통 클릭 시 보통 게임화면으로 이동한다.~~
5. 어려움 클릭 시 어려움 게임화면으로 이동한다.
6. 튜토리얼 화면에서는 게임의 기본적인 조작법과 공격 방법을 설명해준다.
7. 20마리의 적을 잡으면 보스가 등장하고 보스가 클리어 되면 공격력 강화, 포신 추가, 랜덤이라고 적혀 있는 강화 창이 나온다.
8. 3가지 선택지 중에 아무거나 누르면 강화창은 사라지고 다음 스테이지로 진입한다.
9. 보스의 공격속도와 패턴은 스테이지가 진행됨에 따라서 증가한다.
10. 포신 강화를 선택하면 플레이어를 따라다니는 포신이 추가된다.
11. 공격력 강화를 선택하면 +100 만큼 공격력이 가산된다.
12. 랜덤의 전설에는 공격력 *4, 치명타 확률 +30%, 유도 총알이 나타난다.
13. 랜덤의 유니크에는 공속 증가 *2, 포신 추가 +3, 공격력 *3이 나타난다.
14. 랜덤의 에픽에는 공격력 *2, 포신추가 +2, 치명타 확률 +10%가 나타난다.
15. 랜덤의 레어에는 무능력, 공격력 +100, 럭키 샷(치명타시에만 데미지 *3만큼 들어가며 일반공격엔 데미지가 안 들어감)가 나타난다.
16. 랜덤의 커먼에는 공속 +0.1, 폭탄 +1, 이동속도 +5가 나타난다.
17. 포신은 플레이어를 따라다닌다.
18. 크리티컬 확률 구현

## [키보드 이벤트에 대한 흐름도]<a name='8-3'></a>
  <img src="https://user-images.githubusercontent.com/91234912/139146609-75f95977-a992-4843-8e71-2c436ef3be6a.PNG" width="100%">

## [용어정리]<a name='8-4'></a>
  <img src="https://user-images.githubusercontent.com/91234912/139154483-c2088bf2-ffbd-4cb8-a4ae-e95d70fa7df3.PNG" width="100%">

# [개발 작업 일정]<a name='9'></a>
  수정 전
<img src="https://user-images.githubusercontent.com/91234912/139013652-fa6acaf3-588f-44bf-8fe4-a57e29c65e13.PNG" width="100%">
  수정 후
 <img src="https://user-images.githubusercontent.com/91234912/145205880-68418a2c-af89-40ca-910e-dfd65359dcfc.PNG" width="100%">

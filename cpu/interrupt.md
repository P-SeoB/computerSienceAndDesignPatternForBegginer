# 인터럽트란 무엇인가?

## 실생활에서 살펴보는 인터럽트
직역하면, 간섭, 방해 등으로 이해할 수 있는데 
**컴퓨터에서 인터럽트란** 상당히 도움 되는 기능이다. 
예를들어 컴퓨터가 하는 일을 요리에 비유한다면,
우리가 요리 중에 **전화가 울리면 일시로 중단을 하고, 전화를 받거나 하는 상황**에 
처하는데 이런 상황이 인터럽트이다. 

별거 아닌 스팸 전화라면 방해겠지만, 중요한 정보라면 방해가 아니라 유용한 기능일 것이다.
컴퓨터에겐 대체로 유용한 기능이다. CPU가 계산을 처리하는데 인터럽트가 없다면, 
그 계산이 끝날때까지 사용자는 기다려야할 것이다. 
게임을 다운받는 동안 멈춰있는 컴퓨터는 상상만해도 답답할 것 같다. 
글을 쓰면서 노래를 듣는다던지 하는 일이 인터럽트 덕분에 가능한 것이다. 

요약하자면, CPU가 어떤 계산을 처리하고 있는 도중에도 마우스나 키보드를 움직이면 바로 반응하는 모든 행위는 인터럽트 기능 덕분이다. ~~계산중이라고 무시당한 경험은 없으리라..~~

### 인터럽트의 또 다른 유용성
* if 인터럽트가 없으면...
	* CPU는 키보드에 버튼이 눌렸는지 매번 확인해야한다.
* else if 인터럽트가 있으면...
	* 키보드는 버튼을 눌렀다고 CPU에게 알리면 끝!

### 인터럽트가 끝나면 다시 돌아는 일은 어떻게 할까? 

인터럽트한 일이 정리되면 다시 원래 계산 작업으로 돌아갈 수 있게 하는 장치도 중요하다. 
**계산 도중의 숫자나 프로그램 카운터의 값**등을 어딘가 기억해야한다. 

이런 기능을 하는데 도움을 주는 것이 스택과, 스택포인터이다!
ㄴ 인터럽트 작업이 끝난 후 다시 원래 작업으로 돌아가기 위해서 필요한 기억 메모를 하는 기능!

### 스택과 스택 메모리
* 스택 - 메인 메모리 속의 일부를 확보해 두고, 기억 장치로 사용하는 기능 

![스택](https://user-images.githubusercontent.com/50472122/163699210-de1fea62-73a1-4c15-bc81-1c61f347f09b.png)

![스택 포인터](https://user-images.githubusercontent.com/50472122/163699223-25935ae6-14e6-4927-87ce-8051b8811e6b.png)

* 프로그램 카운터
	* 한 수 앞의 어드레스를 기억

* 스택 포인터 
	* 마지막 어드레스를 기억

여러 인터럽트가 들어올 때 순서가 꼬이지 않게 하는 것은 개발자의 역량이다.. (to be continue...)

### 인터럽트의 우선도

> 요리 중 전화도 울리고,  집에 손님이 찾아왔다면? 어떻게 해야하지!!??

* 인터럽트 마스크 
	* 인터럽트를 받아들이지 않게 하는 기능

* 리셋
	* 마스크를 하고 있어도 강제로 인터럽트를 해오는 것
	* 여러 인터럽트 중에서도 우선도가 가장 높다.
	* 마스크를 할 수 없는 특수한 인터럽트 입력이다.(기기 초기화에 사용됨)


# 심화 과정
- 알면 좋고 몰라도 그만 


## 메모리
	* RWM - 읽고 쓸 수 있음, 휘발성 메모리
		* **RAM** - 랜덤 엑세스
		* SAM - 시퀀셜 엑세스 ex) 자기 테이프, 
	* **ROM** - 읽기 전용,  불휘발성 메모리

## I/O 포트, GPU

### I/O 포트 
	*  입출력 장치와 CPU의 레지스터나 ALU가 연결되도록 하는 포트
	* 외부의 입력을 CPU에 전달
	* 방식이 외부 메모리를 연결하는 것과 비슷함

### GPU
	* 모니터(디스플레이 패널)은 CPU와 직접 연결되어 있지 않다.
	* 화면 부분을 **화상 처리 전용 연산 IC**를 이용하여 화면을 만들고 표시한다. 

![GPU](https://user-images.githubusercontent.com/50472122/163699670-1821040e-38fe-4763-b137-f35696d5cf1a.jpg)

## 클록 주파수, 정확도

* 클록 주파수 
	* 일정 주기로 H레벨과 L레벨을 반복하는 신호 '클록'
	* 주파수
		* 1초당 반복하는 신호의 수
		* 단위는 헤르츠(Hz) - 1초간 몇 회 클록 동작이 반복되고 있는지 나타내는 값
			* ex) 40MHz -> 1초간 4,000만 회의 클록 동작이 반복되고 있다는 뜻

**CPU의 심장 고동(클록)**이라고 불르기도 하고, 
내부 회로(ALU에 데이터를 래치하거나 프로그램 카운터를 진행시키는 블록)를
가동하기 위해서는 클록이 필수이다!	

Hz의 값이 높을 수록 클록의 속도가 빨라 CPU의 처리 능력이 뛰어나다고 할 수 있다.

### 정확도
40MHz 파동이 얼마나 정확하게 맞는지에 대한 척도
컴퓨터를 통신기기에 응용하는 경우, 통신 기기끼리 연결하는 
신호선은 서로 기준되는 클록이 일치하지 않으면 타이밍이 맞지 않게 된다. 

### 클록 제너레이터 
발진기 CPU 내부에 발진회로가 있다! 
발진회로 = 증폭기 + **수정 진동자** + 콘덴서와 저항

* 수정 진동자 
	* 수정편 : +, - 로 바뀔 떄 진동이 생기는데 그 진동이 클록의 씨앗이다!
	
## 타이머 인터럽트

![IMG_1159](https://user-images.githubusercontent.com/50472122/163702490-60dd589b-2c4f-4bf6-896f-23fbdcc5129c.jpg)

![IMG_1160](https://user-images.githubusercontent.com/50472122/163702610-9ef2b12f-50dc-4904-905b-e040b6bc55aa.jpg)
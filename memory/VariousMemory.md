# 여러 가지 기억 장치

### 주 기억장치 
* 메인 메모리

### 보조 기억장치
* HDD(SSD)

## 주기억장치와 보조기억장치 비교
```
1. 휘발성
2. CPU와 직접 버스 유무
3. 처리속도
```
### 휘발성

> PC의 전원을 끄면 메모리에 있는 데이터는 사라진다!
> 그러나 하드디스크에 있는 데이터는 사라지지 않는다.

메모리가 프로그램을 들고 있을 수 있는 것은, PC 전원이 켜져있을 때 
**하드디스크에서 메모리로 '데이터의 일부'가 복사**되어 있는 것 뿐!

예를들어, CPU는 두뇌이고, 메모리는 책상 위,  하드디스크는 서랍이라고 볼 수 있다.

### CPU와의 연결성
> 메모리는 CPU에서 직접 읽고 쓸 수 있다!
> 그러나 하드디스크는 CPU에서 직접 쓸 수 없다.

CPU -> I/O 영역(하드디스크 인터페이스) -> HDD

**하드디스크는 CPU가 직접 관리하고 있는 공간 - 어드레스(메모리 공간)에는 없다!** 
**CPU와 직접 주고 받을 수 있는 건 메모리와 I/O 뿐!**
(I/O 영역도 어드레스 공간 안에 있음)

![](https://user-images.githubusercontent.com/50472122/163698489-9db9435a-b36e-4d21-9841-e55990d05386.jpeg)

### 처리속도

> 메모리와 하드디스크를 비교하면 메모리 쪽이 처리 속도가 빠르다!

하드디스크쪽으로 갈 수록 저장공간이 늘어나는대신 처리 속도는 느린 반면, 레지스터(CPU내의 메모리) 쪽으로 갈 수록
처리속도는 빠른 대신, 처리 용량은 줄어든다. 메모리는 그 중간에서 역할을 한다.

![메모리hdd피라미드](https://user-images.githubusercontent.com/50472122/163698580-eedd2a61-7bb8-4e91-9703-91b2715689eb.jpg)

## RAM, ROM, I/O

### 어드레스 공간
CPU에 의한 ~~절대 지배하의 암흑공간~~은 아니고, **CPU가 직접 관리하고 있는 공간**
더 정확히는
**CPU가 관리하는 외부 메모리의 영역 전체**를 가리킨다

<어드레스 공간에 연결된 외부메모리 계층 구조>

* 외부 메모리
	* RAM 영역 
		- 읽고 쓸 수 있는 메모리
		- 전원이 꺼지면 데이터도 사라짐
	* ROM 영역 
		-  읽기 전용 메모리
		- 전원이 꺼져도 데이터를 저장

ROM에는 전원을 끈 후에도 데이터를 저장하고 있고, 읽기만 가능한 메모리가 있다.
대표적으로 CPU가 첫걸음을 내딛기 위한 프로그램이 내장되어 있다. 바로 **BIOS**

**What is BIOS?**
Basic Input/Output System 의 약자로, 가장 기초적인 프로그램이 들어있다. 
전원이 들어온 직후에 PC 내부에 여러가지 장치가 정상적인지 확인하며,  - 1
하드디스크 속의 OS(WIN, OSX, LINUX)를 기동시켜준다. - 2 

### 어드레스 공간의 구조
* RAM 영역
* ROM 영역
* I/O 영역(크기 작음, 메모리영역에 포함되는 경우도 있고, 안되는 경우도 있다.)
	* 입출력 포트가 있어서, 외부 장치와 CPU를 직접 연결 시켜주는 역할

**어드레스 공간을 이용해서 외부 장치도 CPU의 관리하에 놓고 있다**



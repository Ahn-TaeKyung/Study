1. 운영체제의 기능과 거리가 먼 것은?
* 프로세스 스케줄링
* 파일 입출력
* 사용자나 프로세스가 CPU를 사용한 시간에 대한 통계
* **컴파일** - 컴파일은 운영체제가 아닌 컴파일러가 담당하는 작업
---
2. 운영체제의 특징과 동떨어진 내용은?
* 운영체제의 기능이 자원을 관리하는 것이지만, 운영체제가 컴퓨터의 모든 자원을 관리하지는 않는다.
* 운영체제의 역할에는 사용자가 컴퓨터 하드웨어에 대한 지식이 없어도 사용할 수 있도록 해주는 것도 포함된다.
* 운영체제는 메몸리에 상주하여 사용자 프로그램을 실행시키고 종료할 때까지 관리한다.
* **운영체제는 외부로부터의 악의적 침입을 막는다.** - 보안 시스템의 역할
---
3. 고정 프로그래밍 방식을 설명하는 것으로 틀린 것은?
* 고정 프로그래밍 방식이란 수백에서 수천 개의 전선을 연결하여 프로그램을 하드웨어에 고착화시키는 방식이다.
* **운영체제가 한 번에 한 개의 프로그램만 실행시키는 방식이다.** - 단일 프로세싱 시스템 
* ENIAC 컴퓨터는 고정 프로그래밍 방식의 컴퓨터이다.
* 고정 프로그래밍 방식은 1940년대에 컴퓨터를 만드는 방식이었다.
---
4. 모바일 운영체제의 특징이 아닌 것은?
* 휴대용 장치에서 실행되도록 만들어진 운영체제이다.
* 적은 메모리에서 응용프로그램을 실행시킬 수 있도록 특화시킨 운영체제이다.
* **대표적으로 PSOS, VxWorks, VRTX, RT-Linux, Lynx 등이 있다.** - 실시간 운영체제이다.
* 절전이 매우 중요한 기능이다.
---
5. 내장 프로그래밍 방식의 출현이 획기적인 이유가 아닌 것은?
* **컴퓨터를 CPU와 메모리로 분리하게 되었다.** - 내장 프로그래밍 방식의 출현과는 관계가 없다.
* 하드웨어와 소프트웨어의 개념이 분리되었다.
* 메모리에 프로그램을 적재하는 개념이 시작되었다.
* 오늘날 운영체제가 출현되었다.
---
6. 운영체제의 태동이 된 기능은?
* 프로세스 관리 기능
* **프로그램 적재 기능** - 초기 운영체제는 프로그램을 메모리에 적재하고 실행하는 것이 주요 기능
* 메모리 관리 기능
* 파일 입출력 기능
---
7. 초기 운영체제가 나타나게 된 동기가 아닌 것은?
* 개발자마다 입출력 코드를 동일하게 작성하는 비효율성을 개선하기 위해
* 값비싼 컴퓨터가 놀고 있는 시간을 줄이기 위해
* 개발자의 대기 시간을 줄이기 위해
* **비싼 메모리를 효율적으로 사용하기 위해** - 초기 운영체제는 프로세스 관리와 입출력 처리의 효율성을 높이기 위해 개발됨
---
8. 최초의 운영체제 GM-NAA I/O에 구현된 기능은?
* **프로그램 적재 기능** - GM-NAA I/O는 프로그램을 메모리에 적재하는 기능이 핵심
* 메모리 관리 기능
* 프로세스 관리 기능
* 네트워크 기능
---
9. 내장 프로그램 컴퓨터의 특징과 관계없는 것은?
* 컴퓨터 하드웨어와 소프트웨어의 분리
* **CPU와 메모리의 구분없는 고정 프로그래밍 방식** - CPU와 메모리가 구분된 폰노이만 구조를 따름
* 폰노이만
* 오늘날까지 지속되는 구조
---
10. 배치 시스템에 대한 설명으로 옳은 것은?
* **모여진 작업을 순서대로 하나씩 연속하여 처리하는 시스템** - 한번에 여러 작업을 모아 순차적으로 처리하는 방식
* 개발자는 작업을 입력 데크에 올려놓고 실행되는 과정을 관찰하고 오류가 발생하면 바로 고칠 수 있는 시스템
* 모여진 여러 작업들을 동시에 병렬적으로 실행시키는 시스템
* 배치 시스템은 다중프로그래밍 시스템보다 CPU 활용률이 높다.
---
11. 다중프로그래밍을 정확히 묘사한 것은?
* 한 사람이 여러 개의 응용프로그램을 작성하여 실행시키는 기술
* **메모리에 여러 프로그램을 올려놓고 한 프로그램이 입출력을 수행하면 CPU에게 다른 프로그램을 실행시켜 CPU활용률을 높이는 기술** - 다중 프로그래밍은 여러 프로그램을 메모리에 적재해 CPU가 유휴 상태가 되지 않도록 관리하는 기술
* 여러 개의 CPU에 여러 프로그램을 병렬적으로 실행시키는 병렬처리 기법의 일종
* 멀티스레딩과 같이, 동시에 여러개의 작업을 처리할 수 있는 프로그램 작성 기술
---
12. 다중프로그래밍이 출현한 동기는?
* **배치 운영체제의 저조한 CPU 활용률을 개선하기 위해** - CORRECT
* 배치 운영체제에서 사용자의 긴 대기 시간을 줄이기 위해
* 사용자와 대화식 실행을 위해
* 메모리에 많은 프로그램을 적재하기 위해
---
13. 다중프로그래밍 기법은 여러 프로그램을 메모리에 올려놓고 동시에 실행시키기 떄문에 해결해야할 많은 운영체제 이슈와 과제들이 생기게 되었다. 다음 중에서 이슈들을 골라라
```markdown
GUI 화면 관리, 컴퓨터 바이러스 문제, 네트워크를 이용한 원격 연결,

"인터럽트", "다른 프로세스의 메모리 영역을 침범하지 못하게 하는 메모리 보호",
"프로그램 당 메모리 할당 위치와 크기에 관한 전략", "교착상태",
"자원에 대한 프로그램들 사이의 동기화", "CPU 스케줄링"
```
다중프로그래밍 환경에서 발생하는 대표적인 운영체제 과제들

---
14. 개인용 컴퓨터의 출현 동기가 아닌 것은?
* 터미널이 있는 전산실에 가야하는 번거로움 해소
* 다중 사용자로 인한 응답 속도 저하 해결
* 마이크로프로세서의 출현
* **전화로 미니컴퓨터에 원격접속하는 비용 부담 해소** - 사용자의 편의성과 마이크로프로세서의 발전에 기인한 것, 원격 접속 비용 해소와는 관련 없다
---
15. 시간 할당량 단위로 돌아가면서 프로그램에게 CPU를 할당해주는 운영체제는?
* **시분할 운영체제** - 각 프로그램에 일정한 시간 동안 CPU를 할당하는 방식
* 다중 사용자 운영체제
* 배치 운영체제
* 실시간 운영체제
---
16. 사용자가 대화식으로 프로그램을 실행시키기 위해 고안된 운영체제는?
* 배치 운영체제
* 다중 프로그래밍 운영체제
* **시분할 운영체제** - 사용자가 즉각적인 피드백을 받을 수 있도록 설계된 운영체제
* 모바일 운영체제
---
17. 개인용 컴퓨터의 상용화가 이루어지게 된 결정적인 계기는?
* **마이크로프로세서 개발** - CORRECT
* 그래픽 처리 기술 개발
* 사생활 보호
* 인터넷의 개발
---
18. 모바일 운영체제의 목적이 아닌 것은?
* 열악한 하드웨어의 효율적 사용
* 저전력 달성
* 이동 중에서 활용 가능
* **프로그램의 실시간 실행** - 모바일 운영체제는 저전력과 이동성에 중점을 두며, 실시간 운영체제가 실시간 처리를 중요시 한다.
---
19. 실시간 운영체제의 가장 중요한 목적은?
* 프로그램을 최대한 빨리 실행
* **프로그램마다 정해진 완료 시간 이내에 실행** - CORRECT
* 컴퓨터의 고장으로부터 보호
* 저전력 달성
---

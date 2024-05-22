# Application Layer

중

# 텔넷
**Tel**etype **Net**work 의 약자

- 한대의 컴퓨터가 로컬 검퓨터에 연결될 수 있도록 하는 일종의 프로토콜
- ISO에서 제공하는 가상 터미널 서비스를 위한 표준 TCP/IP 프로토콜
- 인터넷이나 로컬 영역 네트워크 연결에 쓰이는 네트워크 프로토콜
- 연결을 시작하는 컴퓨터가 local computer(로컬 컴퓨터)
- 연결을 수락하여 연결되는 컴퓨터가 remote computer (원격 컴퓨터)
- 텔넷 작업 중에는 원격 컴퓨터에서 수행되는 모든 작업이 로컬 컴퓨터에 표시된다
- 로컬 컴퓨터는 텔넷 클라이언트 프로그램을 사용하고, 원격 컴퓨터는 텔넷 서버 프로그램을 사용한다

## Logging

### local login
- 사용자가 로컬 시스템에 로그인할 때마다 로컬 로그인이라고 한다

<img src="https://github.com/Ahn-TaeKyung/Study/assets/154008745/ecd59067-677e-489e-b207-ca24f7b94eaa" width="500">

**절차**
- 사용자가 터미널에 명령어를 입력할 때 터미널 드라이버가 키 입력을 받습니다.
- 터미널 드라이버는 그 명령어를 OS에 전달합니다
- OS는 명령어의 유효성을 검사하고 필요한 응용프로그램을 엽니다

### remote login
- 사용자가 컴퓨터에 로그인하여 원격 컴퓨터에서 사용가능한 서비스를 사요할 수 잇게하는 프로세스
- 원격 로그인의 도움으로 사용자는 원격 컴퓨터에서 로컬 컴퓨터로 처리 결과를 전송한 결과를 이해할 수 있다.

<img src="https://github.com/Ahn-TaeKyung/Study/assets/154008745/35a92a7d-e6a3-4d1e-8ffc-1236688919cd" width="500">

**절차**
- 사용자가 로컬 컴퓨터에 무언가를 입력하면 로컬 OS에서 해당 문자를 입력받습니다.
- 로컬 컴퓨터는 문자를 해석하지않고 TELNET 클라이언트로 전송
- TELNET 클라이언트는 NVT(Network Virtual Terminal)문자로 변환 후, 로컬 TCP/IP프로토콜 스택에 전달
- NETWORK를 통해 원격 컴퓨터의 TCP/IP로 도착
- OS가 전달받고 TELNET서버로 전달
- TELNET 서버가 원격 컴퓨터가 이해할 수 있는 문자로 재변환 하여 문자가 터미널에서 나오는 것처럼 표현하는 소프트 웨어인 의사 터미널 드라이버로 전달
- 의사 터미널 드라이버는 OS로 전달
- OS는 적절한 응용 프로그램에 전달


## NVT 네트워크 가상 터미널
**다양한 유형의 실제 터미널이 공유하는 기본 구조를 갖는 NELNET의 가상 터미널**
서로 다른 운영 체제를 사용하는 서로 다른 유형의 터미널 간의 통신을 가능하게 하기 위해 만들어졌다.

## TELNET 명령어 

바이트코드 255의 IAC 접두사로 식별되고 뒤에 Command code 와 Option code 가 옵니다.

<img src="https://github.com/Ahn-TaeKyung/Study/assets/154008745/2a6a978c-4b00-4202-8932-471089fe8d09" width="500">

**Command code**

<img src="https://github.com/Ahn-TaeKyung/Study/assets/154008745/eac96dc0-b43a-48f6-93b6-5a5f545628c4" width="500">

**Option code**

<img src="https://github.com/Ahn-TaeKyung/Study/assets/154008745/3cd8798e-bfa4-4af0-9f82-a63d58d0576c" width="500">





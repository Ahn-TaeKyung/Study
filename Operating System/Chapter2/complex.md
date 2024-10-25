1. 응용프로그램을 작성할 때 표준 라이브러리 함수 (예: printf())를 호출하는 것이 시스템 호출 함수(예: write())를 호출하는 것보다 나은 방법인 이유를 설명하라.

코드의 가독성, 유지보수성, 편의성 등

2. 인터럽트 서비스 루틴이 커널 영역에 있어야 하는 이유가 무엇일까?

보안 및 안정성, 특권 수준 등

3. 컴퓨터 시스템과 운영체제의 목표는 CPU의 활용률을 극대화하는데 있다. 인터럽트는 이 목적을 달성하게 하는데 중요한 역할을 한다. 인터럽트가 어떤 식으로 CPU 활용률을 높이는데 기여하는지 설명하라.

효율적인 입출력, 우선수위 처리 등

4. 탐구 2-2의 소스 코드를 수정하여 디스플레이에 "I love OS"를 출력하는 프로그램을 작성하고 실행시켜라. 프로그램을 iloveos.s 파일에 작성하고 다음과 같이 컴파일하고 실행하면 된다.

```bash
$ gcc -c iloveos.s && ld iloveos.o
$ ./a.out
I love OS
$
```

`탐구2-2`
hello.s
```assembly
  .global _start
  .text
_start:
  mov  $1, %rax
  mov  $1, %rdi
  mov  $msg, %rsi
  moc  $12, %rdx
  syscall

  mov  $60, %rax
  xor  %rdi, %rdi
  syscall

msg:
  .ascii "Hello world\n"  # .ascii "I love OS\n" 으로 변경
```

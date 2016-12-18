#Interrupt
- 정의 : a signal to the processor or an instruction in software
- CPU 외부의 하드웨어적 요구나 소프트웨어적 요구에 의해 정상적인 실행 흐름을 변경하여, 시급한 작업을 먼저 수행한 뒤 실행중인 프로세스로 복귀하는 방법
- 비동기적인 주변장치의 서비스 요청 이벤트 처리
- 인터럽트 발생 시 복귀 주소(return address)를 저장해 두었다가 ISR(Interrupt Service Routine) 마지막에 복귀명령에 이용
- 운영체제는 인터럽트 의존적이다.
###인터럽트의 종류
- hardware interrupt(externel interrupt) : 입출력 등 외부 장치에서 발생하는 인터럽트(시스템 외부 요인; 전원, 기계, 외부 신호 등)
- software interrupt(internel interrupt와 유사) : 잘못된 명령이나 데이터 사용(프로그램 검사)에 의해 발생하는 인터럽트 = Trap
 * 실질적으로는 hardware interrupt만 존재한다. Trigger가 software일 경우 software interrupt라고 부를 뿐.
###ISR(Interrupt Service Routine)
- 인터럽트가 발생하면, 유저 모드에서 커널 모드로 들어가서 인터럽트를 처리한다. (하드웨어 적으로)
 - 인터럽트가 발생하면, 현재 프로그램 상태를 PC에 저장(Program counter register)
 - Interrupt vector(인터럽트에 해당하는 ISR 실행 정보를 담고 있는 벡터)를 탐색
 - 인터럽트 처리 : 요청 장치를 식별, 실질적 인터럽트 처리
 - 상태를 복구하고, PC에 저장된 프로그램 상태를 통해 실행 개재
- 인터럽트 발생을 확인하는 방법
 - Polling : 하나씩 인터럽트가 걸린 프로세스를 확인
 - Vector interrupt system : 인터럽트 요청을 한 프로세스를 확인할 수 있다.
 - Daisy-Chain : 하드웨어적인 방법

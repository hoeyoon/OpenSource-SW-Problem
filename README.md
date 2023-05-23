# OpenSource-SW-Problem
>**top, ps, jobs, kill에 대해 조사**
---
## top
![image](https://github.com/hoeyoon/OpenSource-SW-Problem/blob/master/picture/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202023-05-22%20004819.png)
+ 현재 실행되고 있는 **프로세스에 관한 정보**를 출력하는 명령어 (Windows작업 관리자와 비슷!)
+ 3초 간격으로 화면을 갱신하며 정보를 보여줌
#
+ 서버 정보
  + **top-00:40:12**: 현재 서버의 시간
  + **up**: 35일째 구동 중
  + **10:05**: 10시간 5분전에 구동
  + **2 users**: 2명의 사용자 접속
  + **load average**: 1, 5, 15분 평균 CPU 부하율
#
+ 프로세스 정보
  + **Tasks**: 324개의 프로세스 가동 중
  + **runnig**: 1개의 프로세스 실행 중
  + **sleeping**: 320개 프로세스 대기 중
  + **stopped**: 3개의 프로세스 멈춤
  + **zombie**: 0개의 좀비상태
#
+ CPU 정보
  + **us**: 사용자 공간에서 사용중인 CPU비중
  + **sy**: system 레벨에서 사용중인 CPU비중
  + **ni**: nice값 낮을수록 우선순위가 높음
  + **id**: 유휴 상태의 CPU 비중
  + **wa**: wa 시스템이 입출력 요청을 처리하지 못한 상태에서 CPU IDLE 비중
#
+ 메모리 정보
  + *Mem* 
    + **total**: 전체적인 물리적 메모리
    + **free**: 사용되지 않는 여유 메모리
    + **used**: 사용중인 메모리
    + **buff/cache**: 버퍼된 메모리
  + *Swap*
    + **total**: 전체 swap 메모리
    + **free**: 사용되지 않는 여유 swap메모리
    + **used**: 사용중인 swap 메모리
    + **avail mem**: 새로운 애플리케이션을 시작할 수 있는 메모리 양

#
+ top 실행 옵션
  + **batch 모드**: top -b 
  + **top 실행 주기 설정**: top -n
#
+ top 실행 후 명령어
  + **shift + p**: CPU 사용률 내림차순
  + **shift + m**: 메모리 사용률 내림차순
  + **shift + t**: 프로세스가 돌아가고 있는 시간 순
  + **k**: kill. k 입력 후 PID 번호 작성. signal은 9
  + **f**: sort field 선택 화면 q 누르면 RES순으로 정렬
  + **a**: 메모리 사용량에 따라 정렬
  + **b**: batch 모드로 작동
  + **1**: CPU Core별로 사용량 보여줌

---
## ps
![image1](https://github.com/hoeyoon/OpenSource-SW-Problem/blob/master/picture/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202023-05-24%20000806.png)
+ 현재 실행중인 프로세스의 목록을 보는 명령어
+ Process Status의 약자
#
+ ps 실행옵션
  + **-e**: 실행중인 모든 프로세스의 정보를 출력
  + **-f**: 프로세스에 대한 자세한 정보를 출력(PID 확인 가능)
  + **-u [사용자이름]**: 특정 사용자에 대한 모든 프로세스의 정보를 출력
  + **-p pid**: pid로 지정한 프로세스의 정보를 출력
  + **u**: 프로세스 소유자의 이름, CPU 사용량, 메모리 사용량 등 상세 정보 출력
  + **x**: 실행 중인 모든 프로세스의 정보를 출력
#
+ ps 상태
  + **USER**: 프로세스 소유자의 USERNAME (BDS 계열)
  + **UID**: 프로세스 소유자의 USERNAME (SYSTEM V 계열)
  + **PID**: 프로세스 식별번호
  + **%CPU**: CPU 사용비율
  + **%MEM**: 메모리 사용비율
  + 이 밖에도 더 있음...
---
 ## jobs
 ![image2](https://github.com/hoeyoon/OpenSource-SW-Problem/blob/master/picture/99E14B465E60F42D2A.png)
 + 실행중인 백그라운드 목록 출력
#
+ jobs 실행옵션
  + **-l**: 더 자세한 내역 출력
  + **-p**: PID 출력
#
+ jobs 상태
  + **Runing**: 작업이 종료하지 않고 계속 진행 중
  + **Done**: 작업이 완료되어 0을 반환하고 종료 함
  + **Stoped**: 작업이 일시 중단
  + **Done**: 작업이 정상적으로 완료 코드를 반환
---
## kill
+ 프로세스에 특정한 신호를 보내는 명령어
+ 보통 실행중인 프로세스에 종료신호를 보냄
+ 중지시킬 수 없는 프로세스를 종료시킬때 많이 사용함
#
+ kill 실행옵션
  + **-9**: PID를 직접 지정하여 종료시 사용함
  + **-l**: 신호로 사용할수 있는 신호 이름들을 보여줌
#
+ 신호 이름
  + **SIGHUP**: HUG, 로그아웃등의 접속이 끊을 때 발생하는 신호
  + **SIGINT**: INT, 현재 작동중인 프로그램을 동작을 멈출때 사용
  + **SIGKILL**: KILL, 프로그램을 무조건 종료할 경우 사용
  + **SIGSEGV**: SEGV, 잘못된 메모리 관리시 생기는 신호
  + 이 밖에 더 있음...

## Security > Vaccine > 콘솔 사용 가이드

Vaccine Agent 활성화 및 비활성화 절차와 상품 이용중 특정 상황에서 참조할수 있는 가이드입니다.

## Vaccine Agent 활성화 절차

### 리눅스 계열 Agent

1\. 설치 스크립트 '클립보드 복사'

<center>![alt](http://static.toastoven.net/prod_vaccine/linux-1.jpg)</center>
<center>[그림1] 리눅스 계열 설치 스크립트</center>

2\. 설치 대상 Instance 터미널 접속

3\. 관리자 권한으로 Agent 스크립트 생성 및 실행

* vi 편집기 등으로 스크립트를 생성합니다.
* 생성한 스크립트 파일의 권한을 변경합니다.
* 파일을 실행합니다.
```
[root@vaccine-test ~]# cd ~
[root@vaccine-test ~]# vi agent.sh
[root@vaccine-test ~]# chmod 744 agent.sh
[root@vaccine-test ~]# ./agent.sh
/tmp/DownloadInstallAgentPackage: OK
Downloading agent package ...
curl https://106.249.21.88:4119/software/agent/RedHat_EL7/x86_64/ -o /tmp/agent.rpm --insecure --silent
Installing agent package ...
Preparing...                          ################################# [100%]
Updating / installing...
   1:ds_agent-10.0.0-2775.el7         ################################# [100%]
Starting ds_agent (via systemctl):  [  OK  ]
HTTP Status: 200 - OK
Activation will be re-attempted 30 time(s) in case of failure
dsa_control
HTTP Status: 200 - OK
Response:
Attempting to connect to https://106.249.21.88:4120/
SSL handshake completed successfully - initiating command session.
Connected with (NONE) to peer at 106.249.21.88
Received a 'GetHostInfo' command from the manager.
Received a 'GetHostInfo' command from the manager.
Received a 'SetDSMCert' command from the manager.
Received a 'SetAgentCredentials' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetInterfaces' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetAgentStatus' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetHostMetaData' command from the manager.
Received a 'SetSecurityConfiguration' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetAgentStatus' command from the manager.
Command session completed.
[root@vaccine-test ~]#
```

4\. 웹콘솔 새로고침 및 사용시작

* 새로고침을 클릭하면 현황 리스트에 설치된 Agent 정보가 표시됩니다.
* 사용시작 버튼을 클릭하면 상품 사용이 시작됩니다.
<center>![alt](http://static.toastoven.net/prod_vaccine/linux-2.jpg)</center>
<center>[그림2] 리눅스 계열 사용시작</center>

### 윈도우 계열 Agent

1\. 콘솔 스크립트 복사

<center>![alt](http://static.toastoven.net/prod_vaccine/window-1.jpg)</center>
<center>[그림3] 윈도우 계열 설치 스크립트</center>

2\. 설치 대상 Instance 터미널 접속

3\. 관리자 권한으로 Agent 스크립트 생성 및 실행

   * 노트패드 등으로 스크립트 파일을 생성합니다.
   * 관리자 권한으로 cmd 창을 활성화 합니다.
   * powershell -file "파일경로/파일명" 형태로 실행합니다.
```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

C:\Users\Administrator>powershell -file "agent.ps1"


    디렉터리: C:\Users\Administrator\AppData\Roaming\Trend Micro\Deep Security Agent


Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----      2018-06-05   오후 2:37            installer
기록이 시작되었습니다. 출력 파일은 C:\Users\Administrator\AppData\Roaming\Trend Micro\Deep Security Agent\installer\dsa_deploy.log입니다.
오후 2:37:23 - DSA download started
오후 2:37:23 - Download Deep Security Agent Package
https://106.249.21.88:4119/software/agent/Windows/x86_64/
오후 2:37:24 - Downloaded File Size:
13897728
오후 2:37:24 - DSA install started
오후 2:37:24 - Installer Exit Code:
0
오후 2:37:32 - DSA activation started
HTTP Status: 200 - OK
Activation will be re-attempted 30 time(s) in case of failure
dsa_control
HTTP Status: 200 - OK
Response:
Attempting to connect to https://106.249.21.88:4120/
SSL handshake completed successfully - initiating command session.
Connected with AES256-SHA256 to peer at 106.249.21.88
Received a 'GetHostInfo' command from the manager.
Received a 'GetHostInfo' command from the manager.
Received a 'SetDSMCert' command from the manager.
Received a 'SetAgentCredentials' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetInterfaces' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetAgentStatus' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetHostMetaData' command from the manager.
Received a 'SetSecurityConfiguration' command from the manager.
Received a 'GetAgentEvents' command from the manager.
Received a 'GetAgentStatus' command from the manager.
Command session completed.
기록이 중지되었습니다. 출력 파일은 C:\Users\Administrator\AppData\Roaming\Trend Micro\Deep Security Agent\installer\dsa_deploy.log입니다.
오후 2:38:29 - DSA Deployment Finished

C:\Users\Administrator>
```

4\. 웹콘솔 새로고침 및 사용시작

* 새로고침을 클릭하면 현황 리스트에 설치된 Agent 정보가 표시됩니다.
* 사용시작 버튼을 클릭하면 상품 사용이 시작됩니다.
<center>![alt](http://static.toastoven.net/prod_vaccine/window-2.jpg)</center>
<center>[그림4] 윈도우 계열 사용시작</center>

## Vaccine Agent 비활성화 절차

### 리눅스 계열 Agent

1\. 웹콘솔 사용중지

* 사용종료 버튼을 클릭하여 백신 사용을 중지합니다.
<center>![alt](http://static.toastoven.net/prod_vaccine/linux-3.jpg)</center>
<center>[그림5] 리눅스 계열 사용중지</center>

2\. 백신 Agent 삭제

* Instance에 접속하여 Vaccine Agent를 삭제합니다.
   * CentOS: rpm -e ds_agent 실행
   * Debian/Ubuntu: apt-get remove ds-agent 실행
### 윈도우 계열 Agent

1\. 웹콘솔 사용중지

* 사용종료 버튼을 클릭하여 백신 사용을 중지합니다.
<center>![alt](http://static.toastoven.net/prod_vaccine/window-3.jpg)</center>
<center>[그림6] 윈도우 계열 사용중지</center>

2\. 백신 Agent 삭제

* Instance에 접속하여 Vaccine Agent를 삭제합니다.
   * 프로그램 및 기능 메뉴에서 "Trend Micro Deep Security Agent" 삭제
## Vaccine Quick 가이드

### 파일 복원 가이드
1\. 파일 복원

* 복원 툴을 [다운로드](http://static.toastoven.net/prod_vaccine/QFAdminUtil_win32.zip) 합니다.
* 다운로드한 QFAdminUtil_win32.zip 파일을 windows OS 환경에서 압축해제 합니다.
* QDecrypt.exe 실행 후 격리된 파일을 열고 파일을 복원합니다.
<center>![alt](http://static.toastoven.net/prod_vaccine/restore.jpg)</center>
<center>[그림7] 복원 툴 실행 및 격리된 파일 복원</center>

2\. 격리 파일 위치

* Linux : /var/opt/ds_agent/guest/0000-0000-0000/quarantined
* Windows : C:\ProgramData\Trend Micro\AMSP\quarantine
   * "보호된 운영체제 파일 숨기기" 해제 및 "숨김 파일, 폴더 및 드라이브 표시"를 체크하여야 합니다.

### 임시 조치 가이드

1\. 삭제

* Vaccine Agent 비활성화 절차 > 백신 Agent 삭제 가이드에 따라 백신을 임시로 삭제합니다.

2\. 분석파일 전달

* 재발 방지를 위한 원인분석을 위해 다음 경로의 파일을 수집하여 고객센터로 분석을 요청합니다.
   * 리눅스
      * /opt/ds_agent/dsa_control -d 실행
      * /var/opt/ds_agent/diag/랜덤10자리숫자.zip 파일 분석 요청
   * 윈도우
      * C:\Program Files\Trend Micro\Deep Security Agent\dsa_control -d 실행
      * C:\Program Files\Trend Micro\Deep Security Agent\diag\랜덤10자리숫자.zip 파일 분석 요청
* 상세한 분석을 위해 문제발생 상황에서 디버깅 수행후 생성된 파일을 추가로 요청할 수 있습니다.
### Image 복제시 사용 가이드

Vaccine Agent가 포함된 Private Image 기반 Instacne 생성시 백신 사용 가이드입니다.

* Instance에 접속하여 각각의 해당하는 스크립트를 생성 및 실행하여 설치합니다.
* Vaccine Agent 활성화 가이드에 따라 서비스 화면에서 새로고침 및 사용시작을 통해 사용이 가능합니다.

※ 주의사항: 스크립트 내용중 "group:앱키"의 앱키는 서비스 화면의 URL & Appkey 메뉴내 Appkey 값으로 변경해야 합니다.
※ 주의사항: 사용을 원치 않는 복제 Instance는 불필요한 리소스가 낭비되지 않도록 설치된 Agent 삭제를 권고 드립니다.

1\. 리눅스 계열 Agent 스크립트

```
#!/bin/bash
IP=`ifconfig eth0 | grep -w -o '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}' | head -1`
HOSTNAME=`hostname`
/opt/ds_agent/dsa_control -r
/opt/ds_agent/dsa_control -a dsm://106.249.21.88:4120/ "group:앱키" "displayname:$IP" "hostname:$HOSTNAME"
```

2\. 윈도우 계열 Agent 스크립트

```
@echo off
FOR /F "tokens=1" %%a IN ('powershell -Command "((Get-WmiObject win32_networkadapterconfiguration | select ipaddress) | findstr .*[0-9].\.).Split(',')[0].Split('{')[-1]"') DO set IP=%%a
"%PROGRAMFILES%\Trend Micro\Deep Security Agent\dsa_control" -r | "%PROGRAMFILES%\Trend Micro\Deep Security Agent\dsa_control" -a dsm://106.249.21.88:4120/ "group:앱키" "displayname:%IP%"
```

### Auto Scale 사용 가이드
Auto Scale 기능을 활용하여 기본 Image 와 Vaccine Agent가 포함된 복제 Image 기반 Instacne 생성시 백신 사용 가이드입니다. 

* Auto Scale > Instance Template > 예약 스크립트에 각각의 해당하는 스크립트를 입력하여 템플릿 생성 및 Scaling Group 을 사용합니다.
* Vaccine Agent 활성화 가이드에 따라 서비스 화면에서 새로고침 및 사용시작을 통해 사용이 가능합니다.

※ 주의사항: 스크립트 내용중 "group:앱키"의 앱키는 서비스 화면의 URL & Appkey 메뉴내 Appkey 값으로 변경해야 합니다.
1\. Linux - 기본 Image
```
서비스 화면에서 기본으로 제공되는 스크립트를 복사하기 버튼으로 메모리에 복사한뒤 예약 스크립트에 입력하여 사용합니다.
```
2\. Linux - 복제 Image
```
#!/bin/bash
IP=`ifconfig eth0 | grep -w -o '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}' | head -1`
HOSTNAME=`hostname`
/opt/ds_agent/dsa_control -r
/opt/ds_agent/dsa_control -a dsm://106.249.21.88:4120/ "group:앱키" "displayname:$IP" "hostname:$HOSTNAME"
```
3\. Windows - 기본 Image
```
서비스 화면에서 기본으로 제공되는 스크립트를 복사하기 버튼으로 메모리에 복사한뒤 예약 스크립트에 입력하여 사용합니다.
```
4\. Windows - 복제 Image
```
@echo off
FOR /F "tokens=1" %%a IN ('powershell -Command "((Get-WmiObject win32_networkadapterconfiguration | select ipaddress) | findstr .*[0-9].\.).Split(',')[0].Split('{')[-1]"') DO set IP=%%a
"%PROGRAMFILES%\Trend Micro\Deep Security Agent\dsa_control" -r | "%PROGRAMFILES%\Trend Micro\Deep Security Agent\dsa_control" -a dsm://106.249.21.88:4120/ "group:앱키" "displayname:%IP%"
```

## 운영 문의

### 문의 대상

1\. 특정 파일 및 폴더 예외처리
2\. Agent 설치 실패 문의
3\. 백신 이벤트 탐지 관련 문의
4\. 정상 파일 오진 신고 및 복원 관련 문의
5\. 백신으로 인한 Instance 오동작 조치 및 원인분석 관련 문의

### 문의 방법

1\. 문의방법: 고객센터 > 1:1 문의
2\. 대응시간: 평일 09:00~18:00
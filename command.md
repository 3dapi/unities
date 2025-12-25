# Powershell
## rename
``` powershell
  dir | Rename-Item -NewName {$_.name -replace "source", "target"}
```
# window command
## 일반
## 일반
 - control : 제어판
 - Access.cpl : 내게 필요한 옵션
 - appwiz.cpl : 프로그램 추가/제거
 - bthprops.cpl : 블루투스장치설정
 - desk.cpl : 디스플레이 등록정보
 - firewall.cpl : Windows방화벽
 - hdwwiz.cpl : 새하드웨어추가마법사
 - inetcpl.cpl : 인터넷 등록정보
 - intl.cpl : 국가 및 언어옵션
 - irprops.cpl : 적외선포트 설정
 - joy.cpl : 게임컨트롤러
 - main.cpl : 마우스등록정보
 - mmsys.cpl : 사운드및 오디오장치등록정보
 - ncpa.cpl : 네트워크연결
 - netsetup.cpl : 네트워크설정마법사
 - nusrmgr.cpl : 사용자계정
 - nwc.cpl : 네트워크 게이트웨이
 - odbccp32.cpl : ODBC데이터원본 관리자
 - powercfg.cpl : : 전원옵션 등록정보
 - sysdm.cpl : 시스템등록정보
 - telephon.cpl : 전화및모뎀 옵션 : 
 - timedate.cpl : 날짜 및 시간 등록정보
 - wscui.cpl : Windows 보안센터
 - wuaucpl.cpl : 자동업데이트
 - Sapi.cpl : 텍스트 음성 변환설정
 - control Admintools : 관리도구
 - control Folders : 폴더옵션
 - control Userpasswords : 사용자 계정


## 관리콘솔 명령어
 - certmgr.msc : 인증서
 - ciadv.msc : 인덱싱서비스
 - ntmsmgr.msc : 이동식저장소
 - ntmsoprq.msc : 이동식저장소 운영자 요청
 - secpol.msc : 로컬보안정책
 - wmimgmt.msc : WMI(Windows Management Infrastructure)
 - compmgmt.msc : 컴퓨터 관리
 - devmgmt.msc : 장치관리자
 - diskmgmt.msc : 디스크 관리
 - dfrg.msc : 디스크 조각모음
 - eventvwr.msc : 이벤트 뷰어
 - fsmgmt.msc : 공유폴더
 - gpedit.msc : 로컬 컴퓨터 정책
 - lusrmgr.msc : 로컬 사용자 및 그룹
 - perfmon.msc : 성능모니터뷰
 - rsop.msc : 정책의 결과와 집합
 - secpol.msc : 로컬 보안설정
 - services.msc : 서비스
 - C:\WINDOWS\system32\Com\comexp.msc : 구성요소서비스
 - C:\WINDOWS\Microsoft.NET\Framework\v1.1.4322\mscorcfg.msc : .NET Configuration 1.1
 - 기타 실행 명령어
 - cmd : 도스명령프롬프트 실행,  단, 윈98은 command
 - shutdown -i : GUI화면으로 시스템 종료, 재부팅 가능
 - shutdown -a : 종료 설정 중지
 - netstat : 인터넷 접속 상황
 - ipconfig /all : ip주소,게이트웨이,서브넷마스크, DNS서버주소,physical주소
 - dxdiag : 다이렉트 - X 상태 정보 화면
 - cleanmgr : 디스크 정리
 - regedit  : 레지스트리 편집기
 - netsetup : 네트워크 설정 마법사
 - calc : 계산기
 - charmap : 문자표
 - pbrush , mspaint  : 그림판
 - cleanmgr : 디스크정리
 - clipbrd : 클립보드에 복사된 내용 표시
 - control : 제어판
 - dxdiag : 다이렉트X 진단도구 및 그래픽과 사운드의 세부정보를 보여줌
 - eudcedit  : 용자 정의 문자 편집기
 - explorer : 탐색기
 - magnify : 돋보기
 - osk : 화상키보드
 - winmine : 지뢰찾기
 - sndrec32 녹음기
 - wordpad : 워드패드
 - sndvol32 : 시스템 사운드 등록정보,볼륨조절
 - sysedit : autoexec.bat, config.sys, win.ini, system.ini 시스템구성편집기
 - systray : 사운드 볼륨설정 노란색 스피커 아이콘을 트라이목록에 띄움
 - mobsync : 동기화
 - msconfig : 시스템 구성요소 유틸리티
 - msinfo32 : 시스템정보
 - mstsc : 원격 데스크톱 연결
 - netstat -na : 현재 열린포트와 TCP/IP 프로토콜정보를 보여줌, 열린포트로 트라이목마형 바이러스 침투 유무확인가능
 - notepad : 메모장
 - wab : 주소록
 - ntbackup : 백업 및 복원 마법사
 - ping 사이트주소 : 핑테스트 해당 사이트의 인터넷연결 유무 확인
 - sfc : 시스템 파일 검사기. 시스템 파일을 검사한후 깨지거난 손실된 파일을 원본 압축파일에서 찾아서 복원시켜줌 . 단, 윈2000에서는 cmd실행 후 sfc사용 - 마지막 설정된 값을 다음 윈도우부팅시 곧바로 실행됨[수정]
 - telnet open 사이트주소 : 텔넷접속명령어
 - tourstart : 윈도우 기능안내 html 문서표시
 - winipcfg : 인터넷에 접속된 자신의 아이피 주소를 보여줌) 단, 윈2000은 ipconfig로 변경됨
 - winver : 윈도우 버전확인
 - wmplayer : 윈도우 미디어 플레이어
 - wupdmgr : 윈도우업데이트
 - 


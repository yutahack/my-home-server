# my-home-server

## 홈서버는 갑자기 왜?
### 기존 NAS 업그레이드 및 대체
 - 기존에 사용하던 Synology DS412+의 성능 부족. 정말 파일 저장 역할 밖에 못할 정도
 - RAM을 4GB로 업그레이드 하였으나 Atom이라는 CPU의 한계에 부딪힘
 - 나 혼자 쓰는 작은 서비스 운영을 위해 Docker를 돌리면 치솟는 CPU 사용률

### 1인 프로젝트 운영을 위한 서버 역할
- 간단한 서비스 제작 및 스토어를 통한 배포 및 운영을 목표
- MSA 학습용

### 개발 테스트베드 환경 구축
- 오픈소스 등 새로운 기술을 테스트하기위한 환경 구축
- VSCode 원격 개발 환경 구축. 폰/테블릿/노트북만 있으면 언제 어디서나 개발 가능

### 원격 데스크탑 환경 구축 (RDP)
- 외부에서 급하게 Windows 10 환경이 필요할 때 접속할 수 있는 환경이 필요하였음

### 스마트홈 구축을 위한 사전 준비
- 각종 IoT 센서, CCTV 연동을 위한 환경 구축

### 취미 만들기
- 퇴근 후 & 주말 취미 (사실 이게 가장 큼)



## 서버 선정을 어떻게 할까
### 후보1. HP ProLiant MicroServer Gen10 Plus (신품)
 - 최신형, 케이스 모양도 가장 이쁘고 맘에 든다
 - Xeon E2220 + 16GB + iLO 포함 시 120~150만원
 - Gen8등 구세대에 비하면 여러 기능이 빠지거나 다운그레이드가 되었다고 함
 - 인증되지 않은 SSD를 SATA케이블에 직접 물리면 CPU 팬이 폭주하는 등 이슈 보유
	 - PCIe슬롯에 SATA카드/NVMe카드를 꽂거나, PCIe SSD를 이용하여 우회 가능?
 - 전원 어댑터 별도. 최대 용량 180W
 - 직구는 찾아봤는데 현재 재고가 없는 것 같음 (2022-08-03)

### 후보2. HP ProLiant MicroServer Gen8 (중고)
 - 큐브형태 모양
 - Xeon E1220(1230) + 16GB + iLO(기본) 탑재 모델이 중고로 40만원 선
 - Gen10 Plus에 비하면 여러 기능이 빠지기 전 모델이라 당시 인기가 많았다고 함
 - 5~6년전 모델이라 연식이 조금 걱정

### 후보3. Z240 베어본 + 직접 구성 (중고)
 - Z240 베어본 10만원 선. (케이스+메인보드+파워 구성)
 - 6-7세대 Core i5 6~10만원, DDR4 메모리 ~10만원
 - 타워형 케이스로 공간을 차지하는 편
 - 저렴하게 입문 가능. 일반 PC와 구성이 동일하며 자유자재로 커스텀 가능
 - 내장 LAN포트가 하나밖에 없음. 별도 랜카드 추가 필요할 듯


## 예상 구성
### OS
 - VMware ESXi
	 - OPNsense (Firewall OS)
	 - Xpenology DSM xxx
	 - Windows 10
	 - Ubuntu 20.04

### UPS
 - APC

### 네트워크
 - Switch: 
	 - HP

1. vagrant로 가상 서버 구축 실습
	- vagrant는 커맨드로 가상 머신을 설치, 삭제와 같은 동작을 제어함
	- vagrant 다운로드
	- vagrant cloud에서 ubuntu 20.04LTS 다운로드
		- cmd 창에 커맨드를 입력해서 다운로드
		- ![image](https://github.com/newdoin/Metanet-Study-Material/assets/121351760/96e228b5-3413-4b67-8490-e9884b28f6bc)
			- 명령을 실행하는 Vagrantfile이 생성되는데 이걸로 가상 서버의 설정이 가능함
				- 사용 포트
				- 메모리 크기
				- 업데이트 진행 여부
				- ...
	- virtual box 다운로드
		- 익스텐션 다운로드
	- "vagrant ssh" 명령어로 가상 서버에 접속
		- 비밀번호 입력없이 바로 접속됨
		- 키가 등록되어 있기 때문!
	- "sudo apt install apache2"로 apache2 서버 설치
		- sudo systemctl status apache2.service 로 서버 동작 상태 확인
		- curl localhost로 실행 중인 서버 내용 확인
	- "scp 파일명" 으로 ssh 접속한 서버 간 데이터 송수신이 가능함
	- ssh-keygen
		- ssh-copy-id
	- sed 명령어로 sshd-config 파일을 수정
		- ssh 접속 시 비밀번호 입력 방식으로 접속하도록 수정
		- Vagrantfile에 쉘 스크립트로 작성하여 vagrant 가동 시 수행되도록 함
2.  네임 서버 설치 및 운영
	- 도메인 이름 체계
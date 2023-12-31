1. aws cloud9 실습
	- cloud9 생성
	- nginx로 docker 컨테이너 배포
		- 인바운드 규칙 설정
	- ec2에서 볼륨 추가 연결
		- 가용 영역 맞춤
		- 추가된 것을 확인 후 강제 분리하여 삭제
	- 컨테이너 조회 및 삭제
2. 운영체제 종류 및 특징
	- 유닉스 - 성능이 좋아야 하는 환경에서 주로 사용했었으나, 리눅스로 다운사이징이 성공적으로 이루어지면서 리눅스로 많이 전환됨
	- 리눅스 - 오픈소스로 가볍고 대부분 무료임, 레드햇 또는 데비안 계열로 나뉨
		- 유상지원서비스가 필요한 경우 레드햇, 그렇지 않으면 데비안을 선택함
		- 데비안 계열의 점유율이 높음(비용면에서도 이점, 도커 이미지도 대부분 우분투임)
		- 레드햇 계열 중 무료인 CentOS의 이슈에 대해 살펴봄
			- CentOS의 지원 정책이 바뀌면서 rocky linux vs CentOs Stream의 대립 관계가 형성됨.
			- 또는 Ubuntu로의 전환도 고려되고 있는 상황
	- 윈도우 - GUI를 따르고 있어 접근성이 좋음, 윈도 서버에서 실행되는 SW를 사용해야 하는 경우에 사용하나 비용이 비쌈
3. 네트워크 장비 및 기본 용어
	- 라우터
		- ping을 통해 외부 통신 가능 확인
		- 라우팅 테이블 변경 실습
	- 스위치
		- L2: 업무용 스위칭 허브
		- L3: 라우터 기능이 추가된 L2 스위치
		- L4/L7: 로드 밸런싱 기능이 추가된 L3 스위치
	- 네트워크 토폴러지 패턴
		- 2계층 구조
		- 3계층 구조
		- 패브릭 구조
	- **TCP/IP vs OSI 7 Layer**
	- TCP/UDP
		- 3 way handshake
4. 스토리지 장비 및 특징
	- DAS(Direct Attached Storage)
	- NAS(Network Attached Storage)
	- SAN(Stroage Area Network)
	- 핫스페어 디스크
	- 스토리지 고급 기능
		- 씬 프로비저닝(Thin Provisioning)
		- 자동 계층화
		- 스냅샷
		- 디둡(De-duplication)
	- AWS S3
		- 웹서비스 인터페이스를 이용하여 웹에서 언제 어디서나 원하는 양의 데이터를 저장하고 검색할 수 있는 스토리지
		- 버킷과 객체로 나뉘며, 저장하고자 하는 모든 요소는 하나의 객체로 저장되고, 오브젝트를 담는 곳이 바로 버킷!
		- S3 자체는 글로벌 서비스이지만 버킷을 생성할 때에는 리전을 선택해야 함 
			- 버킷의 이름은 반드시 고유해야 함
			- 다른 계정에서는 접근 불가함
		- 객체는 객체 데이터와 메타 데이터로 나누며, 각자의 고유한 URL을 가짐
			- S3에 업로드 되는 1개의 데이터를 객체라고 함
			- 객체의 크기가 매우 클 경우 멀티파트 업로드를 통해 신속하게 업로드 가능
		- 데이터의 마이그레이션에 아주 많이 사용됨
		- 수명주기 관리
		- 정적 웹 사이트 호스팅
		- 전송 속도 향상
			- S3로 직접 업로드 하는 것이 아닌 가장 가까운 Edge Location으로 전송하고 아마존 백본 네트워크를 통해 S3로 도달
		- S3 업로드 속도 비교 사이트
			- https://s3-accelerate-speedtest.s3-accelerate.amazonaws.com/en/accelerate-speed-comparsion.html
		- 실습
			- Upload
			- Local 파일을 백업
			- 정적 웹 사이트 호스팅
5. 클라우드 자원 관리
	- AWS CLOUDWATCH: 온프레미스 시스템들의 통합 관리가 가능함
		- Cloudwatch Agent
		- Cloudwatch Logs
		- Cloudwatch Events
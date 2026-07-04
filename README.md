# ☁️ AWS Cloud Fundamentals
## : 클라우드 인프라 기초 및 고가용성 아키텍처 설계

AWS의 핵심 글로벌 인프라(Region, AZ) 구조를 이해하고, 백엔드 아키텍처의 탄탄한 기반이 되는 네트워크(VPC) 설계부터 고가용성 인프라(ELB/Auto Scaling), 객체 스토리지(S3), 권한 관리(IAM) 및 서버리스(Lambda) 기초까지 유기적으로 학습하고 실습한 저장소.

## 📅 교육 기간
- 2026년 6월 23일 ~ 2026년 6월 26일 (총 3일간, OT 포함)

---

## 📂 디렉토리 구조 및 학습 로드맵

### ⚙️ [0일차] 0-OT-cloud-infra-computing
- **클라우드 컴퓨팅 개요:** 클라우드의 정의, 전통적인 온프레미스(On-Premise) 환경과의 차이점 및 장점 학습
- **인프라 기초:** 백엔드 개발자 관점에서의 가상화 기술 및 클라우드 인프라의 전반적인 개념 이해

### 🌐 [1일차] Day1-Network-Compute-Storage
> 독립된 가상 네트워크망을 설계하고, 서브넷 격리 구조 및 다중 방화벽 계층을 통한 인프라 보안의 기초를 확립한 단계
- **[01_AWS_GlobalInfrastructure_VPC](./Day1-Network-Compute-Storage/01_AWS_GlobalInfrastructure_VPC/)**
  - 서울 리전 기반 VPC 생성 및 CIDR 블록(`10.0.0.0/16`)을 활용한 IP 대역 분할 설계
  - Public Subnet(`10.0.1.0/24`)과 Private Subnet(`10.0.2.0/24`)의 라우팅 테이블 분리 규칙 수립
  - Private 인스턴스(`vm01`)의 안전한 패치 업데이트를 위한 NAT 게이트웨이 아웃바운드 라우팅 연동
- **[02_VPC_Security_nACL_SG](./Day1-Network-Compute-Storage/02_VPC_Security_nACL_SG/)**
  - 인스턴스 레벨 방화벽인 보안 그룹(SG, Stateful)의 인바운드/아웃바운드 트래픽 흐름 제어 실습
  - 서브넷 레벨 관문 방화벽인 네트워크 ACL(nACL, Stateless)의 명시적 차단(Deny) 규칙 번호 우선순위 검증

### 🚀 [2일차] Day2-Storage-ELB-Security
> 가상 서버 이중화와 로드 밸런싱을 통한 탄력적 인프라를 검증하고, 스토리지 호스팅 트러블슈팅 및 클라우드 관리 체계를 학습한 단계
- **[01_EC2_AMI_HighAvailability](./Day2-Storage-ELB-Security/01_EC2_AMI_HighAvailability/)**
  - 하이퍼바이저 기반 가상화 환경에서 Nginx 웹 서버(1번) 구축 및 가동
  - 현재 상태를 보존하는 스냅샷인 커스텀 AMI(Amazon Machine Image) 생성을 통한 2번 웹 서버 신속 복제 체계 구축
- **[02_ALB_AutoScaling_CloudWatch](./Day2-Storage-ELB-Security/02_ALB_AutoScaling_CloudWatch/)**
  - 외부 트래픽을 분산 수용하는 ALB(Application Load Balancer) 연동 및 보안 그룹 체이닝 구조 설계
  - 임계값(CPU 50%) 기반 CloudWatch 경보와 SNS 이메일 알림 연동 및 `stress` 툴을 통한 동적 수평 확장(Scale-out, 최대 5대) 매커니즘 최종 검증
- **[03_S3_IAM_Serverless](./Day2-Storage-ELB-Security/03_S3_IAM_Serverless/)**
  - S3 정적 웹 호스팅 구동 과정에서 발생한 부트스트랩 테마(CSS/Assets) 경로 깨짐 현상 분석 및 트러블슈팅 완료
  - 최소 권한 원칙(Least Privilege)에 따른 IAM User/Group/Policy 관리 및 EC2-S3 간 임시 권한(Role) 위임 방식 이해
  - S3 이벤트를 트리거로 작동하는 비용 효율적 서버리스(AWS Lambda) 아키텍처의 효용성 분석

---

## 🛠️ 핵심 실습 기술 스택 & 키워드

| 분류 | AWS 서비스 및 핵심 개념 |
| :--- | :--- |
| **Network** | VPC, Public/Private Subnet, Route Table, Internet Gateway, **nACL vs Security Group** |
| **Compute & Scaling** | Amazon EC2, AMI, ALB, CloudWatch Alert, **Auto Scaling Group (Scale-out)** |
| **Storage & Serverless**| **Amazon S3 (Static Web Hosting)**, S3 Glacier, **AWS Lambda (Serverless)** |
| **Security & Management** | AWS IAM (Role, Policy, Least Privilege), AWS SNS |

---

## 💡 학습 포인트 및 트러블슈팅 회고
- **탄력성(Elasticity) 체감:** 단순히 서버 사양을 높이는 수직 확장(Scale-up)이 아닌, 트래픽 부하 상태를 CloudWatch로 모니터링하며 시스템이 스스로 인스턴스를 늘리는 수평적 확장(Scale-out)을 제어하며 클라우드의 진정한 가치를 배웠습니다.
- **실전 트러블슈팅 역량:** S3 웹 호스팅 시 발생했던 `404 NoSuchKey` 에러와 리소스 경로 오류를 브라우저 개발자 도구(F12) 콘솔 로그 분석을 통해 인지하고, 버킷 루트 경로의 파일 배치를 재정렬하며 인프라 단의 문제 해결력을 길렀습니다.
- **백엔드 개발자로서의 관점 확장:** 네트워크 격리(VPC)와 최소 권한 제어(IAM)를 바탕으로 한 인프라 보안의 중요성을 깨달았으며, 24시간 가동 서버가 아닌 비용 효율적인 서버리스(Lambda) 설계 방식을 고민해 보는 계기가 되었습니다.
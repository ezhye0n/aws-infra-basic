# ☁️ AWS Cloud Fundamentals: 클라우드 인프라 기초 과정
Hands-on labs and summaries for AWS Cloud Fundamentals (VPC, EC2, S3, ELB).  Learning and practicing the core AWS infrastructure for backend architecture.

AWS의 핵심 글로벌 인프라(Region, AZ)를 이해하고, 백엔드 아키텍처의 기반이 되는 네트워크(VPC), 컴퓨팅(EC2), 스토리지(S3, EBS, EFS) 및 보안(IAM) 서비스를 학습하고 실습한 저장소입니다.

## 📅 교육 기간
- 2026년 6월 25일 ~ 2026년 6월 26일 (2일간)

## 📝 주요 학습 내용 & 실습 항목

### 1일차: Global Infra, Network, Computing & Storage
- **Network (VPC):** Region과 AZ 인프라 구조 이해, VPC 및 Public/Private Subnet 설계를 통한 격리된 네트워크 환경 구축
- **Computing (EC2):** 가상 머신(EC2) 인스턴스 생성 및 웹 서버(Apache/Nginx 등) 구성, AMI(Amazon Machine Image)를 활용한 서버 복제 실습
- **Storage (S3):** 객체 스토리지 S3의 특징 이해, S3 버킷 생성 및 정적 웹 서비스(Static Web Hosting) 구동

### 2일차: Advanced Storage/Network, Security & Management
- **Storage:** 블록 스토리지(EBS)와 파일 스토리지(EFS)의 아키텍처별 특징 및 용도 비교
- **Advanced Network:** 서비스 고가용성(High Availability) 및 부하 분산을 위한 ELB(Elastic Load Balancer) 구성, 트래픽 기반 인프라 자동 확장을 위한 AutoScaling 설정
- **Security & Management:** AWS 공동 책임 모델과 IAM(Identity and Access Management)을 통한 계정/권한 관리, CloudWatch(모니터링) 및 CloudTrail(활동 감사)을 통한 운영 관리 기초 학습

## 🛠️ 실습 아키텍처 키워드
- VPC / Subnet / Route Table / Internet Gateway
- EC2 / AMI / Key Pair / Web Server
- Amazon S3 (Static Web Hosting)
- ELB (Application Load Balancer) / AutoScaling Group
- AWS IAM (Role, Policy) / CloudWatch / CloudTrail

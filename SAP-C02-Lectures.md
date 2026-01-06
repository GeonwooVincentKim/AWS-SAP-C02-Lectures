AWS Certified Solutions Architect - Professional (SAP-C02) Study Notes
Based on: Ultimate AWS Certified Solutions Architect Professional Slides (v35) Last Updated: 2026-01 Author: [Your Name / 42 Tokyo Student]

📚 Introduction / 概要 / 개요
🇺🇸 English
This repository contains study notes for the AWS SAP-C02 exam. It covers advanced networking, identity management, complex organization design, and migration strategies based on the SAP-C02 curriculum.

🇯🇵 日本語
本リポジトリは、AWS SAP-C02 試験のための学習ノートです。SAP-C02 カリキュラムに基づき、高度なネットワーキング、ID管理、複雑な組織設計、移行戦略などを網羅しています。

🇰🇷 한국어
이 저장소는 AWS SAP-C02 자격증 시험을 위한 학습 노트입니다. SAP-C02 커리큘럼을 기반으로 고급 네트워킹, 자격 증명 관리, 복잡한 조직 설계 및 마이그레이션 전략을 다룹니다.

📑 Table of Contents / 目次 / 목차
Identity & Organizations

Advanced Networking & Connectivity

Compute, Auto Scaling & Load Balancing

Storage (S3, EBS, EFS, FSx)

Databases & Analytics

Serverless & Containers

Migration & Disaster Recovery

Security & Cost Optimization

1. Identity & Organizations
🇺🇸 English
AWS Organizations: Managing multiple accounts using OUs (Organizational Units) and SCPs (Service Control Policies).

AWS IAM Identity Center (Successor to AWS SSO): Centralized login management and integration with external IdPs (Active Directory, Okta) via SAML 2.0.

AWS RAM (Resource Access Manager): Sharing subnets and Transit Gateways across accounts.

🇯🇵 日本語
AWS Organizations: OU (組織単位) と SCP (サービスコントロールポリシー) を使用したマルチアカウント管理。

AWS IAM Identity Center (旧 AWS SSO): IDの一元管理および外部IdP (Active Directory, Okta) との SAML 2.0 連携。

AWS RAM (Resource Access Manager): アカウント間でのサブネットや Transit Gateway の共有。

🇰🇷 한국어
AWS Organizations: OU(조직 단위)와 SCP(서비스 제어 정책)를 활용한 다중 계정 관리 및 제어.

AWS IAM Identity Center (구 AWS SSO): 중앙 집중식 로그인 관리 및 SAML 2.0을 통한 외부 IdP(AD, Okta 등) 연동.

AWS RAM (Resource Access Manager): 서브넷, Transit Gateway 등을 계정 간에 공유.

2. Advanced Networking & Connectivity
🇺🇸 English
VPC Peering vs Transit Gateway: Limitations of peering (non-transitive) vs. Hub-and-Spoke model using TGW.

VPC Endpoints: Interface Endpoints (PrivateLink) vs. Gateway Endpoints (S3, DynamoDB only).

Hybrid Networking:

Site-to-Site VPN: Quick setup, encrypted, over public internet.

Direct Connect (DX): Dedicated physical connection, consistent performance, high security.

Direct Connect Gateway: Connecting to multiple VPCs across different regions.

🇯🇵 日本語
VPC ピアリング vs Transit Gateway: ピアリングの制約 (推移的ルーティング不可) と TGW を使用したハブ＆スポークモデル。

VPC エンドポイント: インターフェイスエンドポイント (PrivateLink) と ゲートウェイエンドポイント (S3, DynamoDB のみ)。

ハイブリッドネットワーキング:

Site-to-Site VPN: 短期間で構築可能、暗号化あり、インターネット経由。

Direct Connect (DX): 物理専用線、安定したパフォーマンス、高いセキュリティ。

Direct Connect Gateway: 異なるリージョンの複数の VPC への接続。

🇰🇷 한국어
VPC Peering vs Transit Gateway: 피어링의 한계(Transitive Routing 불가)와 TGW를 이용한 허브 앤 스포크 모델 비교.

VPC Endpoints: 인터페이스 엔드포인트(PrivateLink)와 게이트웨이 엔드포인트(S3, DynamoDB 전용)의 차이.

하이브리드 네트워킹:

Site-to-Site VPN: 빠른 구축, 암호화 지원, 공용 인터넷 사용.

Direct Connect (DX): 물리적 전용선 사용, 일관된 성능 및 높은 보안.

Direct Connect Gateway: 서로 다른 리전에 있는 여러 VPC와 연결.

3. Compute, Auto Scaling & Load Balancing
🇺🇸 English
Auto Scaling Strategies: Dynamic Scaling vs. Predictive Scaling. Handling scale-in protection.

Load Balancers:

ALB: Layer 7, Path-based routing, OIDC integration.

NLB: Layer 4, High throughput, Static IP support.

GWLB: Layer 3, deploying 3rd party firewalls (Geneve protocol).

🇯🇵 日本語
Auto Scaling 戦略: 動的スケーリング vs 予測スケーリング。スケールイン保護の設定。

ロードバランサー:

ALB: レイヤー 7、パスベースルーティング、OIDC 統合。

NLB: レイヤー 4、高スループット、静的 IP サポート。

GWLB: レイヤー 3、サードパーティ製ファイアウォールの展開 (Geneve プロトコル)。

🇰🇷 한국어
오토 스케일링 전략: 동적 스케일링 vs 예측 스케일링. 스케일 인 보호 설정.

로드 밸런서:

ALB: L7 계층, 경로 기반 라우팅, OIDC 통합 지원.

NLB: L4 계층, 초고속 처리량, 고정 IP(Static IP) 지원.

GWLB: L3 계층, 타사 방화벽 어플라이언스 배포 (Geneve 프로토콜).

4. Storage (S3, EBS, EFS, FSx)
🇺🇸 English
S3 Storage Classes: Standard, Intelligent-Tiering, Glacier (Instant vs Flexible vs Deep Archive).

S3 Security: Bucket Policies, ACLs, Encryption (SSE-S3, SSE-KMS, SSE-C), Object Lock (WORM).

FSx Family:

FSx for Windows: SMB protocol, AD integration.

FSx for Lustre: High-performance computing (HPC), S3 integration.

🇯🇵 日本語
S3 ストレージクラス: Standard, Intelligent-Tiering, Glacier (Instant, Flexible, Deep Archive).

S3 セキュリティ: バケットポリシー, ACL, 暗号化 (SSE-S3, SSE-KMS, SSE-C), Object Lock (WORM).

FSx ファミリー:

FSx for Windows: SMB プロトコル, Active Directory 統合。

FSx for Lustre: ハイパフォーマンスコンピューティング (HPC), S3 統合。

🇰🇷 한국어
S3 스토리지 클래스: Standard, Intelligent-Tiering, Glacier(Instant, Flexible, Deep Archive) 비교.

S3 보안: 버킷 정책, ACL, 암호화 방식(SSE-S3, SSE-KMS, SSE-C), 객체 잠금(WORM).

FSx 패밀리:

FSx for Windows: SMB 프로토콜, AD 통합 지원.

FSx for Lustre: 고성능 컴퓨팅(HPC) 용도, S3와 데이터 연동.

5. Databases & Analytics
🇺🇸 English
Amazon Aurora: Multi-Master, Global Database, Serverless v2.

DynamoDB: Global Tables (Active-Active), DAX (Caching), Streams.

Redshift: Data Warehousing, Spectrum (Querying S3 directly).

Kinesis: Data Streams (Real-time) vs. Data Firehose (Delivery to S3/Redshift/ElasticSearch).

🇯🇵 日本語
Amazon Aurora: マルチマスター, グローバルデータベース, Serverless v2.

DynamoDB: グローバルテーブル (Active-Active), DAX (キャッシング), Streams.

Redshift: データウェアハウス, Spectrum (S3 直接クエリ).

Kinesis: Data Streams (リアルタイム) vs Data Firehose (S3/Redshift/ElasticSearch への配信).

🇰🇷 한국어
Amazon Aurora: 멀티 마스터, 글로벌 데이터베이스, Serverless v2.

DynamoDB: 글로벌 테이블(Active-Active), DAX(캐싱), 스트림(Streams).

Redshift: 데이터 웨어하우스, Spectrum(S3 데이터 직접 쿼리).

Kinesis: Data Streams(실시간 처리) vs Data Firehose(S3/Redshift/ElasticSearch로 적재).

6. Serverless & Containers
🇺🇸 English
Lambda: Layers, Versions & Aliases, Provisioned Concurrency (Solving cold starts).

API Gateway: Throttling, Caching, Usage Plans, API Keys.

Containers: ECS (EC2 vs Fargate), EKS (Kubernetes), ECR (Image Registry).

🇯🇵 日本語
Lambda: Layers, バージョンとエイリアス, プロビジョニングされた同時実行 (コールドスタート対策).

API Gateway: スロットリング, キャッシング, 使用量プラン, API キー.

コンテナ: ECS (EC2 vs Fargate), EKS (Kubernetes), ECR (イメージレジストリ).

🇰🇷 한국어
Lambda: 계층(Layers), 버전 및 별칭, 프로비저닝된 동시성(콜드 스타트 해결).

API Gateway: 스로틀링, 캐싱, 사용량 계획, API 키 관리.

컨테이너: ECS(EC2 vs Fargate 모드), EKS(쿠버네티스), ECR(이미지 레지스트리).

7. Migration & Disaster Recovery
🇺🇸 English
Migration Strategies (The 6/7 Rs): Rehost (Lift & Shift), Replatform, Refactor, Repurchase, Retain, Retire.

Data Migration: AWS DataSync (Online), Snow Family (Offline/Large scale).

Database Migration: DMS (Database Migration Service) + SCT (Schema Conversion Tool).

Disaster Recovery (DR): Backup & Restore, Pilot Light, Warm Standby, Multi-Site Active/Active.

🇯🇵 日本語
移行戦略 (6/7 Rs): Rehost (リフト＆シフト), Replatform, Refactor, Repurchase, Retain, Retire.

データ移行: AWS DataSync (オンライン), Snow Family (オフライン/大規模).

データベース移行: DMS (Database Migration Service) + SCT (Schema Conversion Tool).

ディザスタリカバリ (DR): バックアップ＆リストア, パイロットライト, ウォームスタンバイ, マルチサイト Active/Active.

🇰🇷 한국어
마이그레이션 전략 (6/7 Rs): 리호스트(Lift & Shift), 리플랫폼, 리팩터링, 재구매, 유지, 은퇴.

데이터 마이그레이션: AWS DataSync(온라인 전송), Snow Family(오프라인 대용량 전송).

데이터베이스 마이그레이션: DMS(데이터 이동) + SCT(스키마 변환).

재해 복구 (DR): 백업 및 복구, 파일럿 라이트, 웜 스탠바이, 멀티 사이트 액티브/액티브.

8. Security & Cost Optimization
🇺🇸 English
KMS (Key Management Service): Symmetric vs. Asymmetric, Key Rotation, Multi-Region Keys.

Protection: AWS WAF (Layer 7), AWS Shield (DDoS), Firewall Manager.

Cost Optimization:

Savings Plans vs. Reserved Instances.

Cost Explorer & Cost Allocation Tags.

🇯🇵 日本語
KMS (Key Management Service): 対称鍵 vs 非対称鍵, キーローテーション, マルチリージョンキー.

保護サービス: AWS WAF (レイヤー 7), AWS Shield (DDoS対策), Firewall Manager.

コスト最適化:

Savings Plans vs リザーブドインスタンス.

Cost Explorer & コスト配分タグ.

🇰🇷 한국어
KMS (키 관리 서비스): 대칭키 vs 비대칭키, 키 로테이션, 멀티 리전 키.

보호 서비스: AWS WAF(L7 보호), AWS Shield(DDoS 방어), Firewall Manager.

비용 최적화:

Savings Plans vs 예약 인스턴스(RI) 비교.

Cost Explorer 및 비용 할당 태그 활용.

📝 Notes & Tips / メモ & ヒント / 메모 및 팁
Pro Tip: Always consider the trade-off between Cost vs. Performance vs. Availability.

Study Focus: The exam focuses heavily on Hybrid Networking (DX, VPN) and Multi-Account Strategy.

Designed for: AWS SAP-C02 Exam Preparation. Goal: Achieve "Solutions Architect Professional" Certification by 2026.

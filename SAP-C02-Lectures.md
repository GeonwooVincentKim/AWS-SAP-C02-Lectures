# ⚡ AWS Certified Solutions Architect - Professional (SAP-C02)

![AWS SAP](https://img.shields.io/badge/AWS-Solutions_Architect_Professional-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Exam Lang](https://img.shields.io/badge/Exam_Language-English_&_Japanese-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-D--Day_March_2026-blue?style=for-the-badge)

> **Goal:** SAP-C02 Certification (Exam Center in Japan 🇯🇵)
> **Strategy:** Understanding in **Korean**, Memorizing keywords in **English & Japanese**.
> **Note:** Click the `▶` arrows to expand details.

---

## 1. Identity & Organizations (Account Management)

<details>
<summary><strong>📂 1.1 Organizations & SCP (Service Control Policies)</strong></summary>

| Language | Key Concept | Detail |
| :--- | :--- | :--- |
| **🇺🇸 EN** | **SCP (Service Control Policy)** | • Explicit **Deny** wins over Allow.<br>• Does not affect the **Management Account**.<br>• Applied to OUs or Accounts. |
| **🇯🇵 JP** | **SCP (サービスコントロールポリシー)** | • 明示的な **拒否 (Deny)** が許可より優先される。<br>• **管理アカウント (Management Account)** には影響しない。<br>• OU またはアカウントに適用。 |
| **🇰🇷 KR** | **SCP (서비스 제어 정책)** | • 명시적 **거부**가 허용보다 무조건 우선.<br>• **관리 계정**에는 적용되지 않음 (Root 권한).<br>• 권한을 부여하는 게 아니라 **"필터링(막는 것)"**임. |

</details>

<details>
<summary><strong>📂 1.2 Identity Federation (SSO)</strong></summary>

| Language | Key Concept | Detail |
| :--- | :--- | :--- |
| **🇺🇸 EN** | **IAM Identity Center**<br>(formerly AWS SSO) | • Integrates with external IdPs via **SAML 2.0**.<br>• Centralized permission management (Permission Sets). |
| **🇯🇵 JP** | **IAM Identity Center**<br>(旧 AWS SSO) | • **SAML 2.0** 経由で外部 IdP (Active Directory等) と連携。<br>• 権限セットによる集中管理。 |
| **🇰🇷 KR** | **IAM Identity Center** | • **SAML 2.0** 표준으로 외부 자격 증명(AD, Okta) 연동.<br>• 멀티 계정 로그인 허브 역할. |

</details>

---

## 2. Advanced Networking (🔥 Critical)

<details>
<summary><strong>📂 2.1 Connectivity (Peering vs TGW)</strong></summary>

| Keyword | 🇺🇸 English | 🇯🇵 Japanese | 🇰🇷 Korean (Meaning) |
| :--- | :--- | :--- | :--- |
| **Peering** | **Non-transitive** routing.<br>Low latency, 1:1 connection. | **非推移的 (ひすいいてき)** ルーティング。<br>低遅延、1対1接続。 | **전이 안 됨** (A↔B, B↔C여도 A↔C 불가).<br>비용 싸고 빠름. |
| **Transit Gateway** | **Hub-and-Spoke** topology.<br>Supports thousands of VPCs.<br>Transitive routing allowed. | **ハブアンドスポーク** 型トポロジー。<br>数千の VPC をサポート。<br>推移的ルーティングが可能。 | **허브 앤 스포크** 구조.<br>수천 개 VPC 연결, 라우팅 관리 편함.<br>VPN/DX 중앙 집중화. |
| **CIDR** | **Overlapping CIDR** issues.<br>Cannot peer directly. Use PrivateLink or NAT. | **重複する CIDR (CIDR の重複)**。<br>直接ピアリング不可。PrivateLink 等で回避。 | **IP 대역 중복**.<br>피어링 불가. PrivateLink로 해결. |

</details>

<details>
<summary><strong>📂 2.2 VPC Endpoints (PrivateLink)</strong></summary>

| Type | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **Interface** | **ENI** based.<br>Uses Private IP.<br>Accessible via VPN/Peering. | **ENI** ベース。<br>プライベート IP を使用。<br>VPN/ピアリング経由でアクセス **可**。 | **ENI (랜카드)** 방식.<br>유료. 온프레미스/타 VPC에서 접근 **가능**. |
| **Gateway** | **S3 & DynamoDB** only.<br>Route Table target.<br>**Not** accessible via VPN. | **S3 と DynamoDB** のみ。<br>ルートテーブルで制御。<br>VPN 経由アクセス **不可**。 | **S3, DynamoDB** 전용.<br>무료. 라우팅 테이블 수정.<br>외부(VPN)에서 접근 **불가**. |

</details>

<details>
<summary><strong>📂 2.3 Hybrid (Direct Connect & VPN)</strong></summary>

| Language | Concept | Detail |
| :--- | :--- | :--- |
| **🇺🇸 EN** | **Direct Connect (DX)** | • Dedicated connection (No Public Internet).<br>• Takes weeks to setup.<br>• **DX + VPN** = Low cost HA & Encryption. |
| **🇯🇵 JP** | **Direct Connect (DX)** | • 専用線接続 (インターネットを経由しない)。<br>• 開通に数週間かかる。<br>• **DX + VPN** = 低コストでの可用性(HA)と暗号化。 |
| **🇰🇷 KR** | **Direct Connect (DX)** | • 전용 물리 회선 (인터넷 X, 보안 O).<br>• 설치 오래 걸림.<br>• **DX(주) + VPN(백업)** 조합이 국룰. |

</details>

---

## 3. Storage Strategy

<details>
<summary><strong>📂 3.1 S3 Storage Classes</strong></summary>

| Class | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **Intelligent-Tiering** | Auto-tiering based on access patterns.<br>**No retrieval fees**. | アクセスパターンに基づく自動階層化。<br>**取り出し料金なし**。 | 액세스 빈도 따라 자동 이동.<br>**꺼낼 때 비용 0원**. (모니터링 비용만 냄) |
| **Glacier Deep Archive** | Lowest cost.<br>Retrieval: **12h (Std) / 48h (Bulk)**. | 最安コスト。<br>取り出し: **12時間 (標準) / 48時間 (大容量)**。 | 제일 쌈.<br>꺼내는 데 **12~48시간** 걸림. (RTO 고려 필수) |
| **Object Lock** | **WORM** (Write Once Read Many).<br>Compliance Mode: Root cannot delete. | **WORM** (書き込みは一度、読み取りは何度でも)。<br>コンプライアンスモード: ルートでも削除不可。 | **삭제 방지 (WORM)**.<br>컴플라이언스 모드는 루트도 삭제 못 함. |

</details>

<details>
<summary><strong>📂 3.2 FSx Family</strong></summary>

- **FSx for Windows:** SMB, AD Integration (Windows Native).
  - 🇯🇵: Windows ファイルサーバー, AD 統合.
- **FSx for Lustre:** HPC, Machine Learning, Linked with S3.
  - 🇯🇵: 高性能コンピューティング (HPC), S3 連携.
- **FSx for NetApp ONTAP:** Multi-protocol (NFS/SMB), Dedup/Compression.
  - 🇯🇵: マルチプロトコル, 重複排除/圧縮.

</details>

---

## 4. Compute & Load Balancing

<details>
<summary><strong>📂 4.1 ELB & Auto Scaling</strong></summary>

| Language | Concept | Detail |
| :--- | :--- | :--- |
| **🇺🇸 EN** | **Gateway Load Balancer (GWLB)** | • Layer 3 (IP).<br>• Used for **Firewall Appliances**.<br>• Uses **Geneve** protocol (Port 6081). |
| **🇯🇵 JP** | **Gateway Load Balancer (GWLB)** | • レイヤー 3。<br>• **ファイアウォールアプライアンス** 向け。<br>• **Geneve** プロトコルを使用。 |
| **🇰🇷 KR** | **GWLB** | • L3 계층.<br>• 타사 보안 장비(방화벽 등) 앞단에 배치.<br>• Geneve 프로토콜 사용. |

- **Predictive Scaling (予測スケーリング / 예측 스케일링):**
  - Uses Machine Learning to scale *before* traffic spikes.
  - 트래픽 패턴이 주기적일 때 사용 (머신러닝 기반).

</details>

---

## 5. Databases & Analytics

<details>
<summary><strong>📂 5.1 Global Architectures</strong></summary>

| Service | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **Aurora Global** | **Cross-Region Replication** < 1s.<br>Disaster Recovery (DR). | **クロスリージョンレプリケーション** 1秒未満。<br>ディザスタリカバリ (DR)。 | 리전 간 복제 1초 미만.<br>읽기 전용 확장 및 DR 용도. |
| **DynamoDB Global** | **Active-Active** (Multi-Master).<br>Replicates to multiple regions. | **アクティブ/アクティブ** (マルチマスター)。<br>複数リージョンへのレプリケーション。 | **양방향(Active-Active)** 복제.<br>어느 리전에서든 쓰고 읽기 가능. |

</details>

<details>
<summary><strong>📂 5.2 Kinesis Data Streams vs Firehose</strong></summary>

- **Data Streams (データストリーム):**
  - Real-time (リアルタイム), Manual Sharding (シャード管理必要).
  - Data retention (1 day ~ 1 year).
- **Firehose (ファイアホース):**
  - Near Real-time (ほぼリアルタイム), Fully Managed (管理不要).
  - Load data into S3 / Redshift / ElasticSearch (S3等へのデータロード).

</details>

---

## 6. Migration & Disaster Recovery (DR)

<details>
<summary><strong>📂 6.1 DR Strategies (RTO/RPO)</strong></summary>

| Strategy | Cost | RTO (Recovery Time) | Description (KR) |
| :--- | :--- | :--- | :--- |
| **Backup & Restore** | $ (Low) | Hours/Days | 백업만 해둠. 터지면 그때 복구 시작. |
| **Pilot Light** | $$ | Tens of Minutes | 데이터는 동기화, 서버는 꺼둠(혹은 초소형). 터지면 켬. |
| **Warm Standby** | $$$ | Minutes | 서버가 작게 돌아가고 있음. 터지면 스케일 업. |
| **Multi-Site Active/Active** | $$$$ | Real-time (Zero) | 양쪽 다 쌩쌩 돌아감. 제일 비쌈. |

* **🇯🇵 Keywords:** バックアップと復元 / パイロットライト / ウォームスタンバイ / マルチサイト

</details>

<details>
<summary><strong>📂 6.2 The 6 Rs of Migration</strong></summary>

- **Rehost (リホスト):** Lift & Shift. (AWS MGN)
- **Replatform (リプラットフォーム):** Lift & Reshape. (EC2 DB -> RDS)
- **Refactor (リファクター):** Re-architecting. (Monolith -> Microservices)

</details>

---

## 7. Security (KMS)

<details>
<summary><strong>📂 7.1 Key Management Service</strong></summary>

| Feature | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **Multi-Region Keys** | Encrypt in Region A,<br>Decrypt in Region B. | リージョン A で暗号化、<br>リージョン B で復号化。 | 리전 A에서 암호화한 걸<br>리전 B에서 바로 복호화 가능. |
| **Key Rotation** | Automatic (every 1 year).<br>New backing key generated. | 自動ローテーション (1年ごと)。<br>新しいバッキングキーが生成される。 | 1년마다 자동 교체.<br>키 ID는 안 바뀜 (내부 키만 변경). |

</details>

---

---

## 🛠 8. Management & Governance (Automation)

<details>
<summary><strong>📂 8.1 CloudFormation & StackSets</strong></summary>

| Feature | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **StackSets** | Deploy stacks across **multiple accounts & regions**.<br>Target: OUs or Account IDs. | **複数のアカウントとリージョン** にスタックを展開。<br>ターゲット: OU またはアカウント ID。 | **멀티 계정 및 리전**에 한 번에 배포.<br>OU 단위로 자동 배포 가능. |
| **Drift Detection** | Detects manual changes outside of CFN.<br>Ensures IaC integrity. | **ドリフト検出**。<br>CFN 外の手動変更を検出する。<br>IaC の整合性を保証。 | **드리프트(변경) 감지**.<br>누가 콘솔에서 몰래 바꾼 설정 잡아냄. |

</details>

<details>
<summary><strong>📂 8.2 Systems Manager (SSM)</strong></summary>

- **Session Manager:**
  - SSH/Bastion Host 대체. 포트 22번 열 필요 없음 (No open ports).
  - 🇯🇵: ポート開放不要 (No Inbound Rules).
- **Patch Manager:**
  - OS 패치 자동화. Maintenance Windows와 연동.
  - 🇯🇵: パッチ適用 (Patching) の自動化.
- **Parameter Store:**
  - 설정값(Configuration), 비번 저장. (Secrets Manager보다 싸지만 자동 회전 X).
  - 🇯🇵: パラメータストア.

</details>

<details>
<summary><strong>📂 8.3 AWS Config & OpsWorks</strong></summary>

- **AWS Config:**
  - 리소스 변경 이력 추적 & 규정 준수(Compliance) 감시.
  - **Remediation:** 규정 위반 시 자동 수정(SSM Document 실행).
  - 🇯🇵: 構成変更の追跡 (Tracking configuration changes).
- **OpsWorks:**
  - Chef & Puppet (Legacy). 시험에 "Chef/Puppet" 나오면 무조건 OpsWorks.
  - 🇯🇵: Chef や Puppet を使用.

</details>

---

## 🧩 9. Serverless & App Integration

<details>
<summary><strong>📂 9.1 Step Functions (Orchestration)</strong></summary>

| Type | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **Standard** | Long-running (up to 1 year).<br>Exactly-once execution.<br>Checkpointing. | 長時間実行 (最大1年)。<br>正確に1回の実行。<br>チェックポイントあり。 | 장기 실행(최대 1년).<br>안정성 중요. (주문 처리, ETL) |
| **Express** | Short-lived (up to 5 mins).<br>High throughput (IoT, Streaming).<br>At-least-once. | 短時間実行 (最大5分)。<br>高スループット (IoTなど)。<br>少なくとも1回の実行。 | 초고속/단기(5분).<br>IoT, 스트리밍 데이터 처리. |

</details>

<details>
<summary><strong>📂 9.2 SQS & SNS & EventBridge</strong></summary>

- **SQS (Queue):**
  - **FIFO:** 순서 보장 (Order preserved), 정확히 1회 처리 (Exactly-once). 속도 느림.
  - **Standard:** 무제한 처리량, 순서 보장 X.
- **SNS (Topic):**
  - **Fan-out Pattern:** SNS 토픽 하나에 여러 SQS를 구독시켜서 병렬 처리. (🇯🇵: ファンアウトパターン)
- **EventBridge (Bus):**
  - SaaS(Salesforce 등) 연동, 스케줄링(Cron), 규칙 기반 라우팅.
  - **Schema Registry:** 이벤트 구조 자동 감지 및 코드 생성.

</details>

<details>
<summary><strong>📂 9.3 AppFlow</strong></summary>

- **Concept:** Securely transfer data between SaaS (Salesforce, Slack, ServiceNow) and AWS (S3, Redshift).
- **Features:** PrivateLink support (No public internet).
- 🇯🇵: SaaS アプリケーションと AWS 間のデータ転送。

</details>

---

## 💰 10. Cost Optimization

<details>
<summary><strong>📂 10.1 Savings Plans vs Reserved Instances</strong></summary>

| Type | Flexibility | Commit | Detail |
| :--- | :--- | :--- | :--- |
| **Compute SP** | ⭐⭐⭐ (High) | $/hour | Region/Family/OS/Tenancy 상관없음.<br>EC2 + Fargate + Lambda 적용. |
| **EC2 Instance SP** | ⭐ (Low) | $/hour | 특정 Region & Family(예: m5) 고정.<br>OS 변경은 가능. |
| **Reserved Instance** | 🌑 (None) | Attributes | Standard RI는 변경 불가.<br>Convertible RI는 교환 가능. |

</details>

<details>
<summary><strong>📂 10.2 Compute Optimizer</strong></summary>

- **Concept:** Uses ML to analyze history and recommend "Rightsizing".
- **Targets:** EC2, Auto Scaling Groups, EBS, Lambda, Fargate.
- **Metric:** Requires CloudWatch Agent for memory utilization data.
- 🇯🇵: 機械学習を使用してリソースの適正化 (Rightsizing) を推奨。

</details>

<details>
<summary><strong>📂 10.3 Cost Allocation Tags</strong></summary>

- **Concept:** Tag resources to track costs by department/project.
- **Important:** Tags must be **activated** in the Billing Console to appear in reports.
- 🇯🇵: コスト配分タグ (請求コンソールで有効化が必要)。

</details>

---

## 📱 11. Front-end & Mobile (Advanced)

<details>
<summary><strong>📂 11.1 CloudFront Functions vs Lambda@Edge</strong></summary>

| Feature | CloudFront Functions | Lambda@Edge |
| :--- | :--- | :--- |
| **Runtime** | JavaScript (Proprietary) | Node.js, Python |
| **Execution** | Sub-millisecond (Ultra fast) | ms ~ seconds |
| **Use Case** | Header manipulation, URL Rewrite.<br>(Simple logic) | Network calls, Auth, Image resizing.<br>(Complex logic) |
| **Location** | Hundreds of Edge Locations | Regional Edge Caches (Fewer) |

</details>

<details>
<summary><strong>📂 11.2 Cognito</strong></summary>

- **User Pools:** Authentication (Sign-up/Sign-in). OIDC/SAML. (Identity Provider)
  - 🇯🇵: 認証 (サインアップ/サインイン)。
- **Identity Pools:** Authorization (Give AWS Credentials). Access S3/DynamoDB directly.
  - 🇯🇵: 認可 (AWS クレデンシャルの付与)。

</details>

---

---

## 🤖 12. Machine Learning (ML)
> **Key Point:** 각 AI 서비스의 "용도(Use Case)"만 정확히 알면 됨.

<details>
<summary><strong>📂 12.1 SageMaker & ML Services</strong></summary>

| Service | 🇺🇸 EN | 🇯🇵 JP | 🇰🇷 KR |
| :--- | :--- | :--- | :--- |
| **SageMaker** | Build, Train, Deploy ML models.<br>**Feature Store**: Share features. | MLモデルの構築、トレーニング、デプロイ。<br>**Feature Store**: 特徴量の共有。 | 머신러닝 모델 구축/학습/배포 통합.<br>Feature Store로 데이터 재사용. |
| **Rekognition** | Image/Video Analysis.<br>Face detection, Content moderation. | 画像/動画分析。<br>顔認識、不適切コンテンツ検出。 | 이미지/동영상 분석.<br>안면 인식, 유해 콘텐츠 차단. |
| **Transcribe** | **Speech to Text (STT)**.<br>Subtitles, Meeting minutes. | 音声文字起こし (STT)。<br>字幕、議事録作成。 | 음성을 텍스트로 변환.<br>자막 생성, 회의록. |
| **Polly** | **Text to Speech (TTS)**.<br>Lifelike speech. | テキスト読み上げ (TTS)。<br>自然な音声。 | 텍스트를 음성으로 변환.<br>오디오북, 안내 방송. |
| **Kendra** | Enterprise Search service.<br>ML-powered document search. | エンタープライズ検索サービス。<br>MLを活用したドキュメント検索。 | 기업용 지능형 검색.<br>사내 문서(Wiki, SharePoint) 검색. |
| **Textract** | Extract text/data from scanned docs.<br>OCR + Structural analysis (Forms). | スキャン文書からテキスト抽出。<br>OCR + 構造分析 (フォーム)。 | 문서에서 텍스트/표 추출(OCR).<br>영수증, 송장 처리. |

</details>

---

## 📡 13. IoT & Edge Computing

<details>
<summary><strong>📂 13.1 IoT Core & Greengrass</strong></summary>

- **AWS IoT Core:**
  - **MQTT** Protocol based.
  - **Device Gateway:** Connects devices securely.
  - **Rules Engine:** Route data to Kinesis, S3, Lambda.
  - 🇯🇵: MQTT プロトコル, デバイスゲートウェイ, ルールエンジン.

- **IoT Greengrass:**
  - **Edge Computing.** Bring AWS services (Lambda, Docker) to local devices.
  - Process data locally **even without internet**, then sync to cloud.
  - 🇯🇵: エッジコンピューティング. オフラインでもローカルで処理可能.

</details>

---

## 🏎️ 14. HPC (High Performance Computing)

<details>
<summary><strong>📂 14.1 Network & Orchestration</strong></summary>

| Service | Detail |
| :--- | :--- |
| **EFA (Elastic Fabric Adapter)** | • Network interface for **HPC / ML**. (Bypasses OS kernel)<br>• Low latency, high throughput.<br>• Use with **MPI** (Message Passing Interface). |
| **AWS ParallelCluster** | • Open source cluster management tool.<br>• Deploys HPC clusters (Slurm) on AWS easily. |

* **Comparison:**
  * **ENA (Elastic Network Adapter):** General purpose high speed (EC2).
  * **EFA:** Specialized for HPC/ML (Inter-node communication).

</details>

---

## 🧱 15. Other Services (Blockchain & Media)

<details>
<summary><strong>📂 15.1 Miscellaneous</strong></summary>

- **Amazon Managed Blockchain:**
  - Hyperledger Fabric & Ethereum support.
  - Decentralized ledger.
- **Amazon QLDB (Quantum Ledger DB):**
  - **Centralized**, Immutable, Cryptographically verifiable. (Not Blockchain)
  - Used for financial transactions history.
  - 🇯🇵: 集中型, 不変性, 暗号化による検証可能.

- **AWS Elemental MediaConvert:**
  - Transcode file-based video (S3 -> S3).
  - 🇯🇵: ファイルベースの動画変換.

</details>

---

## 🏛️ 16. Architecture Patterns (The "Exam Logic")
> **Key Point:** SAP 시험에 자주 나오는 "필승 패턴" 모음.

<details>
<summary><strong>👉 Click to see: SAP Exam Patterns</strong></summary>

1. **VPC CIDR Overlap (IP 중복 해결)**
   - Use **PrivateLink** (Interface Endpoint) to expose specific apps.
   - Use **NAT Gateway** with complex routing (Harder).
   - *Never* use Peering directly.

2. **High Performance Storage (성능 이슈)**
   - EC2 Instance Store (Ephemeral) -> Highest IOPS/Lowest Latency. (Risk: Data loss on stop)
   - FSx for Lustre -> HPC / ML data processing.

3. **Secure S3 Access (보안 이슈)**
   - Use **VPC Endpoint (Gateway)**.
   - Add **Bucket Policy** to allow access *only* from that VPC Endpoint (`aws:sourceVpce`).

4. **DDoS Protection (공격 방어)**
   - **Shield Advanced** + **WAF** + **CloudFront** + **Route 53**.
   - Shield Advanced provides "Cost Protection" against scaling spikes due to attacks.

</details>

---

<div align="center">

**🎉 Complete Roadmap for AWS SAP-C02**
*"Knowledge is power, but Architecture is how you use it."*

</div>

### ✅ Final Check for Exam
- [ ] **Solution Architect Professional**은 "기술" 뿐만 아니라 **"비용"**과 **"운영 효율"**을 동시에 묻습니다.
- [ ] 문제에서 **"Most Cost-effective"**가 보이면 -> S3 Lifecycle, Spot Instances, Lambda.
- [ ] 문제에서 **"Minimizing Operational Overhead"**가 보이면 -> Managed Services (Serverless, Kinesis Firehose, Aurora Serverless).

### 📝 Notes & To-Do

- [ ] **Maarek Lecture:** Networking Section Complete
- [ ] **Tutorials Dojo:** Review "High Availability" scenarios
- [ ] **Hands-on:** VPC Peering vs PrivateLink setup

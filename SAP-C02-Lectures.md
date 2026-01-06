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

### 📝 Notes & To-Do

- [ ] **Maarek Lecture:** Networking Section Complete
- [ ] **Tutorials Dojo:** Review "High Availability" scenarios
- [ ] **Hands-on:** VPC Peering vs PrivateLink setup

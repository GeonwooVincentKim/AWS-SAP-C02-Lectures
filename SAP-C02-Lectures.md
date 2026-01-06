# ☁️ AWS Certified Solutions Architect - Professional (SAP-C02)

![AWS SAP](https://img.shields.io/badge/AWS-Solutions_Architect_Professional-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow?style=for-the-badge)
![Last Updated](https://img.shields.io/badge/Last_Updated-January_2026-blue?style=for-the-badge)

> **Study Notes & Roadmap** based on *Ultimate AWS Certified Solutions Architect Professional Slides (v35)* by Stephane Maarek.  
> This repository documents my journey to mastering advanced AWS architectures, hybrid networking, and migration strategies.

---

## 📑 Table of Contents (目次 / 목차)

1.  [🏢 Identity & Organizations](#1-identity--organizations)
2.  [🌐 Advanced Networking](#2-advanced-networking--connectivity)
3.  [💻 Compute & Load Balancing](#3-compute-auto-scaling--load-balancing)
4.  [💾 Storage Strategy](#4-storage-s3-ebs-efs-fsx)
5.  [📊 Databases & Analytics](#5-databases--analytics)
6.  [⚡ Serverless & Containers](#6-serverless--containers)
7.  [🚀 Migration & DR](#7-migration--disaster-recovery)
8.  [🔒 Security & Cost](#8-security--cost-optimization)

---

## 1. Identity & Organizations

Managing complex multi-account environments and governance.

| Language | Key Concepts |
| :--- | :--- |
| **🇺🇸 EN** | • **AWS Organizations:** Hierarchy management with OUs & **SCPs** (Deny > Allow).<br>• **IAM Identity Center:** Centralized SSO, integrating with external IdPs via **SAML 2.0**.<br>• **RAM:** Sharing Subnets & TGW across accounts to simplify network topology. |
| **🇯🇵 JP** | • **AWS Organizations:** OUと**SCP** (拒否優先) による階層管理。<br>• **IAM Identity Center:** **SAML 2.0** 経由で外部IdPと連携するSSO一元管理。<br>• **RAM:** アカウント間でサブネットやTGWを共有し、ネットワーク構成を簡素化。 |
| **🇰🇷 KR** | • **AWS Organizations:** OU 및 **SCP**(거부 우선 규칙)를 활용한 계층적 권한 관리.<br>• **IAM Identity Center:** **SAML 2.0** 기반 외부 IdP 연동 및 중앙 집중식 SSO.<br>• **RAM:** 서브넷, TGW 등을 계정 간 공유하여 네트워크 토폴로지 단순화. |

---

## 2. Advanced Networking & Connectivity

The core of the SAP exam. Hybrid clouds and VPC interconnections.

### 🔌 Connectivity Patterns
* **VPC Peering vs Transit Gateway**
    * *Peering:* Non-transitive, 1:1 connection. Low latency.
    * *TGW:* Hub-and-Spoke model. Supports thousands of VPCs & transitive routing.
* **VPC Endpoints**
    * **Interface (PrivateLink):** Uses ENI private IP. Accessible from VPN/Peering.
    * **Gateway:** S3 & DynamoDB only. Route table based. Not accessible from VPN.

### 🌉 Hybrid Networking (On-Prem ↔ AWS)
* **🇺🇸 English:** **Direct Connect (DX)** provides dedicated/private bandwidth. **Site-to-Site VPN** is used for backup or quick deployment (public internet).
* **🇯🇵 日本語:** **Direct Connect (DX)** は専用線によるプライベート接続を提供。**VPN** はバックアップまたは迅速な導入（インターネット経由）に使用。
* **🇰🇷 한국어:** **Direct Connect (DX)**는 전용 물리 회선으로 보안/성능 보장. **VPN**은 공용망을 사용하며 백업 또는 빠른 구축용.

---

## 3. Compute, Auto Scaling & Load Balancing

Optimizing performance and handling traffic at scale.

* **📈 Auto Scaling:**
    * **Dynamic Scaling:** Reacts to metrics (CPU > 70%).
    * **Predictive Scaling:** Uses ML to schedule scaling ahead of traffic patterns.
* **⚖️ Load Balancers:**
    * `ALB (L7)`: Path/Host-based routing, OIDC Auth, Container support.
    * `NLB (L4)`: Ultra-low latency, **Static IP**, Millions of requests/sec.
    * `GWLB (L3)`: Deploying 3rd-party firewalls (IPS/IDS) using **Geneve** protocol.

---

## 4. Storage (S3, EBS, EFS, FSx)

Choosing the right storage for performance and cost.

### 🗄️ S3 Storage Classes
> **Lifecycle Rule:** Standard ➔ IA ➔ Glacier (Instant/Flexible/Deep)

* **🇺🇸 EN:** **Intelligent-Tiering** automatically moves objects based on access patterns (No retrieval fee). **Object Lock** enables WORM (Write Once Read Many).
* **🇯🇵 JP:** **Intelligent-Tiering** はアクセスパターンに基づいて自動的に階層を移動（取り出し料金なし）。**Object Lock** は WORM モデルを実現。
* **🇰🇷 KR:** **Intelligent-Tiering**은 액세스 패턴에 따라 계층 자동 이동(수수료 없음). **Object Lock**으로 WORM(임의 삭제 방지) 구현.

### 📂 FSx Family (File Server)
* **FSx for Windows:** SMB, AD Integration.
* **FSx for Lustre:** High Performance Computing (HPC), linked with S3.
* **FSx for NetApp ONTAP:** Multi-protocol (NFS/SMB/iSCSI), Deduplication.

---

## 5. Databases & Analytics

Handling state and big data.

| Service | Feature Focus |
| :--- | :--- |
| **Aurora** | Multi-Master, **Global Database** (DR < 1s), Serverless v2. |
| **DynamoDB** | **Global Tables** (Active-Active), **DAX** (Microsecond cache), Streams. |
| **Kinesis** | **Data Streams** (Real-time, Shards) vs **Firehose** (Load to S3/Redshift). |
| **Redshift** | **Spectrum** (Query S3 data directly without loading). |

---

## 6. Serverless & Containers

Modern application development.

### 🧩 Lambda & API Gateway
* **Provisioned Concurrency:** Solves "Cold Start" issues for latency-sensitive apps.
* **API Gateway:** Throttling, Caching, Usage Plans (Monetization), API Keys.

### 📦 Containers
* **ECS:** Simple, AWS-native. Fargate (Serverless) vs EC2 Launch Type.
* **EKS:** Kubernetes managed service. Complex but standard.
* **App Runner:** Easiest way to deploy containerized web apps.

---

## 7. Migration & Disaster Recovery

Moving to the cloud and staying online.

### 🔄 The 6/7 Rs of Migration
1.  **Rehost:** Lift & Shift (AWS MGN).
2.  **Replatform:** Lift & Reshape (e.g., EC2 DB ➔ RDS).
3.  **Refactor:** Cloud Native (Monolith ➔ Microservices).

### 🚨 Disaster Recovery (DR) Strategies
> **Cost vs. RTO/RPO Trade-off**

* **Backup & Restore:** Cheapest, High RTO (Hours/Days).
* **Pilot Light:** Core services off/scaled down. Data live.
* **Warm Standby:** Scaled down but running.
* **Multi-Site Active/Active:** Most expensive, Zero downtime (Near-zero RTO).

---

## 8. Security & Cost Optimization

### 🔐 Security (KMS & Protection)
* **KMS:** Multi-Region Keys are essential for Global DR/Table encryption.
* **WAF:** Protects ALB/APIGW/CloudFront (Layer 7 - SQLi, XSS).
* **Shield:** DDoS Protection (Shield Advanced for cost protection).

### 💰 Cost Optimization
* **Savings Plans:** Flexible (Compute/EC2/SageMaker). Commit to $/hr.
* **Reserved Instances:** Less flexible. Commit to specific attributes.
* **Compute Optimizer:** ML-based recommendations for rightsizing.

---

## 📝 Exam Tips (멘토의 조언)

> **"Think like an Architect, not a SysAdmin."**

1.  **Requirements First:** Is the priority **Cost**, **Speed**, or **Availability**?
2.  **Hybrid is Key:** Master the **DX + VPN** backup patterns.
3.  **No Single Point of Failure:** Always look for **Multi-AZ** and **Decoupling** (SQS/SNS).

---

<div align="center">

**Goal: AWS Solutions Architect Professional (SAP-C02)** 🎯 Target Date: March 2026

</div>

<a href="https://fireflysoftware.io/openplatform/">
<picture>
  <source media="(max-width: 640px) and (prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/firefly-oss/.github/main/profile/assets/banner-narrow-dark.svg">
  <source media="(max-width: 640px)" srcset="https://raw.githubusercontent.com/firefly-oss/.github/main/profile/assets/banner-narrow-light.svg">
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/firefly-oss/.github/main/profile/assets/banner-dark.svg">
  <img src="https://raw.githubusercontent.com/firefly-oss/.github/main/profile/assets/banner-light.svg" alt="Firefly OpenPlatform - Platform - Bill of Materials" width="100%">
</picture>
</a>

# Firefly OpenPlatform - Platform - Bill of Materials

Developed by the Firefly Software Foundation. [dev@fireflysoftware.io](mailto:dev@fireflysoftware.io)

[Website](https://fireflysoftware.io/) · [OpenPlatform](https://fireflysoftware.io/openplatform/) · [Module catalogue](https://fireflysoftware.io/openplatform/modules/)

Centralized version management for **all** Firefly OpenPlatform `com.firefly` artifacts. Import this BOM to pin every shared library, core service, domain service, experience service, and application to a single version.

OpenPlatform covers shared business capabilities and the industry cores that sit on them. Banking and lending are two of those industries. Insurance is another. The bill of materials is not a core-banking-only catalog.

> **Note:** This BOM manages `com.firefly` artifact versions only. The `org.fireflyframework` artifact versions are managed separately by the `fireflyframework-bom` (imported automatically via `firefly-parent`).

## What It Provides

- One place to define the version of every `com.firefly` artifact
- Guarantees that all modules in a deployment use compatible versions
- Eliminates scattered `<version>` tags in consumer POMs

## Usage

Import the BOM inside your `<dependencyManagement>` section:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.firefly</groupId>
            <artifactId>firefly-bom</artifactId>
            <version>1.2.0-SNAPSHOT</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Then declare dependencies without a `<version>`:

```xml
<dependency>
    <groupId>com.firefly</groupId>
    <artifactId>library-common-core</artifactId>
</dependency>
```

## Managed Artifacts

### Shared Libraries

| Artifact | Description |
|----------|-------------|
| `library-common-core` | Core utilities and common patterns |
| `library-common-web` | Web layer utilities and configurations |
| `library-common-r2dbc` | Reactive database access |
| `library-common-auth` | Authentication and authorization framework |
| `library-common-eda` | Event-driven architecture support |
| `library-common-cache` | Caching utilities |
| `library-common-batch` | Batch processing support |
| `library-psps` | Payment service provider support |
| `library-rails` | Rails integration library |
| `library-utils` | General-purpose utilities |
| `library-commons-validators` | Data validation utilities |
| `library-workflow-engine` | Workflow engine |
| `library-plugin-manager-core` | Plugin manager core |
| `library-plugin-manager-api` | Plugin manager API |

### Core Banking

| Artifact | Description |
|----------|-------------|
| `core-banking-accounts` | Account management |
| `core-banking-cards` | Card services |
| `core-banking-ledger` | General ledger |
| `core-banking-payments` | Payment processing |
| `core-banking-psdx` | Open-banking access records for account information and payment initiation |

### Core Insurance

| Artifact | Description |
|----------|-------------|
| `core-insurance-policies` | Policy records, parties, transactions, coverages, certificates, and line-specific risk details |
| `core-insurance-underwriting` | Submissions, clearance, statements of value, loss runs, quotes, referrals, and decisions |
| `core-insurance-claims` | Claim files, coverage checks, reserves, assessments, settlements, fraud referrals, and recoveries |
| `core-insurance-financials` | Premium schedules, commissions, refunds, bordereaux, audits, and credit control |
| `core-insurance-delegated-authority` | Binders, authority limits, and coverholder appointments |
| `core-insurance-reinsurance` | Treaties, cessions, and reinsurance recoveries |
| `core-insurance-reserving` | Reserving snapshots, loss-development cells, and reporting extracts |

Insurance cores store records. They reference parties in `core-common-customer-mgmt` and agreements in `core-common-contract-mgmt`. Payment execution stays in `core-banking-payments`.

### Core Lending

| Artifact | Description |
|----------|-------------|
| `core-lending-asset-finance` | Asset finance |
| `core-lending-collateral-management` | Collateral tracking and valuation |
| `core-lending-credit-cards` | Credit card management |
| `core-lending-credit-scoring` | Credit risk assessment |
| `core-lending-delinquency-collections` | Collections and recovery |
| `core-lending-loan-origination` | Loan application and approval |
| `core-lending-loan-servicing` | Loan administration |
| `core-lending-mortgage` | Mortgage lending |
| `core-lending-provisioning-risk` | Risk provisioning |
| `core-lending-regulatory-compliance` | Lending compliance |
| `core-lending-supply-chain-finance` | Supply chain finance |

### Core Common

| Artifact | Description |
|----------|-------------|
| `core-common-accounting-gl` | General ledger and accounting |
| `core-common-config-mgmt` | Configuration management |
| `core-common-contract-mgmt` | Contract management |
| `core-common-customer-mgmt` | Customer data management |
| `core-common-distributor-mgmt` | Distributor management |
| `core-common-document-mgmt` | Document management |
| `core-common-kycb-mgmt` | KYC/KYB management |
| `core-common-modelhub` | Dynamic data modeling |
| `core-common-notification-services` | Multi-channel notifications |
| `core-common-org-mgmt` | Organization management |
| `core-common-product-mgmt` | Product lifecycle management |
| `core-common-reference-master-data` | Master data management |
| `core-common-sca-mgmt` | Strong customer authentication |
| `core-common-security-vault` | Security vault |
| `core-common-user-mgmt` | User lifecycle management |

### Core Data

| Artifact | Description |
|----------|-------------|
| `domain-data-credit-bureaus` | Credit bureau integration |
| `core-data-template` | Data service template |

### Domain Services

| Artifact | Description |
|----------|-------------|
| `domain-core-configuration` | Core configuration domain |
| `domain-core-security-center` | Security center domain |
| `domain-customer-kyc-kyb` | KYC/KYB processes |
| `domain-customer-people` | Customer people management |
| `domain-distributor-branding` | White-label branding |
| `domain-distributor-catalog` | Distributor catalogs |
| `domain-lending-loan-origination` | Lending origination domain |
| `domain-lending-loan-servicing` | Lending servicing domain |
| `domain-product-catalog` | Product catalog domain |
| `domain-product-pricing` | Product pricing domain |

### Applications

| Artifact | Description |
|----------|-------------|
| `app-authenticator` | Authentication application |
| `app-configurator-masters` | Master configuration application |
| `bfc-initconfig` | System initialization and configuration |

## Related

- [firefly-parent](https://github.com/firefly-oss/firefly-parent) — parent POM (extends `fireflyframework-parent`, imports `fireflyframework-bom` at **26.10.20**)
- [OpenPlatform](https://openplatform.fireflysoftware.io) — platform host

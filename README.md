# Awesome-Smart-Payment-Routing-Cascading

# Awesome Smart Payment Routing & Cascading

> A curated list of top Smart Payment Routing and Cascading platforms — both SaaS/Hosted commercial solutions and open-source alternatives for dynamically routing transactions across multiple payment providers to maximize authorization rates and minimize costs.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Chargebee Smart Routing](#chargebee-smart-routing)
  - [Adyen Intelligent Payment Routing](#adyen-intelligent-payment-routing)
  - [Checkout.com Intelligent Acceptance](#checkoutcom-intelligent-acceptance)
  - [Worldpay Dynamic Routing](#worldpay-dynamic-routing)
  - [Gr4vy](#gr4vy)
  - [Spreedly](#spreedly)
  - [Paydock](#paydock)
  - [IXOPAY](#ixopay)
- [Open-Source Software](#-open-source-software)
  - [Hyperswitch](#hyperswitch)
  - [Bridge](#bridge)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Smart Payment Routing and Cascading platforms. These are not open-source but are included as reference points for feature comparison.

### Chargebee Smart Routing
**Type:** Dynamic split routing across gateways  
Chargebee's Dynamic Smart Routing uses a continual review logic to determine which payment gateway processes each transaction, based on a configured percentage split between **Chargebee Pay and one external gateway** [citation:1]. The system dynamically adjusts based on actual payment volume rather than static rules. **Prerequisites:** Must accept payments through Chargebee Pay, must have at least one additional gateway active for the chosen payment method, and Dynamic Smart Routing is **limited to Card Payments in USD only** and to the configuration between Chargebee Pay and one external gateway [citation:1].  
**Best for:** Chargebee customers wanting simple percentage-based routing between Chargebee Pay and one other gateway for USD card transactions, accepting the limited scope.

### Adyen Intelligent Payment Routing
**Type:** AI-driven acquiring route optimization  
Adyen's Optimize suite uses AI to automatically find the acquiring route with the highest authorization rate and lowest costs, with configurable goals (maximize conversion, minimize cost, or balance both) [citation:6]. **Smart Payment Messaging** adapts authorization message formatting (CVC, AVS) to each issuing bank's preferences. **Auto Retries** intelligently retries declined transactions by adjusting routing, messaging, authentication, and tokenization in milliseconds. **Auto Rescue** recovers recurring revenue by reducing involuntary churn, and **Excessive Retry Protection** blocks payments likely to trigger excessive retry fees [citation:6].  
**Best for:** Adyen merchants wanting fully managed, AI-driven routing and retry optimization without building custom logic.

### Checkout.com Intelligent Acceptance
**Type:** AI-powered acceptance optimization engine  
Checkout.com's Intelligent Acceptance makes hundreds of micro-decisions in under 150 milliseconds across five optimization families: **dynamic payload optimization** (CVV/AVS formatting), **smart authentication** (3DS exemptions), **adaptive token management** (DPAN vs. FPAN), **strategic routing** across local and global networks, and **intelligent retries** based on decline code context [citation:7]. It claims zero manual work and no coding required, with AI models continuously adjusting to issuer preference shifts [citation:7].  
**Best for:** Checkout.com merchants wanting a hands-off, AI-driven optimization layer across routing, authentication, and retries.

### Worldpay Dynamic Routing
**Type:** Real-time adaptive routing engine  
Worldpay's Dynamic Routing uses live data to route every debit transaction to the best-performing provider instantly, reacting to network conditions, fraud signals, and issuer behavior in real time [citation:8]. Features include **least cost routing**, real-time rerouting during outages, and cross-border localization. One API integration unlocks unlimited routing paths without vendor lock-in, with continuous provider monitoring and automatic mid-transaction rerouting if conditions change [citation:8].  
**Best for:** Worldpay merchants wanting real-time adaptive routing with resilience during provider outages and least-cost optimization.

### Gr4vy
**Type:** Cloud-native payment orchestration with split routing  
Gr4vy provides payment orchestration with **Split Routing** for controlled A/B testing across payment routes directly from the dashboard, distributing traffic across routing variants with independent connector strategies, failover logic, and cost comparisons [citation:14]. The Q4 2025/Q1 2026 releases added native 3DS for mobile SDKs, Plaid integration for bank payment orchestration, Adyen Direct Mode for native SDK flows, and OAuth-secured webhooks [citation:4]. Local payment method coverage expanded across Brazil (Pix), Europe (Wero, Klarna), and emerging markets [citation:4].  
**Best for:** Merchants wanting a modern orchestration layer with built-in A/B testing for routing strategies and broad local payment method coverage.

### Spreedly
**Type:** Payment orchestration with vault and gateway abstraction  
Spreedly provides a single API connection to **over 120 global gateways and PSPs**, with a secure vault for storing payment details and intelligent transaction routing [citation:13]. It supports over 140 payment methods, white-label solutions, 3DS2 (EMVCo certified), and fraud/risk management via partners like Forter and Kount [citation:3]. Spreedly is Level 1 PCI compliant and on the Visa Global Registry of Service Providers [citation:3].  
**Best for:** Enterprises needing gateway abstraction, token portability across providers, and broad global payment method coverage.

### Paydock
**Type:** Modular orchestration for banks and merchants  
Paydock provides a unified payment orchestration platform with over 50 "deep" global processing partners and 100+ additional via partnered connections [citation:5]. Features include **dynamic routing**, a single dashboard for end-to-end visibility, charges rejection based on PAN/amount/currency/card type, whitelist/blacklist IP controls, and SAML SSO [citation:5]. It is positioned for banks and merchants wanting modular orchestration without maintaining multiple SDK integrations.  
**Best for:** Banks and large merchants wanting modular orchestration with strong security controls and a single unified dashboard.

### IXOPAY
**Type:** AI-native orchestration with tokenization and intelligence  
IXOPAY's IXO One platform combines orchestration, payments intelligence, and tokenization in a modular, AI-native stack with 500+ connectors and an Adapter SDK [citation:10]. Features include **intelligent routing** for higher approvals and lower costs, an AI payments assistant for recommendations, anomaly detection, MCP server support, and **P2PE** for in-person payments [citation:10]. It supports 250+ payment providers and 300+ payment methods through a single API, with Universal Tokens connecting online and in-person data [citation:10].  
**Best for:** Enterprises wanting a modular, AI-native orchestration platform with tokenization and strong connector depth.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Smart Payment Routing tools. The open-source ecosystem is **anchored by Hyperswitch** as the only mature, production-grade payment orchestrator with intelligent routing.

### Hyperswitch
**Stack:** Rust | **License:** Apache-2.0  
Hyperswitch (from Juspay) is the leading open-source payments platform with **intelligent routing** as a core module, designed to unify payments across providers, networks, and channels [citation:11]. It offers a **Payments Suite** (end-to-end orchestration with checkout, dynamic routing, and redundancy) and **modular components** (intelligent routing, vault, reconciliation, cost observability, smart retries, APM widgets) that can be adopted independently without overhauling existing infrastructure [citation:11]. The platform handles peak loads up to **5K TPS** with horizontal scaling, multi-region active-active deployment, and zero-downtime failover. It is PCI-compliant with tokenization and security certifications. Backed by Juspay's 12+ years of experience processing over 200 million daily transactions [citation:11].  
**Best for:** Digital businesses wanting a production-grade, self-hosted payment orchestrator with dynamic routing, smart retries, and vaulting under a permissive Apache-2.0 license, without vendor lock-in.

### Bridge
**Stack:** (Check repository) | **License:** Open Source (per project)  
Bridge provides modular building blocks for fiat and crypto payment flows, including **Virtual Accounts** (unique fiat deposit addresses for USD, EUR, MXN, BRL, GBP, COP), **Transfers** (one-time fiat or stablecoin), **Static Template Transfers** for recurring payment routes, and **Liquidation Addresses** that auto-forward crypto to fiat or crypto destinations [citation:9]. While not a traditional card routing engine, it enables **payment route orchestration** for stablecoin and fiat rails, with built-in KYC/KYB compliance and custodial wallets.  
**Best for:** Platforms needing orchestration across fiat and crypto rails, particularly for onramps, offramps, and recurring stablecoin payment routes.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Routing Type | Multi-Gateway | Self-Hosted | Best For |
|----------|---------|-------|--------------|---------------|-------------|----------|
| **Chargebee** | Proprietary | Cloud | Percentage split | 2 (incl. Chargebee Pay) | ❌ | Chargebee USD card routing |
| **Adyen** | Proprietary | Cloud | AI acquiring route | Adyen ecosystem | ❌ | AI-driven routing + retries |
| **Checkout.com** | Proprietary | Cloud | AI micro-decisions | Checkout ecosystem | ❌ | Hands-off AI optimization |
| **Worldpay** | Proprietary | Cloud | Real-time adaptive | Worldpay providers | ❌ | Least-cost + outage resilience |
| **Gr4vy** | Proprietary | Cloud | Split routing + A/B | 100+ connectors | ❌ | Modern orchestration + testing |
| **Spreedly** | Proprietary | Cloud | Gateway abstraction | 120+ gateways | ❌ | Token portability + coverage |
| **Paydock** | Proprietary | Cloud | Dynamic routing | 50+ deep partners | ❌ | Banks + security controls |
| **IXOPAY** | Proprietary | Cloud | AI-native routing | 250+ providers | ❌ | Modular + tokenization |
| **Hyperswitch** | Apache-2.0 | Rust | Intelligent routing | Multiple PSPs | ✅ | Open-source orchestration |
| **Bridge** | Open Source | (Check) | Fiat/crypto routes | Fiat + stablecoin | ✅ | Crypto payment orchestration |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Smart Payment Routing or Cascading tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **smart payment routing** is extremely limited. **Hyperswitch** is the only mature, production-grade open-source payment orchestrator with intelligent routing, backed by Juspay's enterprise track record and processing at scale [citation:11]. **Bridge** provides open-source orchestration for fiat/crypto payment routes but is not a card routing engine in the traditional sense [citation:9]. Commercial platforms like Adyen, Checkout.com, and Worldpay remain differentiated by proprietary AI models trained on billions of transactions, real-time issuer behavior adaptation, and integrated retry/authentication optimization that no open-source tool currently replicates.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐

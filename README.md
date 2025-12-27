# 🧰 Payfet Node.js SDK

**Payfet SDK** is the official Node.js client library for integrating with [Payfet](https://payfet.vercel.app) — a multi-provider fintech infrastructure platform built for startups, SaaS companies, and cooperatives.

> **Motto: Payfet — For Everyone, By Everyone**

---

## ✨ Overview

Payfet simplifies how businesses connect with various financial providers (payments, virtual accounts, KYC, etc.) through a **single API layer**.

This SDK enables developers to:

* 🔐 **Authenticate** as a Payfet tenant
* 🔗 **Manage provider connections**
* 💳 **Issue virtual accounts and wallets**
* 📊 **Access analytics & unified transaction logs**
* ⚙️ **Send and receive webhooks**
* 🧾 **Audit activities across services**

---

## 📦 Installation

```bash
npm install payfet
```

or

```bash
yarn add payfet
```

> Minimum Node.js version: `14+`

---

## ⚙️ Quickstart

```ts
import { PayfetClient } from 'payfet';

const client = new PayfetClient({
  tenantToken: 'your-tenant-token',
  businessId: 'your-business-id',
  secretKey: 'your-secret-key',
});

// Fetch balance from a connected provider
const balance = await client.wallets.getBalance({ provider: 'flutterwave' });
console.log(balance);

// View unified transaction logs
const logs = await client.analytics.getTransactions();
```

---

## 🔍 Core Modules

| Module      | Description                                           |
| ----------- | ----------------------------------------------------- |
| `wallets`   | Get balances, issue virtual accounts                  |
| `providers` | Connect or disconnect providers                       |
| `kyc`       | Submit or retrieve KYC verification results           |
| `analytics` | View transactions, reports, and performance summaries |
| `logs`      | View raw activity logs by tenant                      |

---

## 📊 Unified Analytics

Retrieve normalized data across all providers:

```ts
const analytics = await client.analytics.getOverview({
  from: '2024-01-01',
  to: '2024-01-31',
});
```

You can filter by provider, category, or date.

---

## 🧾 Logs & Auditing

Every sync, webhook, and provider action is tracked:

```ts
const logs = await client.logs.getAll();

logs.forEach((log) => {
  console.log(log.event, log.timestamp);
});
```

---

## 🌐 API Reference

Visit [docs.payfet.com](https://docs.payfet.com) (coming soon) for full documentation.

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes
4. Open a pull request

For large features, open an issue to discuss ideas first.

---

## 🛡️ Security

* Tenant tokens and secrets are encrypted in-memory
* All API communication is over HTTPS (TLS)
* SDK does not store or log credentials locally

---

## 🙋 Support

* GitHub: [Issues](https://github.com/AGASTRONICS/payfet-node-sdk/issues)
* Email: [agastronics.dev@gmail.com](mailto:agastronics.dev@gmail.com)
* Twitter: [@payfet](https://x.com/payfet)
* LinkedIn: [@payfet](https://www.linkedin.com/company/payfet)

---

## © About

Built and maintained by **Abdulsamad Opeyemi Abdulganiyu**
**© Payfet Technologies, 2025**

---

> **“Payfet — For Everyone, By Everyone”**
> Empowering developers to build inclusive financial infrastructure, without the headache.


---
icon: coin-blank
---

# Fees Collection

Fees Collection lets integrators collect fees in a single asset of their choice, without managing the underlying fee aggregation and conversion process.

For example, an integrator can choose to receive all collected fees as **USDC on their preferred destination chain**, even when the underlying user transactions involve different assets.

### How it works

Fees generated through the integration accrue automatically and, when fee conversion is enabled, are consolidated into the integrator's selected **target asset**.

The accumulated balance is withdrawn to the integrator's designated recipient address once it reaches the configured withdrawal threshold.

By default:

* The default withdrawal threshold is **$1,000 USD**.
* Once the threshold is reached, the accumulated fees are sent to the configured recipient address on the target chain.
* When fee conversion is enabled, fees are collected in the selected target asset.

This means integrators do not need to manage individual fee balances across different assets or manually consolidate them.

### Example

An integrator chooses:

* **Target chain:** Base
* **Target asset:** USDC
* **Recipient:** `0x...`

As users transact through the integration, the integrator's fees accumulate and are converted into USDC. Once the accumulated value reaches the configured threshold, the USDC is withdrawn to the provided recipient address.

### Configuring Fees Collection

Fees Collection supports **self-service configuration** through the [Aurora Intents Client Portal](https://portal.intents.aurora.dev/).

Integrators can configure their fee collection settings directly for each API key, without needing to contact Aurora.

#### Self-service configuration

1. Open the [Aurora Intents Client Portal](https://portal.intents.aurora.dev/).
2. Select the API key for which you want to configure fee collection.
3. Navigate to the **Fee collection address** settings.
4. Enable **Fee conversion** if you want all collected fees to be converted into a single asset instead of receiving fees in the assets used by individual swaps.
5. Select **On-chain wallet address** and configure:
   * **Chain** — the blockchain network where you want to receive your collected fees.
   * **Asset** — the asset in which you want to receive your fees (USDC is typically recommended).
   * **Wallet address** — the recipient wallet address on the selected chain.
6. Click **Save address** to save your configuration.

<figure><img src="../../.gitbook/assets/Screenshot 2026-11-19 at 11.02.44.png" alt="" width="563"><figcaption></figcaption></figure>

Once configured, fees associated with the API key will be collected according to your selected settings and sent to the designated wallet when the withdrawal threshold is reached.

> **Note:** Ensure that the recipient wallet address supports the selected chain and asset before saving your configuration.

#### Custom withdrawal thresholds

The default withdrawal threshold is **$1,000 USD**.

If you require a different withdrawal threshold or need assistance with your fee collection configuration, contact the Aurora team.

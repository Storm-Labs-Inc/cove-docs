# Introducing Cove

<figure><img src=".gitbook/assets/banner (1).svg" alt=""><figcaption></figcaption></figure>

### What is Cove?

Cove is the first ERC-4626 yield optimizer with automated and customizable vault management. Earn the best yields on-chain without the hassle of managing a portfolio. Cove is built to synergize with the [Yearn](https://yearn.fi/) ecosystem, and is optimized by [Gauntlet](https://www.gauntlet.xyz/).

### How does it work?

Cove acts as an intent aggregator for liquidity providers (LPs). Users can open a Cove position (basket) in three steps:

1. Select a base asset, either ETH or USD.
2. Choose an allocation strategy, which specifies how capital will be deployed.
3. Determine which ERC-4626 tokens to include. Possible combinations include yDAI/sDAI/sFRAX or stETH/sfrxETH/yETH.

The protocol aggregates and manages deposits according to user preferences. When rebalancing positions, there is the potential for [coincidence of wants](https://en.wikipedia.org/wiki/Coincidence\_of\_wants) (CoW) to exist between baskets, like ring trades in [CoW Swap’s batch auctions](https://docs.cow.fi/overview/coincidence-of-wants).

Approximately maximizing the volume of CoWs given the current/target protocol level allocations is solvable off-chain with linear programming. When there are matches, trades execute without leaking value (i.e. no price impact/slippage/fees/MEV). External trades are routed through CoW Swap (which now supports programmatic orders including TWAP via their [Programatic Order Framework](https://blog.cow.fi/introducing-the-programmatic-order-framework-from-cow-protocol-088a14cb0375)) to ensure the best execution and capture positive slippage.

Cove utilizes the ERC-4626 tokenized vault standard to consolidate diverse yield sources, placing an initial emphasis on Yearn V3 vaults, also known as yVaults. yVaults are “tokenized strategies”, strategies capable of being standalone ERC-4626 vaults themselves. These updated vaults come with a variety of improvements. For a comprehensive list, review the Yearn docs [here](https://docs.yearn.fi/getting-started/products/yvaults/v3).

Users have the flexibility to tailor their portfolios by selecting different allocation strategies for each of their positions. Cove rebalances users' portfolios to seek the best yield sources regularly. This ensures that users always receive the best annual percentage yield (APY) available for their particular risk preferences. Gauntlet is building and tuning models that are specifically designed to achieve this objective.

<figure><img src=".gitbook/assets/1.svg" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/2.svg" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/3.svg" alt=""><figcaption></figcaption></figure>

### What makes Cove unique?

Traditional AMMs are not well suited for portfolio or index construction because they suffer from [loss-versus-rebalancing (LVR)](https://a16zcrypto.com/posts/article/lvr-quantifying-the-cost-of-providing-liquidity-to-automated-market-makers/) due to [toxic order flow](https://insights.deribit.com/market-research/toxic-flow-its-sources-and-counter-strategies/) (i.e. all trades execute at worse-than-market prices).

Cove proposes an alternative solution that eliminates LVR and guarantees general intent level execution as a lower bound (e.g. CoW Swap). This means that trades occurring internally avoid slippage, MEV, price impact, and external trading fees. When trades happen outside of Cove they are routed through CoW Swap and are still protected from MEV and capture positive slippage.

**Key Differentiators**

1. Automation - no more manual management or rebalancing of positions to chase yield. Cove is the next generation of yield farming.
2. Future proof with ERC-4626 support - The new standard enables a simplified integration of yield-bearing vaults, enhances user experiences, and increases security.
3. Harness the Power of Yearn - Cove is building closely with the Yearn ecosystem to include V3 yVaults and boosted veYFI yield from the start. These vaults have been battle tested extensively and offer a variety of attractive features.

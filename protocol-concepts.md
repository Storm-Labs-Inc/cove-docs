---
description: Important building blocks for the Cove protocol.
---

# Protocol Concepts

### ERC-4626

Cove uses the ERC-4626 tokenized vault standard to help automate vault management.

EIP-4626 established a standard for yield bearing vaults. This standard allows Cove to easily integrate any complaint tokens with Cove’s yield automation system. This makes Cove forward compatible with any future potential yield sources that users would like to see supported.

Find more information about ERC-4626 [here](https://eips.ethereum.org/EIPS/eip-4626).

### coveYFI

Yearn is launching V3 of their vaults (V3 yVaults), which will be ERC-4626 compatible. They also recently introduced **veYFI,** a vote escrowed token model that emits a new reward token, called [**dYFI**](https://docs.yearn.fi/contributing/governance/veyfi#dyfi). Examples of yVaults include yvDAI, yvUSDC, and ycrv3usd.

Cove plans to use Yearn V3 for tokenized 4626 strategies that offer boosted veYFI yields for existing Yearn vaults. The protocol also includes **coveYFI**, a liquid locker that users can mint 1:1 by sending YFI. YFI is perpetually locked for veYFI, increasing the protocol’s boosted yields and share of veYFI over time.

Cove’s vaults and tokenized strategies wrap Yearn’s reward gauges for dYFI emissions. Users benefit from Cove’s perma-locked veYFI, reaping the benefit of boosted dYFI emissions, as well as compounding dYFI tokens for higher overall APY for each underlying Yearn V3 vault.

<figure><img src=".gitbook/assets/yfi.svg" alt=""><figcaption></figcaption></figure>

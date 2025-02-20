---
description: This section talks about the locking mechanism behind the MAHAX NFTs
---

# Locking MAHA for NFTs

{% hint style="info" %}
Locking `MAHA` is handled by the locker contract which is currently deployed at [0xbdd8f4daf71c2cb16cce7e54bb81ef3cfcf5aacb](https://etherscan.io/address/0xbdd8f4daf71c2cb16cce7e54bb81ef3cfcf5aacb)
{% endhint %}

`MAHAX` is a representation of the voting power a user gets when they lock their `MAHA`. It is calculated using two metrics:

* How long is the `MAHA` locked for?
* How much `MAHA` is locked?

The goal with this kind of mechanism is to create a fair and decentralized distribution for voting power that gives as much as power for the common man as compared to a whale.&#x20;

In most cases smaller holders will tend to lock their tokens for longer periods of time to get the same amount of voting power as whales who will tend to larger amounts of tokens but for lesser periods of time. This allows participants to have their voice recognized better by simply locking their tokens for longer periods of time.

![A screenshot of the lock screen that allows a user to choose how much MAHA they'd like to lock, for how long and if they'd like to stake their NFT as well.](<../.gitbook/assets/image (4) (2).png>)

To get a tutorial on how to lock your `MAHA`, visit the [Governance Portal Tutorials](governance-portal/staking-maha-for-mahax.md).

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p><a href="https://etherscan.io/tx/0x747a93e76bd8e2f2f680874cbf1e1b4c9526f243acc0f3d0d5e40c5379792182">https://etherscan.io/tx/0x747a93e76bd8e2f2f680874cbf1e1b4c9526f243acc0f3d0d5e40c5379792182</a> This is a sample transaction that takes MAHA from a user and mints a MAHAX NFT. The user also get staked voting power.</p></figcaption></figure>

## How is MAHAX calculated?

MAHAX is calculated using a simple formula that takes into account time and number of tokens locked.

$$
Amount_{mahax} = (Amount_{maha} * days) / (365 * 4)
$$

The below table showcases an example of how much `MAHAX` a person receives given `1000 MAHA` that is locked across various intervals of time. However note that a user can choose any interval between `2 weeks` to `4 years`.

| For 1000 MAHA locked | Lock Duration |
| -------------------- | ------------- |
| `1000 MAHAX`         | 4 years       |
| `250 MAHAX`          | 1 year        |
| `127.4 MAHAX`        | 6 month       |
| `63.7 MAHAX`         | 3 month       |
| `21.23 MAHAX`        | 1 month       |
| `4.79 MAHAX`         | 1 week        |

![A graph showcasing the MAHAX power (y-axis) across the number of days locked (x-axis) for 1000 MAHA](<../.gitbook/assets/image (1) (1) (1) (2).png>)

## Voting power that decays over time

One of the most important properties of a true democracy is the right of members to secede from the group. Transitioning of power is an important aspect of any future footed governance. Current participants need to give space for newer participants to come forward.&#x20;

First-mover advantages within the `MAHA` ecosystem can lead to governance structures centralized to early adopters, making it harder for power to secede successfully.&#x20;

This is why having the voting power decay slowly over time is important in creating future-footed governance.

Unless staked, every `MAHAX` NFT has its voting power, decay over time if it is not participating in active governance. This creates an incentive for holders to not just stake their NFTs but also have voting power that secedes if unstaked.

The end goal is to have a fully decentralized governance model that is evenly spread out and allows room for new participants to join in.

## Staking NFTs

{% hint style="info" %}
Staking MAHAX NFTs is handled by the [Staker](https://github.com/MahaDAO/governance-contracts/blob/master/contracts/MAHAXStaker.sol) Contract which is currently deployed at [0x608917f8392634428ec71c6766f3ec3f5cc8f421](https://etherscan.io/address/0x608917f8392634428ec71c6766f3ec3f5cc8f421)
{% endhint %}

![](<../.gitbook/assets/image (1) (3).png>)

`MAHAX` NFTs unless staked, have no functionality within the governance platform. These include benefits like earning fees, exercising voting power, providing legitimacy to a group of individuals, and so on.

Once an NFT is staked:

* It cannot be moved to another wallet address, and its voting power (`MAHAX` balance) is frozen
* It cannot also be traded on third-party marketplaces such as [OpenSea](https://opensea.io/)
* It can be unstaked at any point in time
* It will start earning fees and can be used for governance, voting, and boosting

Unstaking an NFT removes all the restrictions above, but at the same time unfreezes the voting power (`MAHAX` balance) which will start to decay over time.

To claim the underlying `MAHA` behind an NFT or to merge an NFT with another NFT, they both need to be unstaked.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p><a href="https://etherscan.io/tx/0x11e86040764638448500643da41448d96b50eb6241bb79d2b82cb2abcceb1ab0">https://etherscan.io/tx/0x11e86040764638448500643da41448d96b50eb6241bb79d2b82cb2abcceb1ab0</a> A sample transaction where a user stakes his NFT and gets voting power (MAHAXvp) for it</p></figcaption></figure>

{% hint style="info" %}
When a `MAHAX` NFT lock is created, the user gets an option to decide if he/she wishes to also stake the NFT in the same transaction. By default this is enabled.
{% endhint %}

## Merging NFTs

![The merge screen that selects the NFTs that a user is trying to merge](<../.gitbook/assets/image (4) (3).png>)

`MAHAX` NFTs can be merged into one another, allowing for voting power to get combined and a greater `MAHAX` balance.

When an NFT has merged, the following steps take place:

* A check is run if both NFTs are staked or not. Merging happens only if both NFTs are unstaked
* The first NFT is burnt
* The second NFT is updated with the combined underlying `MAHA` balances for both NFTs
* The second NFT is updated with a lock duration that is longer than the two NFTs

Merging NFTs creates more powerful NFTs with a net combined voting power.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p><a href="https://etherscan.io/tx/0xf499e96a8364b877224cc7918336af94253be4feef1e51f0dfede8957cf5c9e5">https://etherscan.io/tx/0xf499e96a8364b877224cc7918336af94253be4feef1e51f0dfede8957cf5c9e5</a> A NFT being merged into another NFT</p></figcaption></figure>

## Governance

The `MAHAX NFT` locker has various parameters that can be controlled by Governance:

* **The minimum amount of MAHA required for a lock:** This is currently set at `99 MAHAX` (or rather approximately `100 MAHA` locked for 4 years). If the cost of minting an NFT becomes higher, then ideally, lowering the minimum mint floor will allow for more NFTs to be minted as the cost of minting a piece becomes lower.
* **NFT minting privileges:** Currently only used for the migration of NFTs from the polygon, this function allows addresses/contracts to mint NFTs at will. Only to be used in rare scenarios.

## FAQs

### Can I make multiple locks using a single wallet?

Yes, you can make as many locks as want as long as the lock meets the minimum locking criteria (as of writing the minimum lock criteria is set at `100 MAHAX`).

### What happens if my lock expires?

If your lock expires, then your voting power goes to 0. However your NFT does not get burnt unless you decide to do so.

### Do I lose my voting power over time?

Yes, MAHAX is a continuously decreasing value over time however in most cases your NFT you would need to be staked which freezes your voting power to the point at which it was staked at.&#x20;

This voting power is recalculated if you either unstake, extend your lock or lock more `MAHA`.

### What happens if a NFT is staked but it is also listed on a NFT marketplace like Opensea?

NFTs can get kicked from staking if it is listed on marketplaces such as OpenSea. Because NFTs cannot be transferred when they are staked, a listing on OpenSea won't get executed because the transaction would fail.

However this can cause an unwanted floor price manipulation in these marketplaces. Which is why there is a `banFromStake(...)` function that gets triggered to kick NFTs from being staked which are listed on marketplaces like Opensea so that the sale can actually happen on the platform.

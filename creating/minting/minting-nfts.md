# Minting NFTs

Click on **Launchpad** on the navbar.

**Select the store** you want to mint from. If you don't have a store, you need to [deploy](../store/deploy-fee.md) one first.

Press the **Mint** button in the top right to enter the minting flow.

![](<../../.gitbook/assets/Screenshot 2022-08-12 at 10.03.06.png>)

There's a lot of stuff to cover here, so we're going to break down each section.



### Basic Information

#### Amount to Mint

The amount of tokens you are minting. Each NFT can have multiple tokens. Use cases for this, are for example, if you plan to redeem your NFT for real life tickets, you may want to have a big amount like 100 tokens. On the other hand, if you're an artist and are minting a valuable art piece as an NFT, you may want it to be a single 1/1 edition.

#### Name

The name of the NFT.

#### Description

A description explaining what this NFT is about.

#### Main Image

A cover image for your NFT. This is only how your NFT will appear around the marketplace, you can add more media if you want in the Forever Media section. The accepted upload formats **** are **.png / .jpeg / .gif / .svg+xml.** The ideal dimension is **500x500px (1:1)** and the max accepted size is **5mb**.

#### Category

Choose a category for your NFT. This is important to help people find it.

#### Tags

Type tags that are relevant to your NFT, to help people find it in the marketplace.

### Forever Media

This is an optional field where you can upload a file to be attached to your NFT. This file will not be visible on the NFT thumbnail, but on the Thing Page. The accepted formats are **.png / .jpeg / .gif / .svg+xml / .ogg / .mpeg / .mp3 / .webm / .mp4 / .gltf-binary / .gltf+json / .octet-stream.** The max size is **30mb**.

Whatever you upload here will be stored on the blockchain using [Arweave](https://www.arweave.org/), a hybrid and decentralized network.

### Forever Royalties

Forever Royalties are perpetual and are set for the lifetime of the NFT. The wallets added here, will get the specified percentage every time the NFT gets sold.

**Some important points:**

* **You can add Forever Royalties up to 50%.**&#x20;
* You need to add your wallet, if you wish to receive royalties.
* You can add up to 25 wallets (the sum of the percentages can't exceed 50%).
* If this field is left empty, the NFT will have no Forever Royalties.

The store owner can set **Default Forever Royalties** on the Store Settings, which can't be edited on the minting flow.

### Split Revenues

Split Revenues clears after every transaction (sell or transfer). The amount of Split Revenue available depends on the amount of royalties: **100% - X% of Forever Royalties - 2.5% of Market Fee = available revenue.** _If you set 10% of royalties for example, the available amount of revenue is 87.5%. In this example if you set 100% of Split Revenues, it would encompass 87.5% of the total percentage._

Some important points:

* You can add Split Revenues up to 100%, but the amount this represents depend on the amount set for Forever Royalties.
* You can add up to 25 wallets (the sum of the percentages can't exceed 100%).
* If this field is left empty, the available revenues will go to the minter.

### Date

This is an optional field where you can set a date for your token. It will not expire or anything like that, it will simply be displayed.

### Forever Document

Optionally upload a file to be attached to your NFT. This file will not be visible on the NFT thumbnail but on the Thing Page. The accepted formats are **.pdf.** The max size is **30MB**.

Whatever you upload here will be stored on the blockchain using [Arweave](https://www.arweave.org/), a hybrid and decentralized network.

### Location

Option to add a location for your NFT.

### Website

Option to add a website to your NFT.

### Custom

Add custom attributes to your NFT.


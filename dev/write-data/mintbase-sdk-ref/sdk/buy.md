# buy

Buys a token that has been listed on the mintbase market as long as the price provided is greater than what it is currently listed for.

The token is specified via `tokenId` and the corresponding `nftContractId`.

The nftContactId can be supplied as an argument or through the `NFT_CONTRACT_ID` environment variable.

An affiliate kickback is also possible using the referrer field. This allows markets to specify an account to receive affiliante gains. This totals to 1.25% per purchase and works as a built in business model.

Market address default values depend on the `NEAR_NETWORK` environment variable. If you set it to `mainnet` you will get the mainnet address `simple.market.mintbase1.near` otherwise it will default to the `testnet` value `market-v2-beta.mintspace2.testnet`.

**As with all new SDK api methods, this call should be wrapped in** [**execute**](../../../../mintbase-sdk-ref/packages/sdk/src/#execute) **and passed a signing method**

## buy(args: BuyArgs): NearContractCall

`buy` takes a single argument of type `BuyArgs`

```typescript
export type BuyArgs = {
    // the price you want to buy a token for, this must be greater than the amount its currently listed for
    price: string;
    // contract to which the token belongs, 
    //as an argument or through NFT_CONTRACT_ID env
    nftContractId?: string;
    // id of the token to be bought
    tokenId: string;
    // account that will receive the affiliate kick back (check affiliate documentation)
    referrerId?: string;
    //address of the mintbase market contract, this defaults to the correct values depending on the NEAR_NETWORK environment variable
    marketId?: string;
  };
```

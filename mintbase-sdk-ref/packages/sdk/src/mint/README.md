
# Mint

Mint a token for a specified reference material on a contract of your choice. You need to have been given minting permission.

The reference material is typically uploaded to IPFS or Arweave and can be easily done through our `uploadFileToArweave` method found in the storage module.

Royalties and splits can be configured to provide a customized flow of funds to up to 50 people as explained below.

It is possible to configure the amount of copies you want to mint through the `amount` field, but currently they will all share the same reference material.

The nftContactId can be supplied as an argument or through the `TOKEN_CONTRACT` environment variable.

**As with all new SDK api methods, this call should be wrapped in [execute](../#execute) and passed a signing method**

## mint(args: MintArgs): NearContractCall

`mint` takes a single argument of type `MintArgs`

```typescript
export type MintArgs =  {
  //the contractId from which you want to mint
  //can be specified through CONTRACT_ADDRESS configuration / environment variables
  contractAddress?: string;
  //the intended owner of the token being minted
  ownerId: string;
  // metadata including title, description and reference materials
  metadata: TokenMetadata;
  options?: MintOptions;
  noMedia?: boolean;     // explicit opt-in to NFT without media, breaks wallets
  noReference?: boolean; // explicit opt-in to NFT without reference
};

export type TokenMetadata = {
  title?: string;
  description?: string;
  media?: string;
  media_hash?: string;
  copies?: number;
  issued_at?: string;  // Stringified unix timestamp, according to
  expires_at?: string; // standards this is milliseconds since epoch, but
  starts_at?: string;  // since `env::block_timestamp` is in nanoseconds
  updated_at?: string; // most timestamps in the ecosystem are nanoseconds
  extra?: string;
  reference?: string;
  reference_hash?: string;
}


export type MintOptions = {
    // 0 < royaltyPercentage < 0.5
    //total percentage that will be allocated to royalties.
    //the maximum amount that can be allocated to royalties is 0.5 (50%)
    //this value cant be negative
    royaltyPercentage?: number;
    //key value pairs of ids and the relative percentage of the allocated royalties amount
    //splits must have at least 2 entries
    //splits must not have more than 50 entries
    //the splits percentage amounts must total to 1 meaning 100% of royaltyPercentage
    //i.e royaltyPercentage = 0.3 splits = {test1: 0.5, test2: 0.5}
    //in this case test1 and test2 will receive 0.15 of the total gains (0.5*0.3)
    splits?: Splits;
    //the amount of copies of specified token to be minted
    //this amount cannot be larger than 99
    amount?: number;
}
```

## React example

Example usage of mint method in a hypothetical React component:
{% code title="MintComponent.ts" overflow="wrap" lineNumbers="true" %}

```typescript
import { useState } from 'react';
import { useWallet } from '@mintbase-js/react';
import { execute, mint, MintArgs } from '@mintbase-js/sdk';


export const MintComponent = ({ media, reference, contractAddress, owner }: MintArgs): JSX.Element => {

  const { selector } = useWallet();

  const handleMint = async (): Promise<void> => {

    const wallet = await selector.wallet();

    await execute(
      mint({ contractAddress: contractAddress, metadata: { media, reference }, ownerId: owner })
    );

  }

  return (
    <div>
      <button onClick={handleMint}>
        Mint
      </button>
    </div>
  );
};
```
{% endcode %}
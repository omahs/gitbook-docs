
# Remove Minter

Remove minter from a smart contract you own

**As with all new SDK api methods, this call should be wrapped in [execute](../#execute) and passed a signing method**

## removeMinter(args: removeMinterArgs): NearContractCall

`removeMinter` takes a single argument of type `AddMinterArgs`

```typescript
type AddMinterArgs = {
    //the contract you own for which you wish to grant minting access
    //as an argument or through CONTRACT_ADDRESS env
    nftContractId?: string;
    //the id of the account that will be allowed to mint on the corresponding nftContractId
    minterId: string;
};
```
## React example

Example usage of removeMinter method in a hypothetical React component:
{% code title="RemoveMinterComponent.ts" overflow="wrap" lineNumbers="true" %}

```typescript
import { useState } from 'react';
import { useWallet } from '@mintbase-js/react';
import { execute, removeMinter, RemoveMinterArgs } from '@mintbase-js/sdk';


export const RemoveMinterComponent = ({ contractAddress, minterId }: RemoveMinterArgs) : JSX.Element => {
  
  const { selector } = useWallet();
  
  const handleRemoveMinter = async (): Promise<void> => {
    const wallet = await selector.wallet();
    await execute(
      removeMinter({ contractAddress: contractAddress, minterId: minterId })
    );
  }

  return (
    <div>
      <button onClick={handleRemoveMinter}>
        removeMinter from contract you own
      </button>
    </div>
  );
};
```
{% endcode %}
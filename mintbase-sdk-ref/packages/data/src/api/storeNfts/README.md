# storeNfts



{% hint style="warning" %}



This is a work in progress, please reach out to us on [Telegram](https://t.me/mintdev) for support.

For the most reliable data, reference our [existing graphql docs](https://docs.mintbase.io/dev/read-data/mintbase-graph).



{% endhint %}




Returns nfts by `contractAddress` and filtering by `showOnlyListed` with limit and offset.



### storeNfts( contractAddress: string, showOnlyListed?: boolean, { limit, offset }?: Pagination)



This is an example of a data api method.




Example:



{% code title="querystoreNfts.ts" overflow="wrap" lineNumbers="true" %}

```typescript

import { storeNfts } from  '@mintbase-js/data'

const { data, error } = await storeNfts('teammintbase.mintbase1.near', true);

if (error) {console.log('error', error)}


console.log(data) // => store listed nfts data

```

{% endcode %}
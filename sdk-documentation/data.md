# Data

* getTokenReserves
  * Function Signature
  * Input Parameters
  * Example Usage

## getTokenReserves <a id="gettokenreserves"></a>

This function fetches Uniswap reserve data for a given token address on a given network.

If only a chain id is specified, the Ethereum node used to fulfill data requests is determined by [`ethers.getDefaultProvider`](https://docs.ethers.io/ethers.js/html/api-providers.html#connecting-to-ethereum), else it is the one specified by the passed provider.

This function throws an error if the provided tokenAddress is not a token with a Uniswap exchange.

### Function Signature <a id="function-signature"></a>

```text
export async function getTokenReserves(  tokenAddress: string,  chainIdOrProvider: ChainIdOrProvider = 1): Promise<TokenReservesNormalized>
```

### Input Parameters <a id="input-parameters"></a>

### Example Usage <a id="example-usage"></a>

```text
const tokenAddress = '0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359' const chainIdOrProvider: ChainIdOrProvider = 1 ​const tokenReserves: TokenReservesNormalized = await getTokenReserves(tokenAddress, chainIdOrProvider)​​​​
```


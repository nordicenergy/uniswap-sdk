# Orchestration

Orchestration functions are plain-english wrappers for the function defined in [Data](data.md) and [Computation](https://github.com/Uniswap/docs/tree/d81e772a2b536e59f7887e7ac82a4bc568e69267/sdk-documentation/Computation.md).

* tradeExactEthForTokensWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeExactEthForTokens
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeEthForExactTokensWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeEthForExactTokens
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeExactTokensForEthWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeExactTokensForEth
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeTokensForExactEthWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeTokensForExactEth
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeExactTokensForTokensWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeExactTokensForTokens
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeTokensForExactTokensWithData
  * Function Signature
  * Input Parameters
  * Example Usage
* tradeTokensForExactTokens
  * Function Signature
  * Input Parameters
  * Example Usage

Functions with the `WithData` suffix are synchronous, and require token reserves to be passed in as arguments. Functions without the suffix are asychronous, and require token addresses to be passed in as arguments.

## tradeExactEthForTokensWithData <a id="tradeexactethfortokenswithdata"></a>

The function facilitates trading an exact amount of ETH for a specified token.

### Function Signature <a id="function-signature"></a>

```text
export function tradeExactEthForTokensWithData(reserves: OptionalReserves, ethAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters"></a>

### Example Usage <a id="example-usage"></a>

```text
const tradeDetails: TradeDetails = tradeExactEthForTokensWithData(reserves, '1000000000000000000')
```

## tradeExactEthForTokens <a id="tradeexactethfortokens"></a>

The function facilitates trading an exact amount of ETH for a specified token.

### Function Signature <a id="function-signature-1"></a>

```text
export async function tradeExactEthForTokens(  tokenAddress: string,  ethAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-1"></a>

### Example Usage <a id="example-usage-1"></a>

```text
const tradeDetails: TradeDetails = await tradeExactEthForTokens(tokenAddress, '1000000000000000000')
```

## tradeEthForExactTokensWithData <a id="tradeethforexacttokenswithdata"></a>

The function facilitates trading ETH for an exact amount of a specified token.

### Function Signature <a id="function-signature-2"></a>

```text
export function tradeEthForExactTokensWithData(reserves: OptionalReserves, tokenAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters-2"></a>

### Example Usage <a id="example-usage-2"></a>

```text
const tradeDetails: TradeDetails = tradeEthForExactTokensWithData(reserves, '1000000000000000000')
```

## tradeEthForExactTokens <a id="tradeethforexacttokens"></a>

The function facilitates trading ETH for an exact amount of a specified token.

### Function Signature <a id="function-signature-3"></a>

```text
export async function tradeEthForExactTokens(  tokenAddress: string,  tokenAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-3"></a>

### Example Usage <a id="example-usage-3"></a>

```text
const tradeDetails: TradeDetails = await tradeEthForExactTokens(tokenAddress, '1000000000000000000')
```

## tradeExactTokensForEthWithData <a id="tradeexacttokensforethwithdata"></a>

The function facilitates trading an exact amount of a specified token for ETH.

### Function Signature <a id="function-signature-4"></a>

```text
export function tradeExactTokensForEthWithData(reserves: OptionalReserves, tokenAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters-4"></a>

### Example Usage <a id="example-usage-4"></a>

```text
const tradeDetails: TradeDetails = tradeExactTokensForEthWithData(reserves, '1000000000000000000')
```

## tradeExactTokensForEth <a id="tradeexacttokensforeth"></a>

The function facilitates trading an exact amount of a specified token for ETH.

### Function Signature <a id="function-signature-5"></a>

```text
export async function tradeExactTokensForEth(  tokenAddress: string,  tokenAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-5"></a>

### Example Usage <a id="example-usage-5"></a>

```text
const tradeDetails: TradeDetails = await tradeExactTokensForEth(tokenAddress, '1000000000000000000')
```

## tradeTokensForExactEthWithData <a id="tradetokensforexactethwithdata"></a>

The function facilitates trading a specified token for an exact amount of ETH.

### Function Signature <a id="function-signature-6"></a>

```text
export function tradeTokensForExactEthWithData(reserves: OptionalReserves, ethAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters-6"></a>

### Example Usage <a id="example-usage-6"></a>

```text
const tradeDetails: TradeDetails = tradeTokensForExactEthWithData(reserves, '1000000000000000000')
```

## tradeTokensForExactEth <a id="tradetokensforexacteth"></a>

The function facilitates trading a specified token for an exact amount of ETH.

### Function Signature <a id="function-signature-7"></a>

```text
export async function tradeTokensForExactEth(  tokenAddress: string,  ethAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-7"></a>

### Example Usage <a id="example-usage-7"></a>

```text
const tradeDetails: TradeDetails = await tradeTokensForExactEth(tokenAddress, '1000000000000000000')
```

## tradeExactTokensForTokensWithData <a id="tradeexacttokensfortokenswithdata"></a>

The function facilitates trading an exact amount of a specified token for another token.

### Function Signature <a id="function-signature-8"></a>

```text
export function tradeExactTokensForTokensWithData(  reservesInput: OptionalReserves,  reservesOutput: OptionalReserves,  tokenAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters-8"></a>

### Example Usage <a id="example-usage-8"></a>

```text
const tradeDetails: TradeDetails = tradeExactTokensForTokensWithData(    reservesInput, reservesOutput, '1000000000000000000')
```

## tradeExactTokensForTokens <a id="tradeexacttokensfortokens"></a>

The function facilitates trading an exact amount of a specified token for another token.

### Function Signature <a id="function-signature-9"></a>

```text
export async function tradeExactTokensForTokens(  tokenAddressInput: string,  tokenAddressOutput: string,  tokenAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-9"></a>

### Example Usage <a id="example-usage-9"></a>

```text
const tradeDetails: TradeDetails = await tradeExactTokensForTokens(    tokenAddressInput, tokenAddressOutput, '1000000000000000000')
```

## tradeTokensForExactTokensWithData <a id="tradetokensforexacttokenswithdata"></a>

The function facilitates trading a specified token for an exact amount of another token.

### Function Signature <a id="function-signature-10"></a>

```text
export function tradeTokensForExactTokensWithData(  reservesInput: OptionalReserves,  reservesOutput: OptionalReserves,  tokenAmount: BigNumberish): TradeDetails
```

### Input Parameters <a id="input-parameters-10"></a>

### Example Usage <a id="example-usage-10"></a>

```text
const tradeDetails: TradeDetails = tradeTokensForExactTokensWithData(    reservesInput, reservesOutput, '1000000000000000000')
```

## tradeTokensForExactTokens <a id="tradetokensforexacttokens"></a>

The function facilitates trading an exact amount of a specified token for another token.

### Function Signature <a id="function-signature-11"></a>

```text
export async function tradeTokensForExactTokens(  tokenAddressInput: string,  tokenAddressOutput: string,  tokenAmount: BigNumberish,  chainIdOrProvider?: ChainIdOrProvider): Promise<TradeDetails>
```

### Input Parameters <a id="input-parameters-11"></a>

### Example Usage <a id="example-usage-11"></a>

```text
const tradeDetails: TradeDetails = await tradeTokensForExactTokens(    tokenAddressInput, tokenAddressOutput, '1000000000000000000')
```


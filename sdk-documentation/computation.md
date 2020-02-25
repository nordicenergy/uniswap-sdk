# Computation

* getMarketDetails
  * Function Signature
  * Input Parameters
  * Example Usage
* getTradeDetails
  * Function Signature
  * Input Parameters
  * Example Usage

## getMarketDetails <a id="getmarketdetails"></a>

This function computes market details for the passed reserves data. Markets are defined as ETH&lt;&gt;ERC20, ERC20&lt;&gt;ETH, or ERC20&lt;&gt;ERC20 pairs, where the first currency is the input and the second is the output. Reserves must be specified for both the input and output currency.

In the case of ETH, `undefined` should be passed as the reserves data. [`getTokenReserves`](data.md#getTokenReserves) returns properly formatted ERC20 reserves, or the requisite data can be fetched manually and passed in.

Rates are calculated to 18 decimal places of precision.

### Function Signature <a id="function-signature"></a>

```text
export function getMarketDetails(  optionalReservesInput: OptionalReserves,  optionalReservesOutput: OptionalReserves): MarketDetails
```

### Input Parameters <a id="input-parameters"></a>

### Example Usage <a id="example-usage"></a>

```text
const reserves: ChainIdOrProvider = await getTokenReserves(tokenAddress)​const marketDetails: MarketDetails = getMarketDetails(undefined, reserves) ​​​​
```

## getTradeDetails <a id="gettradedetails"></a>

This function computes trade details for the passed market data.

This function throws an error if the passed \_tradeAmount is greater than the amount of ETH/tokens in the relevant Uniswap exchange.

Trade amounts must be passed in non-decimal form \(where e.g. 1 ETH is represented as 1000000000000000000 wei\).

### Function Signature <a id="function-signature-1"></a>

```text
export function getTradeDetails(  tradeExact: TRADE_EXACT,  _tradeAmount: BigNumberish,  marketDetails: MarketDetails): TradeDetails
```

### Input Parameters <a id="input-parameters-1"></a>

### Example Usage <a id="example-usage-1"></a>

```text
const _purchaseAmount: BigNumber = new BigNumber('2.5')const _decimals: number = 18const tradeAmount: BigNumber = _purchaseAmount.multipliedBy(10 ** _decimals)const marketDetails: MarketDetails = getMarketDetails(undefined, reserves) ​const tradeDetails: TradeDetails = getTradeDetails(TRADE_EXACT.OUTPUT, tradeAmount, marketDetails)​​​​​​​​​
```


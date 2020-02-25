# Transact

* 
## getExecutionDetails <a id="getexecutiondetails"></a>

The function formats trade data for execution against the relevant Uniswap exchange.

### Function Signature <a id="function-signature"></a>

```text
export function getExecutionDetails(  trade: TradeDetails,  maxSlippage?: number,  deadline?: number,  recipient?: string): ExecutionDetails
```

### Input Parameters <a id="input-parameters"></a>

### Example Usage <a id="example-usage"></a>

Method arguments are returned as one of: `BigNumber`, `number`, or `string`. `BigNumber`s are large number objects, `numbers` are small numbers in base 10, and `string`s are addresses.

```text
const tradeDetails: TradeDetails = tradeExactEthForTokensWithData(reserves, '1000000000000000000')​const executionDetails: ExecutionDetails = await getExecutionDetails(tradeDetails)​​​​​
```


# Trade tokens

In Uniswap, there is a separate exchange contract for each ERC20 token. These exchanges hold reserves of both ETH and their associated ERC20. Instead of waiting to be matched in an order-book, users can make trades against the reserves at any time. Reserves are pooled between a decentralized network of liquidity providers who collect fees on every trade.

Pricing is automatic, based on thex∗y=kx \* y = kx∗y=k market making formula which automatically adjusts prices based off the relative sizes of the two reserves and the size of the incoming trade. Since all tokens share ETH as a common pair, it is used as an intermediary asset for direct trading between any ERC20 ⇄ ERC20 pair.

## ETH ⇄ ERC20 Calculations <a id="eth-erc20-calculations"></a>

The variables needed to determine price when trading between ETH and ERC20 tokens is:

* ETH reserve size of the ERC20 exchange
* ERC20 reserve size of the ERC20 exchange
* Amount sold \(input\) or amount bought \(output\)

### Amount Bought \(sell order\) <a id="amount-bought-sell-order"></a>

For sell orders \(exact input\), the amount bought \(output\) is calculated:

```text
const inputAmount = userInputEthValueconst inputReserve = web3.eth.getBalance(exchangeAddress)const outputReserve = tokenContract.methods.balanceOf(exchangeAddress).call()​const inputAmount = userInputTokenValueconst inputReserve = tokenContract.methods.balanceOf(exchangeAddress).call()const outputReserve = web3.eth.getBalance(exchangeAddress)​const numerator = inputAmount * outputReserve * 997const denominator = inputReserve * 1000 + inputAmount * 997const outputAmount = numerator / denominator
```

### Amount Sold \(buy order\) <a id="amount-sold-buy-order"></a>

For buy orders \(exact output\), the cost \(input\) is calculated:

```text
const outputAmount = userInputTokenValueconst inputReserve = web3.eth.getBalance(exchangeAddress)const outputReserve = tokenContract.methods.balanceOf(exchangeAddress).call()​const outputAmount = userInputEthValueconst inputReserve = tokenContract.methods.balanceOf(exchangeAddress).call()const outputReserve = web3.eth.getBalance(exchangeAddress)​const numerator = outputAmount * inputReserve * 1000const denominator = (outputReserve - outputAmount) * 997const inputAmount = numerator / denominator + 1
```

### Liquidity Provider Fee <a id="liquidity-provider-fee"></a>

There is a 0.3% liquidity provider fee built into the price formula. This can be calculated:

```text
fee = inputAmount * 0.003
```

### Exchange Rate <a id="exchange-rate"></a>

The exchange rate is simply the output amount divided by the input amount.

```text
const rate = outputAmount / inputAmount
```

## ERC20 ⇄ ERC20 Calculations <a id="erc20-erc20-calculations"></a>

The variables needed to determine price when trading between two ERC20 tokens is:

* ETH reserve size of the input ERC20 exchange
* ERC20 reserve size of the input ERC20 exchange
* ETH reserve size of the output ERC20 exchange
* ERC20 reserve size of the output ERC20 exchange
* Amount sold \(input\) or amount bought \(output\)

### Amount Bought \(sell order\) <a id="amount-bought-sell-order-1"></a>

For sell orders \(exact input\), the amount bought \(output\) is calculated:

```text
const inputAmountA = userInputTokenAValueconst inputReserveA = tokenContractA.methods.balanceOf(exchangeAddressA).call()const outputReserveA = web3.eth.getBalance(exchangeAddressA)​const numeratorA = inputAmountA * outputReserveA * 997const denominatorA = inputReserveA * 1000 + inputAmountA * 997const outputAmountA = numeratorA / denominatorA​const inputAmountB = outputAmountAconst inputReserveB = web3.eth.getBalance(exchangeAddressB)const outputReserveB = tokenContract.methods.balanceOf(exchangeAddressB).call()​const numeratorB = inputAmountB * outputReserveB * 997const denominatorB = inputReserveB * 1000 + inputAmountB * 997const outputAmountB = numeratorB / denominatorB
```

### Amount Sold \(buy order\) <a id="amount-sold-buy-order-1"></a>

For buy orders \(exact output\), the cost \(input\) is calculated:

```text
const outputAmountB = userInputEthValueconst inputReserveB = web3.eth.getBalance(exchangeAddressB)const outputReserveB = tokenContractB.methods.balanceOf(exchangeAddressB).call()​const numeratorB = outputAmountB * inputReserveB * 1000const denominatorB = (outputReserveB - outputAmountB) * 997const inputAmountB = numeratorB / denominatorB + 1​const outputAmountA = userInputEthValueconst inputReserveA = tokenContractA.methods.balanceOf(exchangeAddressA).call()const outputReserveA = web3.eth.getBalance(exchangeAddressA)​const numeratorA = outputAmountA * inputReserveA * 1000const denominatorA = (outputReserveA - outputAmountA) * 997const inputAmountA = numeratorA / denominatorA + 1
```

### Liquidity Provider Fee <a id="liquidity-provider-fee-1"></a>

There is a 0.3% liquidity provider fee to swap from TokenA to ETH on the input exchange. There is another 0.3% liquidity provider fee to swap the remaining ETH to TokenB.

```text
const exchangeAFee = inputAmountA * 0.003const exchangeBFee = inputAmountB * 0.003
```

Since users only inputs Token A, it can be represented to them as:

```text
const combinedFee = inputAmountA * 0.00591
```

### Exchange Rate <a id="exchange-rate-1"></a>

The exchange rate is simply the output amount divided by the input amount.

```text
const rate = outputAmountB / inputAmountA
```

## Deadlines <a id="deadlines"></a>

Many Uniswap functions include a transaction `deadline` that sets a time after which a transaction can no longer be executed. This limits miners holding signed transactions for extended durations and executing them based off market movements. It also reduces uncertainty around transactions that take a long time to execute due to issues with gas price.

Deadlines are calculated by adding the desired amount of time \(in seconds\) to the latest Ethereum block timestamp.

```text
web3.eth.getBlock('latest', (error, block) => {    deadline = block.timestamp + 300    })
```

## Recipients <a id="recipients"></a>

Uniswap allows traders to swap tokens and transfer the output to a new `recipient` address. This allows for a type of payment where the payer sends one token and the payee receives another.

## ETH ⇄ ERC20 Trades <a id="eth-erc20-trades"></a>

Coming soon...

## ERC20 ⇄ ERC20 Trades <a id="erc20-erc20-trades"></a>

Coming soon...

## Custom Pools <a id="custom-pools"></a>

Coming soon...


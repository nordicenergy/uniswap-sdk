# Custom Linking

The Uniswap front-end supports URL query parameters to allow for custom linking to the Uniswap exchange. Users and developers can use these query parameters to link to the Uniswap exchange with custom prefilled settings.

Each Page has specific available URL parameters that can be set. Global parameters can be used on all pages.

A parameter used on an incorrect page will have no effect on exchange settings. Parameters not set with a URL parameter will be set to standard exchange defaults.

#### Theme Options <a id="theme-options"></a>

Theme can be set as `light` or `dark`.

#### Example Usage <a id="example-usage"></a>

```text
https://uniswap.exchange/swap?theme=dark
```

## Swap Page <a id="swap-page"></a>

#### Defaults <a id="defaults"></a>

ETH defaults as the input currency. When a different token is selected for either input or output ETH will default as the opposite selected currency.

#### Constraints <a id="constraints"></a>

Addresses must be valid ERC20 addresses. Slippage and amount values must be valid numbers accepted by the exchange \(or error will prevent from swapping\). Slippage can 0, or within the range 10-&gt;9999 bips \(which converts to 0%, 0.01%-&gt;99%\)

When selecting ETH as the output currency a user must also choose an inputCurrency that is not ETH \(to prevent ETH being populated in both fields\)

#### Setting Amounts <a id="setting-amounts"></a>

Two parameters, exactField and exactAmount can be used to set specific token amounts to be sold or bought. Both fields must be set in the URL or there will be no effect on the settings.

#### Example Usage <a id="example-usage-1"></a>

```text
https://uniswap.exchange/swap?exactField=input?exactAmount=10?inputCurrency=0x0F5D2fB29fb7d3CFeE444a200298f468908cC942
```

## Send Page <a id="send-page"></a>

The send page has the same options available as the Swap page, plus one additional paramter, `recipient`.

#### Example Usage <a id="example-usage-2"></a>

```text
https://uniswap.exchange/send?recipient=0x74Aa01d162E6dC6A657caC857418C403D48E2D77
```

## Pool Page <a id="pool-page"></a>

The Pool page is made up of 3 subroutes: `add-liquidity`, `remove-liquidity`, `create-exchange`.

### Add Liquidity <a id="add-liquidity"></a>

#### Example Usage <a id="example-usage-3"></a>

```text
https://uniswap.exchange/add-liquidity?ethAmount=2.34?token=0x42456D7084eacF4083f1140d3229471bbA2949A8?tokenAmount=300
```

### Remove Liquidity <a id="remove-liquidity"></a>

#### Example Usage <a id="example-usage-4"></a>

```text
https://uniswap.exchange/remove-liquidity?poolTokenAmount=1.23
```

### Create Exchange <a id="create-exchange"></a>

#### Example Usage <a id="example-usage-5"></a>

```text
uniswap.exchange/create-exchange?tokenAddress=0x0F5D2fB29fb7d3CFeE444a200298f468908cC942
```

### Custom Routes <a id="custom-routes"></a>

Custom token routes can still be used in combination with URL paramters. URL paramters are higher in the settings hierarchy than custom routes.

An example using custom token route and URL paramters.

```text
uniswap.exchange/swap/0x0F5D2fB29fb7d3CFeE444a200298f468908cC942?exactField=input?exactAmount=10
```


# Factory API

## initializeFactory <a id="initializefactory"></a>

```text
initializeFactory(template: address)
```

```text
factoryContract.methods.initializeFactory(template).send()
```

## createExchange <a id="createexchange"></a>

```text
createExchange(token: address): address
```

```text
factoryContract.methods.initializeFactory(token).send()
```

## getExchange <a id="getexchange"></a>

```text
@constantgetExchange(token: address): address
```

```text
factoryContract.methods.getExchange(token).call()
```

## getToken <a id="gettoken"></a>

```text
@constantgetToken(exchange: address): address
```

```text
factoryContract.methods.getToken(exchange).call()
```

## getTokenWithId <a id="gettokenwithid"></a>

```text
@constantgetTokenWithId(token_id: uint256): address
```

```text
factoryContract.methods.getToken(exchange).call()
```


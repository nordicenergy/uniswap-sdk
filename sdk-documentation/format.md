# Format

* formatSignificant
  * Function Signature
  * Input Parameters
  * Example Usage
* formatSignificantDecimals
  * Function Signature
  * Input Parameters
  * Example Usage
* formatFixed
  * Function Signature
  * Input Parameters
  * Example Usage
* formatFixedDecimals
  * Function Signature
  * Input Parameters
  * Example Usage

## formatSignificant <a id="formatsignificant"></a>

This function formats values to a specified number of significant digits.

### Function Signature <a id="function-signature"></a>

```text
export function formatSignificant(bigNumberish: BigNumberish, options?: FormatSignificantOptions): string
```

### Input Parameters <a id="input-parameters"></a>

### Example Usage <a id="example-usage"></a>

```text
const formatted: string = formatSignificant('123456', { significantDigits: 3 }) 
```

## formatSignificantDecimals <a id="formatsignificantdecimals"></a>

This function formats token and ethereum values to a specified number of significant digits.

### Function Signature <a id="function-signature-1"></a>

```text
export function formatSignificantDecimals(  bigNumberish: BigNumberish,  decimals: number,  options?: FormatSignificantOptions): string
```

### Input Parameters <a id="input-parameters-1"></a>

### Example Usage <a id="example-usage-1"></a>

```text
const formatted: string = formatSignificantDecimals('1234560000000000000', 18, { significantDigits: 3 }) 
```

## formatFixed <a id="formatfixed"></a>

This function formats values to a specified number of decimal places.

### Function Signature <a id="function-signature-2"></a>

```text
export function formatFixed(bigNumberish: BigNumberish, options?: FormatFixedOptions): string
```

### Input Parameters <a id="input-parameters-2"></a>

### Example Usage <a id="example-usage-2"></a>

```text
const formatted: string = formatFixed('1.2345', { decimalPlaces: 2 }) 
```

## formatFixedDecimals <a id="formatfixeddecimals"></a>

This function formats token and ethereum values to a specified number of decimal places.

### Function Signature <a id="function-signature-3"></a>

```text
export function formatFixedDecimals(  bigNumberish: BigNumberish,  decimals: number,  options?: FormatFixedOptions): string
```

### Input Parameters <a id="input-parameters-3"></a>

### Example Usage <a id="example-usage-3"></a>

```text
const formatted: string = formatFixedDecimals('1234560000000000000', 18, { decimalPlaces: 2 }) 
```


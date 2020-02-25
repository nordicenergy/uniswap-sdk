# Types

import BigNumber from 'bignumber.js'

import { ethers } from 'ethers'

​

import { SUPPORTED\_CHAIN\_ID, TRADE\_TYPE, TRADE\_EXACT, FIXED\_UNDERFLOW\_BEHAVIOR } from './constants'

​

export type BigNumberish = BigNumber \| ethers.utils.BigNumber \| string \| number

​

export type ChainIdOrProvider = SUPPORTED\_CHAIN\_ID \| ethers.providers.AsyncSendable \| ethers.providers.Provider

​

export function isChainId\(chainIdOrProvider: ChainIdOrProvider\): chainIdOrProvider is SUPPORTED\_CHAIN\_ID {

 const chainId: SUPPORTED\_CHAIN\_ID = chainIdOrProvider as SUPPORTED\_CHAIN\_ID

 return typeof chainId === 'number'

}

​

export function isLowLevelProvider\(

 chainIdOrProvider: ChainIdOrProvider

\): chainIdOrProvider is ethers.providers.AsyncSendable {

 if \(isChainId\(chainIdOrProvider\)\) {

 return false

 } else {

 const provider: ethers.providers.AsyncSendable = chainIdOrProvider as ethers.providers.AsyncSendable

 return 'send' in provider \|\| 'sendAsync' in provider

 }

}

​

export interface Token {

 chainId?: SUPPORTED\_CHAIN\_ID

 address?: string

 decimals: number

}

​

export interface TokenAmount {

 token: Token

 amount: BigNumberish

}

​

export interface TokenAmountNormalized {

 token: Token

 amount: BigNumber

}

​

export interface TokenReserves {

 token: Token

 exchange?: Token

 ethReserve: TokenAmount

 tokenReserve: TokenAmount

}

​

export interface TokenReservesNormalized {

 token: Token

 exchange?: Token

 ethReserve: TokenAmountNormalized

 tokenReserve: TokenAmountNormalized

}

​

export interface EthReserves {

 token: Token

}

​

export type OptionalReserves = TokenReserves \| EthReserves \| undefined

​

export function areTokenReserves\(reserves: OptionalReserves\): reserves is TokenReserves {

 const tokenReserves: TokenReserves = reserves as TokenReserves

 return \(

 tokenReserves !== undefined && tokenReserves.ethReserve !== undefined && tokenReserves.tokenReserve !== undefined

 \)

}

​

export function areETHReserves\(reserves: OptionalReserves\): reserves is EthReserves {

 const tokenReserves: TokenReserves = reserves as TokenReserves

 return \(

 tokenReserves !== undefined && tokenReserves.ethReserve === undefined && tokenReserves.tokenReserve === undefined

​

 \)

}

​

export type NormalizedReserves = TokenReservesNormalized \| EthReserves

​

export function areTokenReservesNormalized\(reserves: NormalizedReserves\): reserves is TokenReservesNormalized {

 const tokenReservesNormalized: TokenReservesNormalized = reserves as TokenReservesNormalized

 return tokenReservesNormalized.ethReserve !== undefined && tokenReservesNormalized.tokenReserve !== undefined

}

​

export interface Rate {

 rate: BigNumber

 rateInverted: BigNumber

}

export interface MarketDetails {

 tradeType: TRADE\_TYPE

 inputReserves: NormalizedReserves

 outputReserves: NormalizedReserves

 marketRate: Rate

}

​

export interface TradeDetails {

 marketDetailsPre: MarketDetails

 marketDetailsPost: MarketDetails

 tradeType: TRADE\_TYPE

 tradeExact: TRADE\_EXACT

 inputAmount: TokenAmountNormalized

 outputAmount: TokenAmountNormalized

 executionRate: Rate

 marketRateSlippage: BigNumber

 executionRateSlippage: BigNumber

}

​

export type MethodArgument = BigNumber \| number \| string

​

export interface ExecutionDetails {

 exchangeAddress: string

 methodName: string

 methodId: string

 value: BigNumber

 methodArguments: MethodArgument\[\]

}

​

export type FlexibleFormat = BigNumber.Format \| boolean

​

export function isFormat\(flexibleFormat: FlexibleFormat\): flexibleFormat is BigNumber.Format {

 const format: BigNumber.Format = flexibleFormat as BigNumber.Format

 return typeof format !== 'boolean'

}

​

export interface FormatSignificantOptions {

 significantDigits: number

 roundingMode: BigNumber.RoundingMode

 forceIntegerSignificance: boolean

 format: FlexibleFormat

}

​

export interface FormatFixedOptions {

 decimalPlaces: number

 roundingMode: BigNumber.RoundingMode

 dropTrailingZeros: boolean

 underflowBehavior: FIXED\_UNDERFLOW\_BEHAVIOR

 format: FlexibleFormat

}


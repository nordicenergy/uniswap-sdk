# Constants

import BigNumber from 'bignumber.js'

​

import ERC20 from './abis/ERC20.json'

import FACTORY from './abis/FACTORY.json'

import EXCHANGE from './abis/EXCHANGE.json'

​

export const ETH = 'ETH'

​

export enum SUPPORTED\_CHAIN\_ID {

 Mainnet = 1,

 Ropsten = 3,

 Rinkeby = 4,

 Kovan = 42

}

​

export const FACTORY\_ADDRESS: { \[key: number\]: string } = {

}

​

export const FACTORY\_ABI: string = JSON.stringify\(FACTORY\)

export const EXCHANGE\_ABI: string = JSON.stringify\(EXCHANGE\)

​

export enum TRADE\_TYPE {

 ETH\_TO\_TOKEN = 'ETH\_TO\_TOKEN',

 TOKEN\_TO\_ETH = 'TOKEN\_TO\_ETH',

 TOKEN\_TO\_TOKEN = 'TOKEN\_TO\_TOKEN'

}

​

export enum TRADE\_EXACT {

 INPUT = 'INPUT',

 OUTPUT = 'OUTPUT'

}

​

export enum TRADE\_METHODS {

 ethToTokenSwapInput = 'ethToTokenSwapInput',

 ethToTokenTransferInput = 'ethToTokenTransferInput',

 ethToTokenSwapOutput = 'ethToTokenSwapOutput',

 ethToTokenTransferOutput = 'ethToTokenTransferOutput',

 tokenToEthSwapInput = 'tokenToEthSwapInput',

 tokenToEthTransferInput = 'tokenToEthTransferInput',

 tokenToEthSwapOutput = 'tokenToEthSwapOutput',

 tokenToEthTransferOutput = 'tokenToEthTransferOutput',

 tokenToTokenSwapInput = 'tokenToTokenSwapInput',

 tokenToTokenTransferInput = 'tokenToTokenTransferInput',

 tokenToTokenSwapOutput = 'tokenToTokenSwapOutput',

 tokenToTokenTransferOutput = 'tokenToTokenTransferOutput'

}

​

export const TRADE\_METHOD\_IDS: { \[key: string\]: string } = {

}

​

export enum FIXED\_UNDERFLOW\_BEHAVIOR {

 ZERO = 'ZERO',

 LESS\_THAN = 'LESS\_THAN',

 ONE\_DIGIT = 'ONE\_DIGIT'

}


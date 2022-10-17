# Documentation

All cakewswap pairs consist of two different tokens. ETHW is not a native currency in cakewswap, and is represented only by WETHW in the pairs.

The canonical WETHW address used by the cakewswap interface is `0x7bf88d2c0e32de92cdaf2d43ccdc23e8edfd5990`.

Results are cached for 5 minutes (or 300 seconds).

Contracts:
- Factory: 0xe97352E2d3a4F418044a91533a2379dbd11b425d
- Router: 0xb8dad6ef36940a7c881980860ea28822994e22bd
- CAKEW Token: 0x8a521189BfEDf99b1Dc84BC21571cF8B799DbD4D


## [`/summary`](https://api.cakewswap.finance/api/dex/summary)

Returns data for the top cakewswap pairs, sorted by reserves.

### Request

`GET https://api.cakewswap.finance/api/dex/summary`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // ERC20 token addresses, joined by an underscore
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // last 24h volume denominated in token0
      "quote_volume": "...",          // last 24h volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_ethw": "..."         // liquidity denominated in ETHW
    },
    // ...
  }
}
```

## [`/tokens`](https://api.cakewswap.finance/api/dex/tokens)

Returns the tokens in the top pairs on cakewswap, sorted by reserves.

### Request

`GET https://api.cakewswap.finance/api/dex/tokens`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x...": {                        // the address of the ERC20 token
      "name": "...",                  // not necessarily included for ERC20 tokens
      "symbol": "...",                // not necessarily included for ERC20 tokens
      "price": "...",                 // price denominated in USD
      "price_ethw": "...",             // price denominated in ETHW
    },
    // ...
  }
}
```

## [`/tokens/0x...`](https://api.cakewswap.finance/api/dex/tokens/0x8a521189BfEDf99b1Dc84BC21571cF8B799DbD4D)

Returns the token information, based on address.

### Request

`GET https://api.cakewswap.finance/api/dex/tokens/0x8a521189BfEDf99b1Dc84BC21571cF8B799DbD4D`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "name": "...",                    // not necessarily included for ERC20 tokens
    "symbol": "...",                  // not necessarily included for ERC20 tokens
    "price": "...",                   // price denominated in USD
    "price_ethw": "...",               // price denominated in ETHW
  }
}
```

## [`/tickers`](https://api.cakewswap.finance/api/dex/tickers)

Returns data for the top cakewswap tickers, sorted by reserves.

### Request

`GET https://api.cakewswap.finance/api/dex/tickers`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of ETHW and ERC20 tokens, joined by an underscore
      "id": "0x...",                  // pair id
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_ethw": "..."          // liquidity denominated in ETHW


      "pood_id": "0x...",             // pood id
      "base_currency": "..",          // Symbol/currency code of a the base cryptoasset, eg. CAKEW
      "target_currency": "..",        // Symbol/currency code of a the target cryptoasset, eg. ETHW
      "last_price": "..",             // Last transacted price of base currency based on given target currency (unit in base or target)
      "base_volume": "...",           // volume denominated in token0
      "target_volume": "...",         // volume denominated in token1
    },
    // ...
  }
}
```

## [`/pairs`](https://api.cakewswap.finance/api/dex/pairs)

Returns data for the top cakewswap pairs, sorted by reserves.

### Request

`GET https://api.cakewswap.finance/api/dex/pairs`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of ETHW and ERC20 tokens, joined by an underscore
      "id": "0x...",                  // pair id
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_ethw": "..."          // liquidity denominated in ETHW


      "pood_id": "0x...",             // pood id
      "base": "..",                   // Symbol/currency code of a the base cryptoasset, eg. CAKEW
      "target": "..",                 // Symbol/currency code of a the base cryptoasset, eg. ETHW
      "target": "..",                 // Ticker with delimiter to separate base/target
    },
    // ...
  }
}
```

## [`/pairs/0x...`](https://api.cakewswap.finance/api/dex/pairs/0x654c7a4a18d9BF19770869bDF07F7dbb82B6e57d)

Returns the pair information, based on address.

### Request

`GET https://api.cakewswap.finance/api/dex/pairs/0x654c7a4a18d9BF19770869bDF07F7dbb82B6e57d`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
      "id": "0x...",                  // pair id
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_ethw": "..."          // liquidity denominated in ETHW
  }
}
```

# candlestick-convert
 
This package allow you to convert OHLC candles from given timeframe into a new timeframe.

**Supported formats:** 
- CCXT OHLC  ``` [Object,Object] ```
- Array  ``` [[],[]] ```

**Features:**
- No Dependencies
- Performance single for..loop() used
- Skip missing candles

**Todo optional features:**
- Return data integrity problems (missing timeframes)
- Add OHLC / 4 or Volume Weighted price calculation

**Install:**
```
npm install candlestick-convert
```

**Usage:**
```
const Converter = require("candlestick-convert");

const btc_usdt_1m = [
[1563495000000, 10581.14, 10598.17, 10580.6, 10583.71, 30.145722],
  [1563495060000, 10583.74, 10584.6, 10560, 10578, 31.324269],
  [1563495120000, 10579.73, 10580.77, 10558.57, 10562.48, 41.152152],
  [1563495180000, 10561.56, 10583.74, 10557.69, 10583.26, 47.229129],
  ];

// Convert to 2m Candles
let btc_usdt_2m = Converter.array(btc_usdt_1m, 60, 120);


/* CCXT OHLC support */

const link_btc_1m = [
  {
    time: 1563625680000,
    open: 0.00024824,
    high: 0.00024851,
    low: 0.00024798,
    close: 0.00024831,
    volume: 2264
  },
  {
    time: 1563625740000,
    open: 0.00024817,
    high: 0.00024832,
    low: 0.00024795,
    close: 0.00024828,
    volume: 3145
  }];

// Convert to 2m Candles
let link_btc_2m  = Converter.json(link_btc_1m, 60, 120);

```




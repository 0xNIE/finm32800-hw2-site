# Dataframe: `hw2:fed_funds_futures` - 30-Day Fed Funds Futures (ZQ) Daily Bars

Pulled by src/pull_fed_funds_futures.py from Databento's CME Globex MDP 3.0 dataset (GLBX.MDP3) with the parent symbol ZQ.FUT (stype_in = parent) and the ohlcv-1d schema, one bar per contract per trading day. Columns: date (tz-naive trading date), symbol, open, high, low, close, volume. Prices are quoted as 100 minus the average daily effective fed funds rate over the contract month, so 100 - close is the market's forecast of that average rate. Symbols like ZQU6 are outright monthly contracts; symbols with a hyphen (ZQU6-ZQZ6) are calendar spreads and are dropped by fedwatch.filter_outright_contracts. Far-dated months trade thinly and can be missing on a given day, so use each contract's latest close on or before the date of interest. Requires a Databento API key; the pull checks that the query costs $0.00 before downloading.


## DataFrame Glimpse

```
Rows: 11751
Columns: 7
$ date   <datetime[ns]> 2026-10-25 00:00:00
$ symbol          <str> 'ZQG7-ZQJ7'
$ open            <f64> 15.5
$ high            <f64> 16.0
$ low             <f64> 15.5
$ close           <f64> 16.0
$ volume          <u64> 333


```

## Dataframe Manifest

| Dataframe Name                 | 30-Day Fed Funds Futures (ZQ) Daily Bars                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| Dataframe ID                   | [fed_funds_futures](../dataframes/hw2/fed_funds_futures.md)                                       |
| Sources                        | CME Group                                          |
| Providers                      | Databento                                        |
| Provider Links                 | https://databento.com/datasets/GLBX.MDP3                                   |
| Tags                           | Monetary Policy, Futures, Fed Funds, Fedwatch                                             |
| Access Types                   |                                       |
| How is data pulled?            | Databento Historical API via Python                                                   |
| Data available up to (min)     | 2026-10-25 00:00:00                                                             |
| Data available up to (max)     | 2026-10-25 00:00:00                                                             |
| Dataframe Path                 | /Users/jonathonnie/Documents/finm32800-hw2/_data/fed_funds_futures.parquet                                             |


**Linked Charts:**


- [hw2:fedwatch_latest_forecast](../../charts/hw2.fedwatch_latest_forecast.md)



## Pipeline Manifest

| Pipeline Name                   | HW 2: The Yield Curve and the Policy Path                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [hw2](../../../index.md)              |
| Maintainer                      | Jeremiah Bejarano               |
| Contributors                    | Jeremiah Bejarano |
| Repository                     | https://github.com/hw-finm-32800/hw2                  |
| Pipeline Web Page               | <a href="file:///Users/jonathonnie/Documents/finm32800-hw2/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-10-26 11:59:28           |
| OS Compatibility                | Windows, Linux, macOS |
| Linked Dataframes               |  [hw2:crsp_treasury_consolidated](../../dataframes/hw2/crsp_treasury_consolidated.md)<br>  [hw2:fed_yield_curve](../../dataframes/hw2/fed_yield_curve.md)<br>  [hw2:fed_funds_futures](../../dataframes/hw2/fed_funds_futures.md)<br>  |


**Build Commands:**
```
doit

```


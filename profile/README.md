# Roq Trading Solutions


## What

* API's, libraries and tools so you can build your own low latency trading system
* Gateways supporting market data and order management
* Event logs to capture historical data
* Simulation framework


## Framework / Objectives

* Open API with no lock-in (MIT license)
* Tools are free to use (with a strong motivation to open source)
* Very low latency to support market making (single digit microsecond software response time on a high-end server)
* Gateways require a license agreement (free to download and use for evaluation and development purposes)

> We do not do NDA


## Design

![Design](/profile/architecture_reference.svg)


## Strategies

An API provides you with a uniform interface to communicate with the gateways.
The API is designed to make it easy to switch between simulation and live trading
without having to change strategy code.
Strategies should preferably be implemented using C++23.

> There is experimental Python support but we do not recommend it for anything
> low latency.


## Exchanges / Gateways

> The full list can be found [here](https://roq-trading.com/docs/introduction/gateways/).

### Traditional

* [CME](https://roq-trading.com/docs/reference/gateways/traditional/roq-cme/) -- supports iLink, MBO and MBP

### Cryptocurrency

* Binance [spot](https://roq-trading.com/docs/reference/gateways/crypto/roq-binance/) and [futures](https://roq-trading.com/docs/reference/gateways/crypto/roq-binance-futures/)
* [BitMEX](https://roq-trading.com/docs/reference/gateways/crypto/roq-bitmex/)
* [Bybit](https://roq-trading.com/docs/reference/gateways/crypto/roq-bybit/)
* [Coinbase PRO](https://roq-trading.com/docs/reference/gateways/crypto/roq-coinbase-pro/)
* [Deribit](https://roq-trading.com/docs/reference/gateways/crypto/roq-deribit/) -- supports multicast
* Gate.io [spot](https://roq-trading.com/docs/reference/gateways/crypto/roq-gate/) and [futures](https://roq-trading.com/docs/reference/gateways/crypto/roq-gate-futures/)
* Huobi [spot](https://roq-trading.com/docs/reference/gateways/crypto/roq-huobi/) and [futures](https://roq-trading.com/docs/reference/gateways/crypto/roq-huobi-futures/)
* Kraken [spot](https://roq-trading.com/docs/reference/gateways/crypto/roq-kraken/) and [futures](https://roq-trading.com/docs/reference/gateways/crypto/roq-kraken-futures/)
* KuCoin [spot](https://roq-trading.com/docs/reference/gateways/crypto/roq-kucoin/) and [futures](https://roq-trading.com/docs/reference/gateways/crypto/roq-kucoin-futures/)
* [OKX](https://roq-trading.com/docs/reference/gateways/crypto/roq-okx/)

## Bridges

* [FIX](https://roq-trading.com/docs/reference/clients/bridges/roq-fix-bridge/)

... and [more](https://roq-trading.com/docs/reference/clients/bridges/)

> We aim to integrate with the major open source projects and third-party vendors.
> Please [reach out](mailto:info@roq-trading.com) if you have specific requirements.


## Adapters

* [ClickHouse](https://roq-trading.com/docs/reference/clients/adapters/roq-clickhouse/)

... and [more](https://roq-trading.com/docs/reference/clients/adapters/)

> We strongly recommend [ClickHouse](https://clickhouse.com/) which provides
> exceptionally good performance vs ease-of-use.


## Event Logs

Events (messages) are collected into a log which can be used for simulation,
query (_"what happened?"_) and export to third-party database solutions.
The event logs are backwards compatible and therefore the basis for a historical
database.


## Metrics / Alerts / Dashboards

All components support [Prometheus](https://prometheus.io/)' exposition format.
[AlertManager](https://prometheus.io/docs/alerting/latest/alertmanager/)
allows you to automatically send alerts based on exceptional conditions.
[Grafana](https://grafana.com/) allows you to build custom monitoring dashboards.

> Please [reach out](mailto:info@roq-trading.com) if you have any questions about
> integration with alternative monitoring solutions.

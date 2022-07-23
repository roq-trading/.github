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
Strategies should preferably be implemented using C++20.

> There is experimental Python support but we do not recommend it for anything
> low latency.


## Exchanges / Gateways

* Binance [spot](https://roq-trading.com/docs/reference/gateways/roq-binance/) and [futures](https://roq-trading.com/docs/reference/gateways/roq-binance-futures/)
* [BitMEX](https://roq-trading.com/docs/reference/gateways/roq-bitmex/)
* Bybit [spot](https://roq-trading.com/docs/reference/gateways/roq-bybit/) and [futures](https://roq-trading.com/docs/reference/gateways/roq-bybit-futures/)
* [Coinbase PRO](https://roq-trading.com/docs/reference/gateways/roq-coinbase-pro/)
* [Deribit](https://roq-trading.com/docs/reference/gateways/roq-deribit/) including support for the **multicast** protocol
* [FTX](https://roq-trading.com/docs/reference/gateways/roq-ftx/)
* Huobi [spot](https://roq-trading.com/docs/reference/gateways/roq-huobi/) and [futures](https://roq-trading.com/docs/reference/gateways/roq-huobi-futures/)
* Kraken [spot](https://roq-trading.com/docs/reference/gateways/roq-kraken/) and [futures](https://roq-trading.com/docs/reference/gateways/roq-kraken-futures/)
* KuCoin [spot](https://roq-trading.com/docs/reference/gateways/roq-kucoin/) and [futures](https://roq-trading.com/docs/reference/gateways/roq-kucoin-futures/)
* [OKX](https://roq-trading.com/docs/reference/gateways/roq-okx/)

... and [more](https://roq-trading.com/docs/introduction/gateways/)


## Event Logs

Events (messages) are collected into a log which can be used for simulation,
query (_"what happened?"_) and export to third-party database solutions.
The event logs are backwards compatible and therefore the basis for a historical
database.


## Adapters

* [ClickHouse](https://roq-trading.com/docs/reference/adapters/roq-clickhouse/)
  on [GitHub](https://github.com/roq-trading/roq-clickhouse-adapter)

... and [more](https://roq-trading.com/docs/reference/adapters/)

> We strongly recommend [ClickHouse](https://clickhouse.com/) which provides
> exceptionally good performance vs ease-of-use.


## Bridges

* [FIX](https://roq-trading.com/docs/reference/bridges/roq-fix-bridge/)
* [JSON](https://roq-trading.com/docs/reference/bridges/roq-json-bridge/)
* [Redis](https://roq-trading.com/docs/reference/bridges/roq-redis-bridge/)
  on [GitHub](https://github.com/roq-trading/roq-redis-bridge)
* [ZeroMQ](https://roq-trading.com/docs/reference/bridges/roq-zeromq-bridge/)
  on [GitHub](https://github.com/roq-trading/roq-zeromq-bridge)

... and [more](https://roq-trading.com/docs/reference/bridges/)

> We aim to integrate with the major open source projects and third-party vendors.
> Please [reach out](mailto:info@roq-trading.com) if you have specific requirements.


## Metrics / Alerts / Dashboard

All components support [Prometheus](https://prometheus.io/)' exposition format.
[AlertManager](https://prometheus.io/docs/alerting/latest/alertmanager/)
allows you to automatically send alerts based on exceptional conditions.
[Grafana](https://grafana.com/) allows you to build custom monitoring dashboards.

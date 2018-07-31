# AusBits Client for Elixir

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add ausbits_client to your list of dependencies in `mix.exs`:

        def deps do
          [{:ausbits_client, "~> 0.1.1"}]
        end

  2. Ensure ausbits_client is started before your application:

        def application do
          [applications: [:ausbits_client]]
        end

## Useage

More API document please visit [AusBits API](https://ausbits.com.au/documents/api_v2)

```
# Public API
AusbitsClient.ticker market
AusbitsClient.trades market

# Private API
# Create a API server with your key and secret.
AusbitsClient.Server.start_link id, key, secret

# Get Member info
AusbitsClient.me id

# Entry Order
AusbitsClient.ask id, market, [{private, volume}, ...]
AusbitsClient.bid id, market, [{private, volume}, ...]
AusbitsClient.entry id, market, [{side, private, volume}, ...]

# Take Order info
AusbitsClient.order id, order.id

# Cancel Order or all
AusbitsClient.cancel_all id
AusbitsClient.cancel_ask id
AusbitsClient.cancel_bid id

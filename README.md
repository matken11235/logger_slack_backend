# LoggerSlackBackend

**TODO: Add description**

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `logger_slack_backend` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:logger_slack_backend, "~> 0.1.0"}
  ]
end
```

```elixir:config.exs
config :logger_slack_backend,
  webhook_url: System.get_env("SLACK_WEBHOOK_URL")

# Configures Elixir's Logger
config :logger,
  backends: [
    :console,
    {LoggerSlackBackend, :info},
    {LoggerSlackBackend, :error}
  ]

config :logger, :console,
  format: "$time $metadata[$level] $message\n",
  metadata: [:request_id]

config :logger, :info,
  level: :info,
  format: "$time $metadata[$level] $message\n",
  metadata: [:request_id]

config :logger, :error,
  level: :error,
  format: "$time $metadata[$level] $message\n",
  metadata: [:request_id]
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/logger_slack_backend](https://hexdocs.pm/logger_slack_backend).


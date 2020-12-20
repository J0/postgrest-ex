# Postgrestex

Elixir Client library for Postgrest. The design mirrors that of [postgrest-py](https://github.com/supabase/postgrest-py)

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `postgrestex` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:postgrestex, "~> 0.1.0"}
  ]
end
```


Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/postgrestex](https://hexdocs.pm/postgrestex).

## Getting Started


TODOS:
- [ ] Support Filter Request
- [ ] Support Select Requests
- [ ] Write Tests
- [ ] Support Auth
- [ ] Document all functions

## Initialize and read from a table
```
 Client.init("api") |> Client.from("todos") |> Client.call()
```

### Create
```
Client.init("api") |> Client.from("todos") |> RequestBuilder.insert(%{"name": "Singapore", "capital": "Singapore" }, False) |> Client.call()
```

### Read
```
Client.init("api") |> Client.from("todos") |> RequestBuilder.select(["id", "name"]) |>Client.call()
```

### Update
```
Client.init("api") |> Client.from("todos") |> FilterRequestBuilder.eq("name", "Singapore") |> RequestBuilder.update(%{"capital": "Sentosa"}) |> Client.call()
```

### Delete
```
Client.init("api") |> Client.from("todos") |> FilterRequestBuilder.eq("name", "Singapore") |> Client.delete() |> Client.call()
```



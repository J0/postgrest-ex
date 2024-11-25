# Postgrestex

## Maintenance mode

This repository is moving into maintenance mode. Please use the new [Postgrest-ex](https://github.com/supabase-community/postgrest-ex) library. We will archive the hex.pm library as well. Thank you for your usage over the past few years.

**Status: POC**

Elixir Postgrestex library for Postgrest. The design mirrors that of [postgrest-py](https://github.com/supabase/postgrest-py)

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `postgrestex` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:postgrestex, "~> 0.1.2"}
  ]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/postgrestex](https://hexdocs.pm/postgrestex).

## Getting Started

## Initialize and read from a table

First, `import Postgrestex`

Then do any one of the following options:

### Create

Example usage:

```
init("public") \
      |> from("users") \
      |> insert(
        %{username: "nevergonna", age_range: "[1,2)", status: "ONLINE", catchphrase: "giveyouup"},
        false
      ) \
      |> call()
```

### Read

Example usage:

```
init("public") \
    |> from("messages") \
    |> select(["id", "username"]) \
    |> call()
```

### Update

Example usage:

```
  init("public") \
    |> from("users") \
    |> eq("username", "supabot") \
    |> update(%{status: "OFFLINE"}) \
    |> call()
```

### Delete

Example usage:

```
init("public") \
  |> from("users") \
  |> eq("username", "nevergonna") \
  |> eq("status", "ONLINE") \
  |> delete() \
  |> call()
```

## Testing

Run `mix test`

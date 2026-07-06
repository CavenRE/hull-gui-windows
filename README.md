# Hull Desktop for Windows

A native Windows desktop app for [Hull](https://github.com/CavenRE/hull), built with WPF.

**Status: in progress.** Not yet released. The Hull CLI is the shipping product; this
app is catching up to it.

## What this is

The app is a thin client over Hull's daemon. It talks to a running `hulld` over its
local `/v1` HTTP API (see [`openapi.yaml`](openapi.yaml)) and holds no logic of its
own, so anything it does you can also do from the `hull` CLI. Close the app and the
daemon keeps your sites running.

## Requirements

- Hull installed, with its daemon running (`hulld`). Get the CLI from
  [github.com/CavenRE/hull](https://github.com/CavenRE/hull).
- .NET 8 SDK to build.

## Build

```powershell
dotnet build Hull.Gui.csproj
```

## The API contract

[`openapi.yaml`](openapi.yaml) is a vendored copy of Hull's frozen `/v1` API
(`docs/api/openapi.yaml` in the hull repo). It is the only thing this app depends on.
When you target a newer Hull, refresh this file and update against it; the daemon's
drift test in the hull repo keeps the contract honest.

## How you will install it

Once released, you will not clone this repo to use the app. You will either run
`hull gui install` from the CLI, which fetches the build from this repo's releases, or
download a bundled installer that lays down the CLI and the app together (with a
CLI-only option inside it).

## License

MIT, same as Hull. See [LICENSE](LICENSE).

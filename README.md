# nim-overpass

- [OpenStreetMap](https://openstreetmap.org) [Overpass](https://overpass-turbo.eu) API Lib,
[Async & Sync](https://github.com/juancarlospaco/nim-overpass/blob/master/src/overpass.nim#L74),
with & without SSL, [command line App (50Kb)](https://github.com/juancarlospaco/nim-overpass/releases).

![OpenStreetMap](https://raw.githubusercontent.com/juancarlospaco/nim-overpass/master/osm.jpg "OpenStreetMap")


# Install

- `nimble install overpass`


# Use

- `./overpass --color --lower --timeout=9 "node(1422314245)"`

- The output format is automatically set to JSON, `JsonNode` type.
- You must omit the `[out:json];` and `;out;` on the Query.


# Requisites

- None.


# API

`search*(this: Overpass | AsyncOverpass, query: string, api_url = api_main0)`

- `this` is `Overpass(timeout=int8)` for Synchronous code or `AsyncOverpass(timeout=int8)` for Asynchronous code.
- `query` is an overpass query, `string` type, required.
- `api_url` is an overpass HTTP API URL, `string` type, optional.

- The `timeout` argument is on Seconds.
- OpenStreetMap API limits the length of all key and value strings to a maximum of 255 characters.
- For Proxy support define a `Overpass.proxy` or `AsyncOverpass.proxy` of `Proxy` type.
- No OS-specific code, so it should work on Linux, Windows and Mac. Not JS.


# FAQ

- How to Edit the OpenStreetMap using this lib ?.

You can not, Overpass is a read-only OpenStreetMap API, but optimized for read speed.

- This works without SSL ?.

Yes.

- This works with SSL ?.

Yes.

- This works with Asynchronous code ?.

Yes.

- This works with Synchronous code ?.

Yes.

- This requires API Key or Login ?.

No.

- This requires Credit Card or Payments ?.

No.

- How do I build the Query string ?.

Use Nims [FMT strings module](https://nim-lang.org/docs/strformat.html).

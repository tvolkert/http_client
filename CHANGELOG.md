# Changelog

## 1.0.4

- `Request.change` to override `url`, `headers` or `body`. `addHeader` to extend current headers.

## 1.0.3

- `CloseClientFn` in `UpdatingClient`.

## 1.0.2

- Class-level `invalidateOnError` and `forceCloseOnError` for `UpdatingClient`.
- `TrackingClient.toString()` forwards to delegate client.

## 1.0.1

- Automatic `Content-Length` header when body is specified (in `ConsoleClient`).

## 1.0.0+1

- Fix: cleanup of past clients in `UpdatingClient`.

## 1.0.0

**BREAKING CHANGES**
- `Request.body` is used instead of `bodyStream` and `bodyBytes`.
- `Stream<List<int>>` inputs are no longer supported, use restartable `FutureOr<Stream<List<int>>> StreamFn()` instead.
- Single `Response` constructor, `body` become an untyped holder (use `bodyAsStream` if migrating uses). 

Other updates

- Explicit expiration, and optional on-exception expiration in `UpdatingClient`.
- Support form-encoded values as request body.
- Support `File` with `Request.body` on `ConsoleClient`.
- Support native request types with `Request.body` and `Response.body` on `BrowserClient`.

## 0.6.0

- Support `close({bool force})` on the API (and on console).
- Support `Response.done` to indicate when the underlying input stream has been read and completed.
- `TrackingClient` to keep track of ongoing and completed request count (with content read support). 
- `UpdatingClient` to automatically recreate client resources (or rotate proxies) after some use.

## 0.5.1

- Code update: Dart 2.1(-dev) lints.

## 0.5.0

- Dart 2

## 0.4.4+1

- Fix header override bug.

## 0.4.3

- Record redirect info (when available).
- `Response.requestAddress` to have the address where the request was opened at.
- **BREAKING**: `Response.remoteAddress` renamed to `responseAddress`.

## 0.4.2

- Better `Headers` handling.
- Request properties: `persistentConnection`, `followRedirects`, `maxRedirects`.
- ConsoleClient properties: `idleTimeout`, `maxConnectionsPerHost`, `autoUncompress`, `userAgent`.
- `Response.remoteAddress` (in ConsoleClient).

## 0.4.1

- Enabled Dart2 Preview for analysis.

## 0.4.0

- Fix deprecated API use.
- Fix header wrapping in requests.
- Default header values in `ConsoleClient`.

## 0.3.1

- Added http proxy option to the console client.

## 0.3.0

- Removed dependency on `http` package.

## 0.2.2

- Add executor support to rate-limit the clients.

## 0.2.1

- Add curl support.

## 0.2.0

**Breaking changes**:

- instead of exporting the `http` package, `http_client` provides its own API
  - *console* and *browser* clients continue to use the `http` package
  - preparation to support [node_io](https://github.com/dglogik/node_io.dart)
    for apps that want to be packaged as a single binary (e.g. `.exe`)
  - preparation to support the Fetch API (e.g. in service workers)

- removed the awkward `newHttpClient()` methods.

## 0.1.0

- Exporting classes from the `http` package (version: `^0.1.13`).

### 0.1.0+1

- Exporting streaming request and response.

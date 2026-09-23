# opencode-brave-websearch

An OpenCode v2 plugin that registers [Brave Search](https://brave.com/search/api/) as the default websearch provider.

## Configuration

Set `BRAVE_SEARCH_API_KEY` in the OpenCode process environment. Add the package to `opencode.jsonc`:

```jsonc
{
  "websearch": { "provider": "brave" },
  "plugins": ["opencode-brave-websearch"]
}
```

For a local checkout in this repository, the plugin entry in `opencode/opencode.common.jsonc` is `"../plugins/opencode-brave-search"` instead.

The plugin sends the search query to `https://api.search.brave.com/res/v1/web/search` with the API key in the `X-Subscription-Token` header. It maps Brave web results to OpenCode search results. A missing key fails the request.

See [development.md](docs/development.md) for local tests and publishing.

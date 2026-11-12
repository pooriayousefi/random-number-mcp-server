# random-number-mcp-server

A standalone C++20 Model Context Protocol (MCP) server for random sampling from common probability distributions.

## Tools

17 sampling tools covering uniform, Bernoulli, binomial, geometric, negative-binomial, Poisson, exponential, gamma, Weibull, extreme-value, normal, log-normal, chi-squared, Cauchy, Fisher-F, and Student-t distributions.

## Dependency

The shared MCP implementation is provided by [mcpxx](https://github.com/pooriayousefi/mcpxx), pinned as a Git submodule at commit `c7753ec6b15eb15b6ecdfed82b93ace745ba0c6b` under `external/mcpxx`.

## Clone and build

```sh
git clone --recurse-submodules https://github.com/pooriayousefi/random-number-mcp-server.git
cd random-number-mcp-server
make
```

Or compile directly:

```sh
clang++ -std=c++20 -O2 -pthread -Wall -Wextra -Wpedantic \\
  -I external/mcpxx/include \\
  src/random_number_mcp_tool_server.cpp \\
  -o bin/random_number_mcp_tool_server
```

On Windows with MinGW, add `-lws2_32`.

## Run

Stdio (default): `./bin/random_number_mcp_tool_server`

Streamable HTTP: `./bin/random_number_mcp_tool_server http 127.0.0.1 8095`

The HTTP endpoint is `/mcp`. Bind to loopback unless suitable network controls are configured.

## License

Apache-2.0. See [LICENSE](LICENSE).

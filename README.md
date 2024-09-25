
# Avalanche Subnet

This README provides examples of various API endpoints for interacting with the Avalanche network. These endpoints are useful for monitoring the health of the network, querying information about the network and node, and performing administrative operations.

## Health Check API

### `health.health`
Returns the last set of health check results.

```bash
curl -H 'Content-Type: application/json' --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "health.health",
    "params": {
        "tags": ["2AKbBT8jFUfUsUJ2hhRiDUnAAajJdNhTKeNgEe3q77spMj1N8F"]
    }
}' 'http://localhost:9650/ext/health'
```

## Information APIs

### `info.acps`
Returns peer preferences for Avalanche Community Proposals (ACPs).

```bash
curl -sX POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.acps",
    "params" : {}
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.isBootstrapped`
Checks whether a given chain is done bootstrapping.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.isBootstrapped",
    "params": {
        "chain": "X"
    }
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getBlockchainID`
Given a blockchain's alias, get its ID.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getBlockchainID",
    "params": {
        "alias": "X"
    }
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getNetworkID`
Get the ID of the network this node is participating in.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getNetworkID"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getNetworkName`
Get the name of the network this node is participating in.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getNetworkName"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getNodeID`
Get the ID, the BLS key, and the proof of possession (BLS signature) of this node.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getNodeID"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getNodeIP`
Get the IP address of this node.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getNodeIP"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getNodeVersion`
Get the version of this node.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getNodeVersion"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getTxFee`
Get the transaction fees of the network.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getTxFee"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.getVMs`
Get the virtual machines installed on this node.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.getVMs",
    "params" : {}
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.peers`
Get a description of peer connections.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.peers",
    "params": {
        "nodeIDs": []
    }
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

### `info.uptime`
Returns the network's observed uptime of this node. This is the only reliable source of data for your node's uptime. Other sources may use data gathered with incomplete (limited) information.

```bash
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id"     : 1,
    "method" : "info.uptime"
}' -H 'Content-Type: application/json;' http://127.0.0.1:9650/ext/info
```

---

This README section provides clear explanations and formatted `curl` commands for interacting with the Avalanche node APIs. Each API call is accompanied by its purpose and the necessary `curl` command to execute it.
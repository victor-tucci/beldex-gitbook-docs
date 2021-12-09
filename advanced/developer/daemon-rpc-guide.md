# Daemon RPC Guide

## Introducton

This is a list of the RPC calls, their inputs and outputs, and examples of each.&#x20;

Many RPC calls use the JSON RPC interface while others use their own interfaces, as demonstrated below.

Note: "atomic units" refer to the smallest fraction of 1 BELDEX which is 1e9 atomic units.

## RPC Methods

* [COMMAND\_RPC\_GET\_HEIGHT](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_height)
* [COMMAND\_RPC\_GET\_BLOCKS\_FAST](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_blocks\_fast)
* [COMMAND\_RPC\_GET\_BLOCKS\_BY\_HEIGHT](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_blocks\_by\_height)
* [COMMAND\_RPC\_GET\_ALT\_BLOCKS\_HASHES](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_hashes\_fast)
* [COMMAND\_RPC\_GET\_HASHES\_FAST](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_hashes\_fast)
* [COMMAND\_RPC\_GET\_ADDRESS\_TXS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_address\_txs)
* [COMMAND\_RPC\_GET\_ADDRESS\_INFO](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_address\_info)
* [COMMAND\_RPC\_GET\_UNSPENT\_OUTS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_unspent\_outs)
* [COMMAND\_RPC\_GET\_RANDOM\_OUTS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_random\_outs)
* [COMMAND\_RPC\_SUBMIT\_RAW\_TX](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_submit\_raw\_tx)
* [COMMAND\_RPC\_LOGIN](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_login)
* [COMMAND\_RPC\_IMPORT\_WALLET\_REQUEST](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_import\_wallet\_request)
* [COMMAND\_RPC\_GET\_TRANSACTIONS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_transactions)
* [COMMAND\_RPC\_IS\_KEY\_IMAGE\_SPENT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_is\_key\_image\_spent)
* [COMMAND\_RPC\_GET\_TX\_GLOBAL\_OUTPUTS\_INDEXES](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_tx\_global\_outputs\_indexes)
* [COMMAND\_RPC\_GET\_OUTPUTS\_BIN](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_outputs\_bin)
* [COMMAND\_RPC\_GET\_OUTPUTS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_outputs)
* [COMMAND\_RPC\_SEND\_RAW\_TX](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_send\_raw\_tx)
* [COMMAND\_RPC\_START\_MINING](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_start\_mining)
* [COMMAND\_RPC\_GET\_INFO](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_info)
* [COMMAND\_RPC\_GET\_ALL\_MASTER\_NODES\_KEYS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_all\_master\_nodes\_keys)
* [COMMAND\_RPC\_STOP\_MINING](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_stop\_mining)
* [COMMAND\_RPC\_MINING\_STATUS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_mining\_status)
* [COMMAND\_RPC\_SAVE\_BC](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_save\_bc)
* [COMMAND\_RPC\_GETBLOCKCOUNT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_getblockcount)
* [COMMAND\_RPC\_GETBLOCKHASH](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_getblockhash)
* [COMMAND\_RPC\_GETBLOCKTEMPLATE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_getblocktemplate)
* [COMMAND\_RPC\_SUBMITBLOCK](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_submitblock)
* [COMMAND\_RPC\_GENERATEBLOCKS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_generateblocks)
* [COMMAND\_RPC\_GET\_LAST\_BLOCK\_HEADER](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_last\_block\_header)
* [COMMAND\_RPC\_GET\_BLOCK\_HEADER\_BY\_HASH](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_block\_header\_by\_hash)
* [COMMAND\_RPC\_GET\_BLOCK\_HEADER\_BY\_HEIGHT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_block\_header\_by\_height)
* [COMMAND\_RPC\_GET\_BLOCK](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_block)
* [COMMAND\_RPC\_SET\_LOG\_HASH\_RATE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_set\_log\_hash\_rate)
* [COMMAND\_RPC\_SET\_LOG\_LEVEL](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_set\_log\_level)
* [COMMAND\_RPC\_SET\_LOG\_CATEGORIES](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_set\_log\_categories)
* [COMMAND\_RPC\_GET\_TRANSACTION\_POOL](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_transaction\_pool)
* [COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_HASHES\_BIN](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_transaction\_pool\_hashes\_bin)
* [COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_HASHES](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_transaction\_pool\_hashes)
* [COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_BACKLOG](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_transaction\_pool\_backlog)
* [COMMAND\_RPC\_GET\_CONNECTIONS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_connections)
* [COMMAND\_RPC\_GET\_BLOCK\_HEADERS\_RANGE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_block\_headers\_range)
* [COMMAND\_RPC\_STOP\_DAEMON](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_stop\_daemon)
* [COMMAND\_RPC\_GET\_LIMIT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_limit)
* [COMMAND\_RPC\_SET\_LIMIT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_set\_limit)
* [COMMAND\_RPC\_OUT\_PEERS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_out\_peers)
* [COMMAND\_RPC\_IN\_PEERS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_in\_peers)
* [COMMAND\_RPC\_START\_SAVE\_GRAPH](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_start\_save\_graph)
* [COMMAND\_RPC\_STOP\_SAVE\_GRAPH](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_stop\_save\_graph)
* [COMMAND\_RPC\_HARD\_FORK\_INFO](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_hard\_fork\_info)
* [COMMAND\_RPC\_GETBANS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_getbans)
* [COMMAND\_RPC\_SETBANS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_setbans)
* [COMMAND\_RPC\_FLUSH\_TRANSACTION\_POOL](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_flush\_transaction\_pool)
* [COMMAND\_RPC\_GET\_OUTPUT\_HISTOGRAM](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_output\_histogram)
* [COMMAND\_RPC\_GET\_VERSION](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_version)
* [COMMAND\_RPC\_GET\_COINBASE\_TX\_SUM](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_coinbase\_tx\_sum)
* [COMMAND\_RPC\_GET\_BASE\_FEE\_ESTIMATE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_base\_fee\_estimate)
* [COMMAND\_RPC\_GET\_ALTERNATE\_CHAINS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_alternate\_chains)
* [COMMAND\_RPC\_UPDATE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_update)
* [COMMAND\_RPC\_RELAY\_TX](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_relay\_tx)
* [COMMAND\_RPC\_SYNC\_INFO](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_sync\_info)
* [COMMAND\_RPC\_GET\_OUTPUT\_DISTRIBUTION](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_output\_distribution)
* [COMMAND\_RPC\_POP\_BLOCKS](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_pop\_blocks)
* [COMMAND\_RPC\_PRUNE\_BLOCKCHAIN](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_prune\_blockchain)
* [COMMAND\_RPC\_GET\_QUORUM\_STATE](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_quorum\_state)
* [COMMAND\_RPC\_GET\_QUORUM\_STATE\_BATCHED](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_quorum\_state\_batched)
* [COMMAND\_RPC\_GET\_MASTER\_NODE\_REGISTRATION\_CMD\_RAW](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_master\_node\_registration\_cmd\_raw)
* [COMMAND\_RPC\_GET\_MASTER\_NODE\_REGISTRATION\_CMD](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_master\_node\_registration\_cmd)
* [COMMAND\_RPC\_GET\_MASTER\_NODE\_KEY](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_master\_node\_key)
* [COMMAND\_RPC\_GET\_MASTER\_NODES](https://docs.beldex.io/advanced/developer/daemon-rpc-guide#command\_rpc\_get\_master\_nodes)
* [COMMAND\_RPC\_GET\_STAKING\_REQUIREMENT](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_staking\_requirement)
* [COMMAND\_RPC\_GET\_MASTER\_NODE\_BLACKLISTED\_KEY\_IMAGES](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_master\_node\_blacklisted\_key\_images)
* [COMMAND\_RPC\_GET\_OUTPUT\_BLACKLIST](https://docs.beldex.io/Developer/DaemonRPCBeta/#command\_rpc\_get\_output\_blacklist)

### COMMAND\_RPC\_GET\_HEIGHT

Get the node's current height.

**Endpoints:** _/get\_height_, _/getheight_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_height -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "height": 234767,
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `height - uint64`: The current blockchain height according to the queried daemon.
* `status - string`: Generic RPC error code. "OK" is the success value.
* `untrusted - bool`: If the result is obtained using bootstrap mode, and therefore not trusted `true`, or otherwise `false`.

### COMMAND\_RPC\_GET\_BLOCKS\_FAST

Get all blocks info. Binary request.

**Endpoints:** _/get\_blocks.bin_, _/getblocks.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_blocks.bin -d '
{
  "block_ids": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
  "start_height": 123,
  "prune": true,
  "no_miner_tx": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "blocks": [{
      "block": "sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9",
      "txs": ["sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9", ...]
    }, ...],
  "start_height": 123,
  "current_height": 123,
  "status": "OK",
  "output_indices": [{
      "indices": [{
          "indices": [123, ...]
        }, ...]
    }, ...],
  "untrusted": false
}
```

**Inputs:**

* `block_ids - string[64][]`: First 10 blocks id goes sequential, next goes in pow(2,n) offset, like 2, 4, 8, 16, 32, 64 and so on, and the last one is always genesis block
* `start_height - uint64`: The starting block's height.
* `prune - bool`: Prunes the blockchain, drops off 7/8 off the block iirc.
* `no_miner_tx - bool`: Optional (false by default).

**Outputs:**

* `blocks - block_complete_entry[]`: Array of block complete entries
  * `block - string`
  * `txs - string[]`
* `start_height - uint64`: The starting block's height.
* `current_height - uint64`: The current block height.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `output_indices - block_output_indices[]`: Array of indices.
  * `indices - tx_output_indices[]`: Array of TX output indices:
    * `indices - uint64[]`: Array of unsigned int.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_BLOCKS\_BY\_HEIGHT

Get blocks by height. Binary request.

**Endpoints:** _/get\_blocks\_by\_height.bin_, _/getblocks\_by\_height.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_blocks_by_height.bin -d '
{
  "heights": [123, ...]
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "blocks": [{
      "block": "sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9",
      "txs": ["sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9", ...]
    }, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `heights - uint64[]`: List of block heights

**Outputs:**

* `blocks - block_complete_entry[]`: Array of block complete entries
  * `block - string`
  * `txs - string[]`
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_ALT\_BLOCKS\_HASHES

Get the known blocks hashes which are not on the main chain.

**Endpoints:** _/get\_alt\_blocks\_hashes_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_alt_blocks_hashes -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "blks_hashes": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `blks_hashes - string[]`: List of alternative blocks hashes to main chain.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_HASHES\_FAST

Get hashes. Binary request.

**Endpoints:** _/get\_hashes.bin_, _/gethashes.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_hashes.bin -d '
{
  "block_ids": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
  "start_height": 123
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "m_block_ids": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
  "start_height": 123,
  "current_height": 123,
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `block_ids - string[64][]`: First 10 blocks id goes sequential, next goes in pow(2,n) offset, like 2, 4, 8, 16, 32, 64 and so on, and the last one is always genesis block \*/
* `start_height - uint64`: The starting block's height.

**Outputs:**

* `m_block_ids - string[64][]`: Binary array of hashes, See block\_ids above.
* `start_height - uint64`: The starting block's height.
* `current_height - uint64`: The current block height.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_ADDRESS\_TXS

TODO: Undocumented light wallet RPC call

**Inputs:**

* `address - string`: Address of wallet to receive tx information.&#x20;
* `view_key - string`: View key of Address.

**Outputs:**

* `total_received - uint64`: Total Beldex received in atomic units.
* `total_received_unlocked - uint64`: OpenMonero only
* `scanned_height - uint64`
* `transactions - transaction[]`
  * `id - uint64`: The transaction identifier.
  * `hash - string`: The hash of this transaction.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `total_received - uint64`: Total Beldex received in atomic units.
  * `total_sent - uint64`: Total beldex sent in atomic units.
  * `unlock_time - uint64`: Unlock time in blocks.
  * `height - uint64`: Block height transaction was made.
  * `spent_outputs - spent_output[]`: List of spent outputs.
    * `amount - uint64`: Amount transferred.
    * `key_image - string`: Unique cryptographic key associated with output.
    * `tx_pub_key - string`: Pubkey associated with transaction.
    * `out_index - uint64`: Index for transaction.
    * `mixin - uint32`: The number of other signatures (aside from yours) in the ring signature that authorises the transaction.
  * `payment_id - string`: The payment ID of the transaction.
  * `coinbase - bool`: States if the transaction is a coinbase transaction. `true` if the transaction is coinbase, `false` if not.
  * `mempool - bool`: States if the transaction is sitting in the mempool. `true if the transaction is,`false\` if not.
  * `mixin - uint32`: The number of other signatures (aside from yours) in the ring signature that authorises the transaction.
* `blockchain_height - uint64`
* `scanned_block_height - uint64`
* `status - string`

### COMMAND\_RPC\_GET\_ADDRESS\_INFO

TODO: Undocumented light wallet RPC call

**Inputs:**

* `address - string`
* `view_key - string`

**Outputs:**

* `locked_funds - uint64`
* `total_received - uint64`
* `total_sent - uint64`
* `scanned_height - uint64`
* `scanned_block_height - uint64`
* `start_height - uint64`
* `transaction_height - uint64`
* `blockchain_height - uint64`
* `spent_outputs - spent_output[]`
  * `amount - uint64`
  * `key_image - string`
  * `tx_pub_key - string`
  * `out_index - uint64`
  * `mixin - uint32`

### COMMAND\_RPC\_GET\_UNSPENT\_OUTS

TODO: Undocumented light wallet RPC call

**Inputs:**

* `amount - string`
* `address - string`
* `view_key - string`: OpenMonero specific
* `mixin - uint64`
* `use_dust - bool`
* `dust_threshold - string`

**Outputs:**

* `amount - uint64`
* `outputs - output[]`
  * `amount - uint64`
  * `public_key - string`
  * `index - uint64`
  * `global_index - uint64`
  * `rct - string`
  * `tx_hash - string`
  * `tx_pub_key - string`
  * `tx_prefix_hash - string`
  * `spend_key_images - string[]`
  * `timestamp - uint64`
  * `height - uint64`
* `per_kb_fee - uint64`
* `status - string`
* `reason - string`

### COMMAND\_RPC\_GET\_RANDOM\_OUTS

TODO: Undocumented light wallet RPC call

**Inputs:**

* `amounts - string[]`
* `count - uint32`

**Outputs:**

* `amount_outs - amount_out[]`
  * `amount - uint64`
  * `outputs - output[]`
    * `public_key - string`
    * `global_index - uint64`
    * `rct - string`: 64+64+64 characters long ( + + )
* `Error - string`

### COMMAND\_RPC\_SUBMIT\_RAW\_TX

TODO: Undocumented light wallet RPC call

**Inputs:**

* `address - string`
* `view_key - string`
* `tx - string`

**Outputs:**

* `status - string`
* `error - string`

### COMMAND\_RPC\_LOGIN

TODO: Undocumented light wallet RPC call

**Inputs:**

* `address - string`
* `view_key - string`
* `create_account - bool`

**Outputs:**

* `status - string`
* `reason - string`
* `new_address - bool`

### COMMAND\_RPC\_IMPORT\_WALLET\_REQUEST

TODO: Undocumented light wallet RPC call

**Inputs:**

* `address - string`
* `view_key - string`

**Outputs:**

* `payment_id - string`
* `import_fee - uint64`
* `new_request - bool`
* `request_fulfilled - bool`
* `payment_address - string`
* `status - string`

### COMMAND\_RPC\_GET\_TRANSACTIONS

Look up one or more transactions by hash.

**Endpoints:** _/get\_transactions_, _/gettransactions_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_transactions -d '
{
  "txs_hashes": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...],
  "decode_as_json": true,
  "prune": true,
  "split": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "txs_as_hex": ["TODO(beldex): Write example string", ...],
  "txs_as_json": ["TODO(beldex): Write example string", ...],
  "missed_tx": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...],
  "txs": [{
      "tx_hash": "b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123",
      "as_hex": "TODO(beldex): Write example string",
      "pruned_as_hex": "TODO(beldex): Write example string",
      "prunable_as_hex": "TODO(beldex): Write example string",
      "prunable_hash": "b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123",
      "as_json": "TODO(beldex): Write example string",
      "in_pool": true,
      "double_spend_seen": true,
      "block_height": 123,
      "block_timestamp": 123,
      "output_indices": [123, ...]
    }, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `txs_hashes - string[]`: List of transaction hashes to look up.
* `decode_as_json - bool`: Optional (`false` by default). If set true, the returned transaction information will be decoded rather than binary.
* `prune - bool`: Prunes the blockchain, drops off 7/8 off the block iirc. Optional (`False` by default).
* `split - bool`: Optional (`false` by default).

**Outputs:**

* `txs_as_hex - string[]`: Full transaction information as a hex string (old compatibility parameter)
* `txs_as_json - string[]`: Transactions decoded as json (old compat)
* `missed_tx - string[]`: (Optional - returned if not empty) Transaction hashes that could not be found.
* `txs - entry[]`: Array of structure entry as follows:
  * `tx_hash - string`: Transaction hash.
  * `as_hex - string`: Full transaction information as a hex string.
  * `pruned_as_hex - string`
  * `prunable_as_hex - string`
  * `prunable_hash - string`
  * `as_json - string`: List of transaction info.
  * `in_pool - bool`: States if the transaction is in pool (`true`) or included in a block (`false`).
  * `double_spend_seen - bool`: States if the transaction is a double-spend (`true`) or not (`false`).
  * `block_height - uint64`: Block height including the transaction.
  * `block_timestamp - uint64`: Unix time at chich the block has been added to the blockchain.
  * `output_indices - uint64[]`: List of transaction indexes.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_IS\_KEY\_IMAGE\_SPENT

Check if outputs have been spent using the key image associated with the output.

**Endpoints:** _/is\_key\_image\_spent_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/is_key_image_spent -d '
{
  "key_images": ["TODO(beldex): Write example string", ...]
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "spent_status": [0, 1, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `key_images - string[]`: List of key image hex strings to check.

**Outputs:**

* `spent_status - int[]`: List of statuses for each image checked. Statuses are follows: 0 = unspent, 1 = spent in blockchain, 2 = spent in transaction pool
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_TX\_GLOBAL\_OUTPUTS\_INDEXES

Get global outputs of transactions. Binary request.

**Endpoints:** _/get\_o\_indexes.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_o_indexes.bin -d '
{
  "txid": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70"
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "o_indexes": [123, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `txid - string[64]`: Binary txid.

**Outputs:**

* `o_indexes - uint64[]`: List of output indexes
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_OUTPUTS\_BIN

Get outputs. Binary request.

**Endpoints:** _/get\_outs.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_outs.bin -d '
{
  "outputs": [{
      "amount": 123,
      "index": 123
    }, ...],
  "get_txid": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "outs": [{
      "key": ,
      "mask": ,
      "unlocked": true,
      "height": 234767,
      "txid": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70"
    }, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `outputs - get_outputs_out[]`: Array of structure `get_outputs_out`.
  * `amount - uint64`: Amount of Beldex in TXID.
  * `index - uint64`
* `get_txid - bool`: TXID

**Outputs:**

* `outs - outkey[]`: List of outkey information.
  * `key - crypto::public_key`: The public key of the output.
  * `mask - rct::key`
  * `unlocked - bool`: States if output is locked (`false`) or not (`true`).
  * `height - uint64`: Block height of the output.
  * `txid - string[64]`: Transaction id.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_OUTPUTS

**Endpoints:** _/get\_outs_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_outs -d '
{
  "outputs": [{
      "amount": 123,
      "index": 123
    }, ...]
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "outs": [{
      "key": "TODO(beldex): Write example string",
      "mask": "TODO(beldex): Write example string",
      "unlocked": true,
      "height": 234767,
      "txid": "b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123"
    }, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `outputs - get_outputs_out[]`: Array of structure `get_outputs_out`.
  * `amount - uint64`: Amount of Beldex in TXID.
  * `index - uint64`

**Outputs:**

* `outs - outkey[]`: List of outkey information.
  * `key - string`: The public key of the output.
  * `mask - string`
  * `unlocked - bool`: States if output is locked (`false`) or not (`true`).
  * `height - uint64`: Block height of the output.
  * `txid - string`: Transaction id.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_SEND\_RAW\_TX

Broadcast a raw transaction to the network.

**Endpoints:** _/send\_raw\_transaction_, _/sendrawtransaction_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/send_raw_transaction -d '
{
  "tx_as_hex": "TODO(beldex): Write example string",
  "do_not_relay": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "reason": "TODO(beldex): Write example string",
  "not_relayed": true,
  "untrusted": false,
  "tvc": 
}
```

**Inputs:**

* `tx_as_hex - string`: Full transaction information as hexidecimal string.
* `do_not_relay - bool`: Stop relaying transaction to other nodes (default is `false`).

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.
* `reason - string`: Additional information. Currently empty or "Not relayed" if transaction was accepted but not relayed.
* `not_relayed - bool`: Transaction was not relayed (true) or relayed (false).
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).
* `tvc - tx_verification_context`

### COMMAND\_RPC\_START\_MINING

Start mining on the daemon.

**Endpoints:** _/start\_mining_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/start_mining -d '
{
  "miner_address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk",
  "threads_count": 123,
  "do_background_mining": true,
  "ignore_battery": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `miner_address - string`: Account address to mine to.
* `threads_count - uint64`: Number of mining thread to run.
* `do_background_mining - bool`: States if the mining should run in background (`true`) or foreground (`false`).
* `ignore_battery - bool`: States if battery state (on laptop) should be ignored (`true`) or not (`false`).

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.

### COMMAND\_RPC\_GET\_INFO

Retrieve general information about the state of your node and the network.

**Endpoints:** _/get\_info_, _/getinfo_, _get\_info_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_info"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "height": 234767,
  "target_height": 123,
  "difficulty": 123,
  "target": 123,
  "tx_count": 123,
  "tx_pool_size": 123,
  "alt_blocks_count": 123,
  "outgoing_connections_count": 123,
  "incoming_connections_count": 123,
  "rpc_connections_count": 123,
  "white_peerlist_size": 123,
  "grey_peerlist_size": 123,
  "mainnet": true,
  "testnet": true,
  "stagenet": true,
  "nettype": "MAINNET",
  "top_block_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
  "cumulative_difficulty": 123,
  "block_size_limit": 123,
  "block_weight_limit": 123,
  "block_size_median": 123,
  "block_weight_median": 123,
  "start_time": 123,
  "free_space": 123,
  "offline": true,
  "untrusted": false,
  "bootstrap_daemon_address": "127.0.0.1:22023",
  "height_without_bootstrap": 123,
  "was_bootstrap_ever_used": true,
  "database_size": 123,
  "update_available": true,
  "version": "TODO(beldex): Write example string"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `height - uint64`: Current length of longest chain known to daemon.
* `target_height - uint64`: The height of the next block in the chain.
* `difficulty - uint64`: Network difficulty (analogous to the strength of the network).
* `target - uint64`: Current target for next proof of work.
* `tx_count - uint64`: Total number of non-coinbase transaction in the chain.
* `tx_pool_size - uint64`: Number of transactions that have been broadcast but not included in a block.
* `alt_blocks_count - uint64`: Number of alternative blocks to main chain.
* `outgoing_connections_count - uint64`: Number of peers that you are connected to and getting information from.
* `incoming_connections_count - uint64`: Number of peers connected to and pulling from your node.
* `rpc_connections_count - uint64`: Number of RPC client connected to the daemon (Including this RPC request).
* `white_peerlist_size - uint64`: White Peerlist Size
* `grey_peerlist_size - uint64`: Grey Peerlist Size
* `mainnet - bool`: States if the node is on the mainnet (`true`) or not (`false`).
* `testnet - bool`: States if the node is on the testnet (`true`) or not (`false`).
* `stagenet - bool`: States if the node is on the stagenet (`true`) or not (`false`).
* `nettype - string`: Nettype value used.
* `top_block_hash - string`: Hash of the highest block in the chain.
* `cumulative_difficulty - uint64`: Cumulative difficulty of all blocks in the blockchain.
* `block_size_limit - uint64`: Maximum allowed block size.
* `block_weight_limit - uint64`: Maximum allowed block weight.
* `block_size_median - uint64`: Median block size of latest 100 blocks.
* `block_weight_median - uint64`: Median block weight of latest 100 blocks.
* `start_time - uint64`: Start time of the daemon, as UNIX time.
* `free_space - uint64`: Available disk space on the node.
* `offline - bool`: States if the node is offline (`true`) or online (`false`).
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).
* `bootstrap_daemon_address - string`: Bootstrap node to give immediate usability to wallets while syncing by proxying RPC to it. (Note: the replies may be untrustworthy).
* `height_without_bootstrap - uint64`: Current length of the local chain of the daemon.
* `was_bootstrap_ever_used - bool`: States if a bootstrap node has ever been used since the daemon started.
* `database_size - uint64`: Current size of Blockchain data.
* `update_available - bool`: States if a update is available ('true') and if one is not available ('false').
* `version - string`: Current version of software running.

### COMMAND\_RPC\_GET\_ALL\_MASTER\_NODES\_KEYS

Retrieve all Master Node Keys.

**Endpoints:** _get\_all\_master\_nodes\_keys_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_all_master_nodes_keys",
  "params": {
    "fully_funded_nodes_only": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "keys": ["TODO(beldex): Write example string", ...]
}
```

**Inputs:**

* `fully_funded_nodes_only - bool`: Return keys for master nodes if they are funded and working on the network

**Outputs:**

* `keys - string[]`: Returns as base32z of the hex key, for Beldex network internal usage

### COMMAND\_RPC\_STOP\_MINING

Stop mining on the daemon.

**Endpoints:** _/stop\_mining_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/stop_mining -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.

### COMMAND\_RPC\_MINING\_STATUS

Get the mining status of the daemon.

**Endpoints:** _/mining\_status_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/mining_status -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "active": true,
  "speed": 123,
  "threads_count": 8,
  "address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk",
  "is_background_mining_enabled": true
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.
* `active - bool`: States if mining is enabled (`true`) or disabled (`false`).
* `speed - uint64`: Mining power in hashes per seconds.
* `threads_count - uint32`: Number of running mining threads.
* `address - string`: Account address daemon is mining to. Empty if not mining.
* `is_background_mining_enabled - bool`: States if the mining is running in background (`true`) or foreground (`false`).

### COMMAND\_RPC\_SAVE\_BC

Save the blockchain. The blockchain does not need saving and is always saved when modified,&#x20;

however it does a sync to flush the filesystem cache onto the disk for safety purposes against Operating System or Hardware crashes.

**Endpoints:** _/save\_bc_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/save_bc -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.

### COMMAND\_RPC\_GETBLOCKCOUNT

Look up how many blocks are in the longest chain known to the node.

**Endpoints:** _get\_block\_count_, _getblockcount_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblockcount",
  "params": {
    "request": ["TODO(beldex): Write example string", ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "count": 123,
  "status": "OK"
}
```

**Inputs:**

* `request - string[]`

**Outputs:**

* `count - uint64`: Number of blocks in longest chain seen by the node.
* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_GETBLOCKHASH

Look up a block's hash by its height.

**Endpoints:** _on\_get\_block\_hash_, _on\_getblockhash_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"on_getblockhash",
  "params": {
    "request": [123, ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "response": "TODO(beldex): Write example string"
}
```

**Inputs:**

* `request - uint64[]`: Block height (int array of length 1).

**Outputs:**

* `response - string`: Block hash (string).

### COMMAND\_RPC\_GETBLOCKTEMPLATE

Get a block template on which mining a new block.

**Endpoints:** _get\_block\_template_, _getblocktemplate_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblocktemplate",
  "params": {
    "reserve_size": 123,
    "wallet_address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk"
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "difficulty": 123,
  "height": 234767,
  "reserved_offset": 123,
  "expected_reward": 123,
  "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
  "blocktemplate_blob": "sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9",
  "blockhashing_blob": "sd2b5f838e8cc7774d92f5a6ce0d72cb9bd8db2ef28948087f8a50ff46d188dd9",
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `reserve_size - uint64`: Max 255 bytes
* `wallet_address - string`: Address of wallet to receive coinbase transactions if block is successfully mined.

**Outputs:**

* `difficulty - uint64`: Difficulty of next block.
* `height - uint64`: Height on which to mine.
* `reserved_offset - uint64`: Reserved offset.
* `expected_reward - uint64`: Coinbase reward expected to be received if block is successfully mined.
* `prev_hash - string`: Hash of the most recent block on which to mine the next block.
* `blocktemplate_blob - string`: Blob on which to try to mine a new block.
* `blockhashing_blob - string`: Blob on which to try to find a valid nonce.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_SUBMITBLOCK

Submit a mined block to the network.

**Endpoints:** _submit\_block_, _submitblock_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"submitblock",
  "params": {
    "request": ["TODO(beldex): Write example string", ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `request - string[]`: Block blob data - array of strings; list of block blobs which have been mined. See get\_block\_template to get a blob on which to mine.

**Outputs:**

* `status - string`: Block submit status.

### COMMAND\_RPC\_GENERATEBLOCKS

Developer only.

**Endpoints:** _generateblocks_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"generateblocks",
  "params": {
    "amount_of_blocks": 123,
    "wallet_address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk"
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "height": 234767,
  "status": "OK"
}
```

**Inputs:**

* `amount_of_blocks - uint64`
* `wallet_address - string`

**Outputs:**

* `height - uint64`
* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_GET\_LAST\_BLOCK\_HEADER

Block header information for the most recent block is easily retrieved with this method. No inputs are needed.

**Endpoints:** _get\_last\_block\_header_, _getlastblockheader_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getlastblockheader",
  "params": {
    "fill_pow_hash": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "block_header": {
    "major_version": 11,
    "minor_version": 11,
    "timestamp": 123,
    "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "nonce": 2130706433,
    "orphan_status": true,
    "height": 234767,
    "depth": 123,
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "difficulty": 25179406071,
    "cumulative_difficulty": 25179406071,
    "reward": 123,
    "miner_reward": 123,
    "block_size": 123,
    "block_weight": 123,
    "num_txes": 123,
    "pow_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "long_term_weight": 123
  },
  "untrusted": false
}
```

**Inputs:**

* `fill_pow_hash - bool`: Tell the daemon if it should fill out pow\_hash field.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `block_header - block_header_response`: A structure containing block header information.
  * `major_version - uint8`: The major version of the beldex protocol at this block height.
  * `minor_version - uint8`: The minor version of the beldex protocol at this block height.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `prev_hash - string`: The hash of the block immediately preceding this block in the chain.
  * `nonce - uint32`: A cryptographic random one-time number used in mining a Beldex block.
  * `orphan_status - bool`: Usually `false`. If `true`, this block is not part of the longest chain.
  * `height - uint64`: The number of blocks preceding this block on the blockchain.
  * `depth - uint64`: The number of blocks succeeding this block on the blockchain. A larger number means an older block.
  * `hash - string`: The hash of this block.
  * `difficulty - uint64`: The strength of the Beldex network based on mining power.
  * `cumulative_difficulty - uint64`: The cumulative strength of the Beldex network based on mining power.
  * `reward - uint64`: The amount of new generated in this block and rewarded to the miner, foundation and master Nodes. Note: 1 BELDEX = 1e12 atomic units.
  * `miner_reward - uint64`: The amount of new generated in this block and rewarded to the miner. Note: 1 BELDEX = 1e12 atomic units.&#x20;
  * `block_size - uint64`: The block size in bytes.
  * `block_weight - uint64`: The block weight in bytes.
  * `num_txes - uint64`: Number of transactions in the block, not counting the coinbase tx.
  * `pow_hash - string`: The hash of the block's proof of work.
  * `long_term_weight - uint64`: Long term weight of the block.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_BLOCK\_HEADER\_BY\_HASH

Block header information can be retrieved using either a block's hash or height. This method includes a block's hash as an input parameter to retrieve basic information about the block.

**Endpoints:** _get\_block\_header\_by\_hash_, _getblockheaderbyhash_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblockheaderbyhash",
  "params": {
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "fill_pow_hash": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "block_header": {
    "major_version": 11,
    "minor_version": 11,
    "timestamp": 123,
    "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "nonce": 2130706433,
    "orphan_status": true,
    "height": 234767,
    "depth": 123,
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "difficulty": 25179406071,
    "cumulative_difficulty": 25179406071,
    "reward": 123,
    "miner_reward": 123,
    "block_size": 123,
    "block_weight": 123,
    "num_txes": 123,
    "pow_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "long_term_weight": 123
  },
  "untrusted": false
}
```

**Inputs:**

* `hash - string`: The block's SHA256 hash.
* `fill_pow_hash - bool`: Tell the daemon if it should fill out pow\_hash field.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `block_header - block_header_response`: A structure containing block header information.
  * `major_version - uint8`: The major version of the beldex protocol at this block height.
  * `minor_version - uint8`: The minor version of the beldex protocol at this block height.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `prev_hash - string`: The hash of the block immediately preceding this block in the chain.
  * `nonce - uint32`: A cryptographic random one-time number used in mining a Beldex block.
  * `orphan_status - bool`: Usually `false`. If `true`, this block is not part of the longest chain.
  * `height - uint64`: The number of blocks preceding this block on the blockchain.
  * `depth - uint64`: The number of blocks succeeding this block on the blockchain. A larger number means an older block.
  * `hash - string`: The hash of this block.
  * `difficulty - uint64`: The strength of the Beldex network based on mining power.
  * `cumulative_difficulty - uint64`: The cumulative strength of the Beldex network based on mining power.
  * `reward - uint64`: The amount of new generated in this block and rewarded to the miner, foundation and master Nodes. Note: 1 BELDEX = 1e12 atomic units.
  * `miner_reward - uint64`: The amount of new generated in this block and rewarded to the miner. Note: 1 BELDEX = 1e12 atomic units.&#x20;
  * `block_size - uint64`: The block size in bytes.
  * `block_weight - uint64`: The block weight in bytes.
  * `num_txes - uint64`: Number of transactions in the block, not counting the coinbase tx.
  * `pow_hash - string`: The hash of the block's proof of work.
  * `long_term_weight - uint64`: Long term weight of the block.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_BLOCK\_HEADER\_BY\_HEIGHT

Similar to get\_block\_header\_by\_hash above, this method includes a block's height as an input parameter to retrieve basic information about the block.

**Endpoints:** _get\_block\_header\_by\_height_, _getblockheaderbyheight_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblockheaderbyheight",
  "params": {
    "height": 234767,
    "fill_pow_hash": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "block_header": {
    "major_version": 11,
    "minor_version": 11,
    "timestamp": 123,
    "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "nonce": 2130706433,
    "orphan_status": true,
    "height": 234767,
    "depth": 123,
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "difficulty": 25179406071,
    "cumulative_difficulty": 25179406071,
    "reward": 123,
    "miner_reward": 123,
    "block_size": 123,
    "block_weight": 123,
    "num_txes": 123,
    "pow_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "long_term_weight": 123
  },
  "untrusted": false
}
```

**Inputs:**

* `height - uint64`: The block's height.
* `fill_pow_hash - bool`: Tell the daemon if it should fill out pow\_hash field.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `block_header - block_header_response`: A structure containing block header information.
  * `major_version - uint8`: The major version of the beldex protocol at this block height.
  * `minor_version - uint8`: The minor version of the beldex protocol at this block height.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `prev_hash - string`: The hash of the block immediately preceding this block in the chain.
  * `nonce - uint32`: A cryptographic random one-time number used in mining a Beldex block.
  * `orphan_status - bool`: Usually `false`. If `true`, this block is not part of the longest chain.
  * `height - uint64`: The number of blocks preceding this block on the blockchain.
  * `depth - uint64`: The number of blocks succeeding this block on the blockchain. A larger number means an older block.
  * `hash - string`: The hash of this block.
  * `difficulty - uint64`: The strength of the Beldex network based on mining power.
  * `cumulative_difficulty - uint64`: The cumulative strength of the Beldex network based on mining power.
  * `reward - uint64`: The amount of new generated in this block and rewarded to the miner, foundation and master Nodes. Note: 1 BELDEX = 1e12 atomic units.
  * `miner_reward - uint64`: The amount of new generated in this block and rewarded to the miner. Note: 1 BELDEX = 1e12 atomic units.&#x20;
  * `block_size - uint64`: The block size in bytes.
  * `block_weight - uint64`: The block weight in bytes.
  * `num_txes - uint64`: Number of transactions in the block, not counting the coinbase tx.
  * `pow_hash - string`: The hash of the block's proof of work.
  * `long_term_weight - uint64`: Long term weight of the block.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_BLOCK

Full block information can be retrieved by either block height or hash, like with the above block header calls.&#x20;

For full block information, both lookups use the same method, but with different input parameters.

**Endpoints:** _get\_block_, _getblock_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblock",
  "params": {
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "height": 234767,
    "fill_pow_hash": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "block_header": {
    "major_version": 11,
    "minor_version": 11,
    "timestamp": 123,
    "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "nonce": 2130706433,
    "orphan_status": true,
    "height": 234767,
    "depth": 123,
    "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "difficulty": 25179406071,
    "cumulative_difficulty": 25179406071,
    "reward": 123,
    "miner_reward": 123,
    "block_size": 123,
    "block_weight": 123,
    "num_txes": 123,
    "pow_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
    "long_term_weight": 123
  },
  "miner_tx_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
  "tx_hashes": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...],
  "blob": "TODO(beldex): Write example string",
  "json": "TODO(beldex): Write example string",
  "untrusted": false
}
```

**Inputs:**

* `hash - string`: The block's hash.
* `height - uint64`: The block's height.
* `fill_pow_hash - bool`: Tell the daemon if it should fill out pow\_hash field.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `block_header - block_header_response`: A structure containing block header information. See get\_last\_block\_header.
  * `major_version - uint8`: The major version of the beldex protocol at this block height.
  * `minor_version - uint8`: The minor version of the beldex protocol at this block height.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `prev_hash - string`: The hash of the block immediately preceding this block in the chain.
  * `nonce - uint32`: A cryptographic random one-time number used in mining a Beldex block.
  * `orphan_status - bool`: Usually `false`. If `true`, this block is not part of the longest chain.
  * `height - uint64`: The number of blocks preceding this block on the blockchain.
  * `depth - uint64`: The number of blocks succeeding this block on the blockchain. A larger number means an older block.
  * `hash - string`: The hash of this block.
  * `difficulty - uint64`: The strength of the Beldex network based on mining power.
  * `cumulative_difficulty - uint64`: The cumulative strength of the Beldex network based on mining power.
  * `reward - uint64`: The amount of new generated in this block and rewarded to the miner, foundation and master Nodes. Note: 1 BELDEX = 1e12 atomic units.
  * `miner_reward - uint64`: The amount of new generated in this block and rewarded to the miner. Note: 1 BELDEX = 1e12 atomic units.&#x20;
  * `block_size - uint64`: The block size in bytes.
  * `block_weight - uint64`: The block weight in bytes.
  * `num_txes - uint64`: Number of transactions in the block, not counting the coinbase tx.
  * `pow_hash - string`: The hash of the block's proof of work.
  * `long_term_weight - uint64`: Long term weight of the block.
* `miner_tx_hash - string`: Miner transaction information
* `tx_hashes - string[]`: List of hashes of non-coinbase transactions in the block. If there are no other transactions, this will be an empty list.
* `blob - string`: Hexadecimal blob of block information.
* `json - string`: JSON formatted block details.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_SET\_LOG\_HASH\_RATE

Set the log hash rate display mode.

**Endpoints:** _/set\_log\_hash\_rate_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/set_log_hash_rate -d '
{
  "visible": true
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `visible - bool`: States if hash rate logs should be visible (true) or hidden (false)

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.

### COMMAND\_RPC\_SET\_LOG\_LEVEL

Set the daemon log level. By default, log level is set to `0`.

**Endpoints:** _/set\_log\_level_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/set_log_level -d '
{
  "level": 8
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `level - int8`: Daemon log level to set from `0` (less verbose) to `4` (most verbose)

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.

### COMMAND\_RPC\_SET\_LOG\_CATEGORIES

Set the daemon log categories. Categories are represented as a comma separated list of `<Category>:<level>` (similarly to syslog standard `<Facility>:<Severity-level>`), where:

Category is one of the following: \* (all facilities), default, net, net.http, net.p2p, logging, net.trottle, blockchain.db, blockchain.db.lmdb, bcutil, checkpoints, net.dns, net.dl,

i18n, perf,stacktrace, updates, account, cn ,difficulty, hardfork, miner, blockchain, txpool, cn.block\_queue, net.cn, daemon, debugtools.deserialize, debugtools.objectsizes, device.ledger,&#x20;

wallet.gen\_multisig, multisig, bulletproofs, ringct, daemon.rpc, wallet.simplewallet, WalletAPI, wallet.ringdb, wallet.wallet2, wallet.rpc, tests.core.

Level is one of the following: FATAL - higher level, ERROR, WARNING, INFO, DEBUG, TRACE.

Lower level A level automatically includes higher level. By default, categories are set to:

`*:WARNING,net:FATAL,net.p2p:FATAL,net.cn:FATAL,global:INFO,verify:FATAL,stacktrace:INFO,logging:INFO,msgwriter:INFO`

Setting the categories to "" prevent any logs to be outputed.

**Endpoints:** _/set\_log\_categories_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/set_log_categories -d '
{
  "categories": "TODO(beldex): Write example string"
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "categories": "TODO(beldex): Write example string"
}
```

**Inputs:**

* `categories - string`: Optional, daemon log categories to enable

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.
* `categories - string`: Daemon log enabled categories

### COMMAND\_RPC\_GET\_TRANSACTION\_POOL

Show information about valid transactions seen by the node but not yet mined into a block,&#x20;

as well as spent key image information for the txpool in the node's memory.

**Endpoints:** _/get\_transaction\_pool_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_transaction_pool -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "transactions": [{
      "id_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "tx_json": "TODO(beldex): Write example string",
      "blob_size": 123,
      "weight": 123,
      "fee": 123,
      "max_used_block_id_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "max_used_block_height": 123,
      "kept_by_block": true,
      "last_failed_height": 123,
      "last_failed_id_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "receive_time": 123,
      "relayed": true,
      "last_relayed_time": 123,
      "do_not_relay": true,
      "double_spend_seen": true,
      "tx_blob": "TODO(beldex): Write example string"
    }, ...],
  "spent_key_images": [{
      "id_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "txs_hashes": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...]
    }, ...],
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `transactions - tx_info[]`: List of transactions in the mempool are not in a block on the main chain at the moment:
  * `id_hash - string`: The transaction ID hash.
  * `tx_json - string`: JSON structure of all information in the transaction
  * `blob_size - uint64`: The size of the full transaction blob.
  * `weight - uint64`: The weight of the transaction.
  * `fee - uint64`: The amount of the mining fee included in the transaction, in atomic units.
  * `max_used_block_id_hash - string`: Tells the hash of the most recent block with an output used in this transaction.
  * `max_used_block_height - uint64`: Tells the height of the most recent block with an output used in this transaction.
  * `kept_by_block - bool`: States if the tx was included in a block at least once (`true`) or not (`false`).
  * `last_failed_height - uint64`: If the transaction validation has previously failed, this tells at what height that occured.
  * `last_failed_id_hash - string`: Like the previous, this tells the previous transaction ID hash.
  * `receive_time - uint64`: The Unix time that the transaction was first seen on the network by the node.
  * `relayed - bool`: States if this transaction has been relayed
  * `last_relayed_time - uint64`: Last unix time at which the transaction has been relayed.
  * `do_not_relay - bool`: States if this transaction should not be relayed.
  * `double_spend_seen - bool`: States if this transaction has been seen as double spend.
  * `tx_blob - string`: Hexadecimal blob represnting the transaction.
* `spent_key_images - spent_key_image_info[]`: List of spent output key images:
  * `id_hash - string`: Key image.
  * `txs_hashes - string[]`: List of tx hashes of the txes (usually one) spending that key image.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_HASHES\_BIN

Get hashes from transaction pool. Binary request.

**Endpoints:** _/get\_transaction\_pool\_hashes.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_transaction_pool_hashes.bin -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "tx_hashes": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `tx_hashes - string[64][]`: List of transaction hashes,
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_HASHES

Get hashes from transaction pool.

**Endpoints:** _/get\_transaction\_pool\_hashes_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_transaction_pool_hashes -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "tx_hashes": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...],
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `tx_hashes - string[]`: List of transaction hashes,
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_TRANSACTION\_POOL\_BACKLOG

Get all transaction pool backlog.

**Endpoints:** _get\_txpool\_backlog_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_txpool_backlog"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "backlog": [{
      "weight": 123,
      "fee": 123,
      "time_in_pool": 123
    }, ...],
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `backlog - tx_backlog_entry[]`: Array of structures tx\_backlog\_entry (in binary form):
  * `weight - uint64`
  * `fee - uint64`: Fee in Beldex measured in atomic units.
  * `time_in_pool - uint64`
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_CONNECTIONS

Retrieve information about incoming and outgoing connections to your node.

**Endpoints:** _get\_connections_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_connections"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "connections": [, ...]
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `connections - connection_info[]`: List of all connections and their info:

### COMMAND\_RPC\_GET\_BLOCK\_HEADERS\_RANGE

Similar to get\_block\_header\_by\_height above, but for a range of blocks.&#x20;

This method includes a starting block height and an ending block height as&#x20;

parameters to retrieve basic information about the range of blocks.

**Endpoints:** _get\_block\_headers\_range_, _getblockheadersrange_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"getblockheadersrange",
  "params": {
    "start_height": 123,
    "end_height": 123,
    "fill_pow_hash": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "headers": [{
      "major_version": 11,
      "minor_version": 11,
      "timestamp": 123,
      "prev_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "nonce": 2130706433,
      "orphan_status": true,
      "height": 234767,
      "depth": 123,
      "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "difficulty": 25179406071,
      "cumulative_difficulty": 25179406071,
      "reward": 123,
      "miner_reward": 123,
      "block_size": 123,
      "block_weight": 123,
      "num_txes": 123,
      "pow_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "long_term_weight": 123
    }, ...],
  "untrusted": false
}
```

**Inputs:**

* `start_height - uint64`: The starting block's height.
* `end_height - uint64`: The ending block's height.
* `fill_pow_hash - bool`: Tell the daemon if it should fill out pow\_hash field.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `headers - block_header_response[]`: Array of block\_header (a structure containing block header information. See get\_last\_block\_header).
  * `major_version - uint8`: The major version of the beldex protocol at this block height.
  * `minor_version - uint8`: The minor version of the beldex protocol at this block height.
  * `timestamp - uint64`: The unix time at which the block was recorded into the blockchain.
  * `prev_hash - string`: The hash of the block immediately preceding this block in the chain.
  * `nonce - uint32`: A cryptographic random one-time number used in mining a Beldex block.
  * `orphan_status - bool`: Usually `false`. If `true`, this block is not part of the longest chain.
  * `height - uint64`: The number of blocks preceding this block on the blockchain.
  * `depth - uint64`: The number of blocks succeeding this block on the blockchain. A larger number means an older block.
  * `hash - string`: The hash of this block.
  * `difficulty - uint64`: The strength of the Beldex network based on mining power.
  * `cumulative_difficulty - uint64`: The cumulative strength of the Beldex network based on mining power.
  * `reward - uint64`: The amount of new generated in this block and rewarded to the miner, foundation and master Nodes. Note: 1 BELDEX = 1e12 atomic units.
  * `miner_reward - uint64`: The amount of new generated in this block and rewarded to the miner. Note: 1 BELDEX = 1e12 atomic units.&#x20;
  * `block_size - uint64`: The block size in bytes.
  * `block_weight - uint64`: The block weight in bytes.
  * `num_txes - uint64`: Number of transactions in the block, not counting the coinbase tx.
  * `pow_hash - string`: The hash of the block's proof of work.
  * `long_term_weight - uint64`: Long term weight of the block.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_STOP\_DAEMON

Send a command to the daemon to safely disconnect and shut down.

**Endpoints:** _/stop\_daemon_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/stop_daemon -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_GET\_LIMIT

Get daemon bandwidth limits.

**Endpoints:** _/get\_limit_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_limit -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "limit_up": 123,
  "limit_down": 123,
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `limit_up - uint64`: Upload limit in kBytes per second.
* `limit_down - uint64`: Download limit in kBytes per second.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_SET\_LIMIT

Set daemon bandwidth limits.

**Endpoints:** _/set\_limit_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/set_limit -d '
{
  "limit_down": 8192,
  "limit_up": 8192
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "limit_up": 8192,
  "limit_down": 8192
}
```

**Inputs:**

* `limit_down - int64`: Download limit in kBytes per second (-1 reset to default, 0 don't change the current limit)
* `limit_up - int64`: Upload limit in kBytes per second (-1 reset to default, 0 don't change the current limit)

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `limit_up - int64`: Upload limit in kBytes per second.
* `limit_down - int64`: Download limit in kBytes per second.

### COMMAND\_RPC\_OUT\_PEERS

Limit number of Outgoing peers.

**Endpoints:** _/out\_peers_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/out_peers -d '
{
  "out_peers": 123
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `out_peers - uint64`: Max number of outgoing peers

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_IN\_PEERS

Limit number of Incoming peers.

**Endpoints:** _/in\_peers_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/in_peers -d '
{
  "in_peers": 123
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `in_peers - uint64`

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_START\_SAVE\_GRAPH

Obsolete. Conserved here for reference.

**Endpoints:** _/start\_save\_graph_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/start_save_graph -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_STOP\_SAVE\_GRAPH

Obsolete. Conserved here for reference.

**Endpoints:** _/stop\_save\_graph_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/stop_save_graph -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_HARD\_FORK\_INFO

Look up information regarding hard fork voting and readiness.

**Endpoints:** _hard\_fork\_info_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"hard_fork_info",
  "params": {
    "version": 11
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "version": 11,
  "enabled": true,
  "window": 2130706433,
  "votes": 2130706433,
  "threshold": 2130706433,
  "voting": 11,
  "state": 2130706433,
  "earliest_height": 123,
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

* `version - uint8`: The major block version for the fork.

**Outputs:**

* `version - uint8`: The major block version for the fork.
* `enabled - bool`: Tells if hard fork is enforced.
* `window - uint32`: Number of blocks over which current votes are cast. Default is 10080 blocks.
* `votes - uint32`: Number of votes towards hard fork.
* `threshold - uint32`: Minimum percent of votes to trigger hard fork. Default is 80.
* `voting - uint8`: Hard fork voting status.
* `state - uint32`: Current hard fork state: 0 (There is likely a hard fork), 1 (An update is needed to fork properly), or 2 (Everything looks good).
* `earliest_height - uint64`: Block height at which hard fork would be enabled if voted in.
* `status - string`: General RPC error code. "OK" means everything looks good.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GETBANS

Get list of banned IPs.

**Endpoints:** _get\_bans_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_bans"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "bans": [{
      "host": "127.0.0.1",
      "ip": 2130706433,
      "seconds": 2130706433
    }, ...]
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `bans - ban[]`: List of banned nodes:
  * `host - string`: Banned host (IP in A.B.C.D form).
  * `ip - uint32`: Banned IP address, in Int format.
  * `seconds - uint32`: Local Unix time that IP is banned until.

### COMMAND\_RPC\_SETBANS

Ban another node by IP.

**Endpoints:** _set\_bans_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"set_bans",
  "params": {
    "bans": [{
        "host": "127.0.0.1",
        "ip": 2130706433,
        "ban": true,
        "seconds": 2130706433
      }, ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `bans - ban[]`: List of nodes to ban.
  * `host - string`: Host to ban (IP in A.B.C.D form - will support I2P address in the future).
  * `ip - uint32`: IP address to ban, in Int format.
  * `ban - bool`: Set true to ban.
  * `seconds - uint32`: Number of seconds to ban node.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_FLUSH\_TRANSACTION\_POOL

Flush tx ids from transaction pool..

**Endpoints:** _flush\_txpool_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"flush_txpool",
  "params": {
    "txids": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `txids - string[]`: Optional, list of transactions IDs to flush from pool (all tx ids flushed if empty).

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_GET\_OUTPUT\_HISTOGRAM

Get a histogram of output amounts. For all amounts (possibly filtered by parameters),&#x20;

gives the number of outputs on the chain for that amount. RingCT outputs counts as 0 amount.

**Endpoints:** _get\_output\_histogram_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_output_histogram",
  "params": {
    "amounts": [123, ...],
    "min_count": 123,
    "max_count": 123,
    "unlocked": true,
    "recent_cutoff": 123
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "histogram": [{
      "amount": 123,
      "total_instances": 123,
      "unlocked_instances": 123,
      "recent_instances": 123
    }, ...],
  "untrusted": false
}
```

**Inputs:**

* `amounts - uint64[]`: list of amounts in Atomic Units.
* `min_count - uint64`: The minimum amounts you are requesting.
* `max_count - uint64`: The maximum amounts you are requesting.
* `unlocked - bool`: Look for locked only.
* `recent_cutoff - uint64`

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `histogram - entry[]`: List of histogram entries:
  * `amount - uint64`: Output amount in atomic units.
  * `total_instances - uint64`
  * `unlocked_instances - uint64`
  * `recent_instances - uint64`
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_VERSION

Get node current version.

**Endpoints:** _get\_version_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_version"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "version": 2130706433,
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `version - uint32`: Node current version.
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_COINBASE\_TX\_SUM

Get the coinbase amount and the fees amount for n last blocks starting at particular height.

**Endpoints:** _get\_coinbase\_tx\_sum_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_coinbase_tx_sum",
  "params": {
    "height": 234767,
    "count": 123
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "emission_amount": 123,
  "fee_amount": 123
}
```

**Inputs:**

* `height - uint64`: Block height from which getting the amounts.
* `count - uint64`: Number of blocks to include in the sum.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `emission_amount - uint64`: Amount of coinbase reward in atomic units.
* `fee_amount - uint64`: Amount of fees in atomic units.

### COMMAND\_RPC\_GET\_BASE\_FEE\_ESTIMATE

Gives an estimation on fees per kB.

**Endpoints:** _get\_fee\_estimate_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_fee_estimate",
  "params": {
    "grace_blocks": 123
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "fee": 123,
  "quantization_mask": 123,
  "untrusted": false
}
```

**Inputs:**

* `grace_blocks - uint64`: Optional

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `fee - uint64`: Amount of fees estimated per kB in atomic units
* `quantization_mask - uint64`
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_GET\_ALTERNATE\_CHAINS

Display alternative chains seen by the node.

**Endpoints:** _get\_alternate\_chains_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_alternate_chains"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "chains": [{
      "block_hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
      "height": 234767,
      "length": 123,
      "difficulty": 123,
      "block_hashes": ["bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70", ...],
      "main_chain_parent_block": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70"
    }, ...]
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `chains - chain_info[]`: Array of Chains.
  * `block_hash - string`: The block hash of the first diverging block of this alternative chain.
  * `height - uint64`: The block height of the first diverging block of this alternative chain.
  * `length - uint64`: The length in blocks of this alternative chain, after divergence.
  * `difficulty - uint64`: The cumulative difficulty of all blocks in the alternative chain.
  * `block_hashes - string[]`
  * `main_chain_parent_block - string`

### COMMAND\_RPC\_UPDATE

Update daemon.

**Endpoints:** _/update_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/update -d '
{
  "command": "TODO(beldex): Write example string",
  "path": "TODO(beldex): Write example string"
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "update": true,
  "version": "TODO(beldex): Write example string",
  "user_uri": "TODO(beldex): Write example string",
  "auto_uri": "TODO(beldex): Write example string",
  "hash": "bf430a3279f576ed8a814be25193e5a1ec61d3ee5729e64f47d8480ce5a2da70",
  "path": "TODO(beldex): Write example string"
}
```

**Inputs:**

* `command - string`: Command to use, either check or download.
* `path - string`: Optional, path where to download the update.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `update - bool`: States if an update is available to download (`true`) or not (`false`).
* `version - string`: Version available for download.
* `user_uri - string`
* `auto_uri - string`
* `hash - string`
* `path - string`: Path to download the update.

### COMMAND\_RPC\_RELAY\_TX

Relay a list of transaction IDs.

**Endpoints:** _relay\_tx_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"relay_tx",
  "params": {
    "txids": ["b605cab7e3b9fe1f6d322e3167cd26e1e61c764afa9d733233ef716787786123", ...]
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK"
}
```

**Inputs:**

* `txids - string[]`: Optional, list of transactions IDs to flush from pool (all tx ids flushed if empty).

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.

### COMMAND\_RPC\_SYNC\_INFO

Get synchronisation information.

**Endpoints:** _sync\_info_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"sync_info"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "height": 234767,
  "target_height": 123,
  "next_needed_pruning_seed": 2130706433,
  "peers": [{
      "id": 123,
      "host": "127.0.0.1",
      "ip": 2130706433,
      "port": 12345,
      "last_seen": 1554685440,
      "pruning_seed": 2130706433
    }, ...],
  "spans": [{
      "start_block_height": 123,
      "nblocks": 123,
      "connection_id": "083c301a3030329a487adb12ad981d2c",
      "rate": 2130706433,
      "speed": 2130706433,
      "size": 123,
      "remote_address": "127.0.0.1:22023"
    }, ...],
  "overview": "TODO(beldex): Write example string"
}
```

**Inputs:**

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good. Any other value means that something went wrong.
* `height - uint64`: Block height.
* `target_height - uint64`: Target height the node is syncing from (optional, absent if node is fully synced).
* `next_needed_pruning_seed - uint32`
* `peers - peer[]`: Array of Peer structure
  * `id - uint64`: Peer id.
  * `host - string`: IP address in string format.
  * `ip - uint32`: IP address in integer format.
  * `port - uint16`: TCP port the peer is using to connect to beldex network.
  * `last_seen - uint64`: Unix time at which the peer has been seen for the last time
  * `pruning_seed - uint32`
* `spans - span[]`: Array of Span Structure.
  * `start_block_height - uint64`: Block height of the first block in that span.
  * `nblocks - uint64`: Number of blocks in that span.
  * `connection_id - string`: Id of connection.
  * `rate - uint32`: Connection rate.
  * `speed - uint32`: Connection speed.
  * `size - uint64`: Total number of bytes in that span's blocks (including txes).
  * `remote_address - string`: Peer address the node is downloading (or has downloaded) than span from.
* `overview - string`

### COMMAND\_RPC\_GET\_OUTPUT\_DISTRIBUTION

**Endpoints:** _/get\_output\_distribution.bin_, _get\_output\_distribution_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_output_distribution",
  "params": {
    "amounts": [123, ...],
    "from_height": 123,
    "to_height": 123,
    "cumulative": true,
    "binary": true,
    "compress": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "distributions": [{
      "data": ,
      "amount": 123,
      "compressed_data": "TODO(beldex): Write example string",
      "binary": true,
      "compress": true
    }, ...],
  "untrusted": false
}
```

**Inputs:**

* `amounts - uint64[]`: Amounts to look for in atomic units.
* `from_height - uint64`: (optional, default is 0) starting height to check from.
* `to_height - uint64`: (optional, default is 0) ending height to check up to.
* `cumulative - bool`: (optional, default is false) States if the result should be cumulative (true) or not (false).
* `binary - bool`
* `compress - bool`

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `distributions - distribution[]`
  * `data - rpc::output_distribution_data`
  * `amount - uint64`
  * `compressed_data - string`
  * `binary - bool`
  * `compress - bool`
* `untrusted - bool`: States if the result is obtained using the bootstrap mode, and is therefore not trusted (`true`), or when the daemon is fully synced (`false`).

### COMMAND\_RPC\_POP\_BLOCKS

**Endpoints:** _/pop\_blocks_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/pop_blocks -d '
{
  "nblocks": 123
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "height": 234767
}
```

**Inputs:**

* `nblocks - uint64`: Number of blocks in that span.

**Outputs:**

* `status - string`: General RPC error code. "OK" means everything looks good.
* `height - uint64`

#### COMMAND\_RPC\_PRUNE\_BLOCKCHAIN <a href="#command_rpc_prune_blockchain" id="command_rpc_prune_blockchain"></a>

**Endpoints:** _prune\_blockchain_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"prune_blockchain",
  "params": {
    "check": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "pruning_seed": 2130706433,
  "status": "OK"
}
```

**Inputs:**

* `check - bool`

**Outputs:**

* `pruning_seed - uint32`
* `status - string`

### COMMAND\_RPC\_GET\_QUORUM\_STATE

Get the quorum state which is the list of public keys of the nodes&#x20;

who are voting, and the list of public keys of the nodes who are being tested.

**Endpoints:** _get\_quorum\_state_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_quorum_state",
  "params": {
    "height": 234767
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "quorum_nodes": ["4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3", ...],
  "nodes_to_test": ["4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3", ...],
  "untrusted": false
}
```

**Inputs:**

* `height - uint64`: The height to query the quorum state for.

**Outputs:**

* `status - string`: Generic RPC error code. "OK" is the success value.
* `quorum_nodes - string[]`: Array of public keys identifying master nodes which are being tested for the queried height.
* `nodes_to_test - string[]`: Array of public keys identifying master nodes which are responsible for voting on the queried height.
* `untrusted - bool`: If the result is obtained using bootstrap mode, and therefore not trusted `true`, or otherwise `false`.

### COMMAND\_RPC\_GET\_QUORUM\_STATE\_BATCHED

Get the quorum state which is the list of public keys of the nodes&#x20;

who are voting, and the list of public keys of the nodes who are being tested.

**Endpoints:** _get\_quorum\_state\_batched_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_quorum_state_batched",
  "params": {
    "height_begin": 123,
    "height_end": 123
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "quorum_entries": [{
      "height": 234767,
      "quorum_nodes": ["4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3", ...],
      "nodes_to_test": ["4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3", ...]
    }, ...],
  "untrusted": false
}
```

**Inputs:**

* `height_begin - uint64`: The starting height (inclusive) to query the quorum state for.
* `height_end - uint64`: The ending height (inclusive) to query the quorum state for.

**Outputs:**

* `status - string`: Generic RPC error code. "OK" is the success value.
* `quorum_entries - response_entry[]`: Array of quorums that was requested.
  * `height - uint64`: The height of this quorum state that was queried.
  * `quorum_nodes - string[]`: Array of public keys identifying master nodes which are being tested for the queried height.
  * `nodes_to_test - string[]`: Array of public keys identifying master nodes which are responsible for voting on the queried height.
* `untrusted - bool`: If the result is obtained using bootstrap mode, and therefore not trusted `true`, or otherwise `false`.

### COMMAND\_RPC\_GET\_MASTER\_NODE\_REGISTRATION\_CMD\_RAW

**Endpoints:** _get\_master\_node\_registration\_cmd\_raw_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_master_node_registration_cmd_raw",
  "params": {
    "args": ["TODO(beldex): Write example string", ...],
    "make_friendly": true,
    "staking_requirement": 10000000000000
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "registration_cmd": "register_master_node 18446744073709551612 bxKJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk 18446744073709551612 1555894565 f90424b23c7969bb2f0191bca45e6433a59b0b37039a5e38a2ba8cc7ea1075a3 ba24e4bfb4af0f5f9f74e35f1a5685dc9250ee83f62a9ee8964c9a689cceb40b4f125c83d0cbb434e56712d0300e5a23fd37a5b60cddbcd94e2d578209532a0d"
}
```

**Inputs:**

* `args - string[]`: (Developer) The arguments used in raw registration, i.e. portions
* `make_friendly - bool`: Provide information about how to use the command in the result.
* `staking_requirement - uint64`: The staking requirement to become a Master Node the registration command will be generated upon

**Outputs:**

* `status - string`: Generic RPC error code. "OK" is the success value.
* `registration_cmd - string`: The command to execute in the wallet CLI to register the queried daemon as a Master Node.

### COMMAND\_RPC\_GET\_MASTER\_NODE\_REGISTRATION\_CMD

**Endpoints:** _get\_master\_node\_registration\_cmd_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_master_node_registration_cmd",
  "params": {
    "operator_cut": "50%",
    "contributions": [{
        "address": "bx8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk",
        "amount": 26734261552878
      }, ...],
    "staking_requirement": 5000000000000
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "status": "OK",
  "registration_cmd": "register_master_node 18446744073709551612 bxKJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk 18446744073709551612 1555894565 f90424b23c7969bb2f0191bca45e6433a59b0b37039a5e38a2ba8cc7ea1075a3 ba24e4bfb4af0f5f9f74e35f1a5685dc9250ee83f62a9ee8964c9a689cceb40b4f125c83d0cbb434e56712d0300e5a23fd37a5b60cddbcd94e2d578209532a0d"
}
```

**Inputs:**

* `operator_cut - string`: The percentage of cut per reward the operator receives expressed as a string, i.e. "1.1%"
* `contributions - contribution_t[]`: Array of contributors for this Master Node
  * `address - string`: The wallet address for the contributor
  * `amount - uint64`: The amount that the contributor will reserve in Beldex atomic units towards the staking requirement
* `staking_requirement - uint64`: The staking requirement to become a Master Node the registration command will be generated upon

**Outputs:**

* `status - string`: Generic RPC error code. "OK" is the success value.
* `registration_cmd - string`: The command to execute in the wallet CLI to register the queried daemon as a Master Node.

### COMMAND\_RPC\_GET\_MASTER\_NODE\_KEY

Get the master node public key of the queried daemon.&#x20;

The daemon must be started in --master-node mode otherwise this RPC command will fail.

**Endpoints:** _get\_master\_node\_key_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_master_node_key"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "master_node_pubkey": "4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3",
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `master_node_pubkey - string`: The queried daemon's master node key.
* `status - string`: Generic RPC error code. "OK" is the success value.

### COMMAND\_RPC\_GET\_MASTER\_NODES

Get information on Master Nodes.

**Endpoints:** _get\_master\_nodes_, _get\_all\_master\_nodes_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_all_master_nodes",
  "params": {
    "master_node_pubkeys": ["4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3", ...],
    "include_json": true
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "master_node_states": [{
      "master_node_pubkey": "4a8c30cea9e729b06c91132295cce32d2a8e6e5bcf7b74a998e2ee1b3ed590b3",
      "registration_height": 234767,
      "requested_unlock_height": 123,
      "last_reward_block_height": 234767,
      "last_reward_transaction_index": 2130706433,
      "last_uptime_proof": 123,
      "master_node_version": [3, 0, ...],
      "contributors": [{
          "amount": 123,
          "reserved": 123,
          "address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk",
          "locked_contributions": [{
              "key_image": "8d1bd8181bf7d857bdb281e0153d84cd55a3fcaa57c3e570f4a49f935850b5e3",
              "key_image_pub_key": "b1b696dd0a0d1815e341d9fed85708703c57b5d553a3615bcf4a06a36fa4bc38",
              "amount": 123
            }, ...]
        }, ...],
      "total_contributed": 123,
      "total_reserved": 123,
      "staking_requirement": 100000000000,
      "portions_for_operator": 18446744073709551612,
      "operator_address": "L8KJf3nRQ53NTX1YLjtHryjegFRa3ZCEGLKmRxUfvkBWK19UteEacVpYqpYscSJ2q8WRuHPFdk7Q5W8pQB7Py5kvUs8vKSk"
    }, ...],
  "status": "OK",
  "as_json": "TODO(beldex): Write example string"
}
```

**Inputs:**

* `master_node_pubkeys - string[]`: Array of public keys of active Master Nodes to get information about. Pass the empty array to query all Master Nodes.
* `include_json - bool`: When set, the response's as\_json member is filled out.

**Outputs:**

* `master_node_states - entry[]`: Array of master node registration information
  * `master_node_pubkey - string`: The public key of the Master Node.
  * `registration_height - uint64`: The height at which the registration for the Master Node arrived on the blockchain.
  * `requested_unlock_height - uint64`: The height at which contributions will be released and the Master Node expires. 0 if not requested yet.
  * `last_reward_block_height - uint64`: The last height at which this Master Node received a reward.
  * `last_reward_transaction_index - uint32`: When multiple Master Nodes register on the same height, the order the transaction arrive dictate the order you receive rewards.
  * `last_uptime_proof - uint64`: The last time this Master Node's uptime proof was relayed by atleast 1 Master Node other than itself in unix epoch time.
  * `master_node_version - uint16[]`: The major, minor, patch version of the Master Node respectively.
  * `contributors - contributor[]`: Array of contributors, contributing to this Master Node.
    * `amount - uint64`: The total amount of locked Beldex in atomic units for this contributor.
    * `reserved - uint64`: The amount of Beldex in atomic units reserved by this contributor for this Master Node.
    * `address - string`: The wallet address for this contributor rewards are sent to and contributions came from.
    * `locked_contributions - contribution[]`: Array of contributions from this contributor.
      * `key_image - string`: The contribution's key image that is locked on the network.
      * `key_image_pub_key - string`: The contribution's key image, public key component
      * `amount - uint64`: The amount that is locked in this contribution.
  * `total_contributed - uint64`: The total amount of Beldex in atomic units contributed to this Master Node.
  * `total_reserved - uint64`: The total amount of Beldex in atomic units reserved in this Master Node.
  * `staking_requirement - uint64`: The staking requirement in atomic units that is required to be contributed to become a Master Node.
  * `portions_for_operator - uint64`: The operator percentage cut to take from each reward expressed in portions, see cryptonote\_config.h's STAKING\_PORTIONS.
  * `operator_address - string`: The wallet address of the operator to which the operator cut of the staking reward is sent to.
* `status - string`: Generic RPC error code. "OK" is the success value.
* `as_json - string`: If `include_json` is set in the request, this contains the json representation of the `entry` data structure

### COMMAND\_RPC\_GET\_STAKING\_REQUIREMENT

Get the required amount of Beldex to become a Master Node at the queried height.&#x20;

For stagenet and testnet values, ensure the daemon is started with the&#x20;

`--stagenet` or `--testnet` flags respectively.

**Endpoints:** _get\_staking\_requirement_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '
{
  "jsonrpc":"2.0", "id":"0", "method":"get_staking_requirement",
  "params": {
    "height": 234767
  }
}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "staking_requirement": 100000000000,
  "status": "OK"
}
```

**Inputs:**

* `height - uint64`: The height to query the staking requirement for.

**Outputs:**

* `staking_requirement - uint64`: The staking requirement in Beldex, in atomic units.
* `status - string`: Generic RPC error code. "OK" is the success value.

### COMMAND\_RPC\_GET\_MASTER\_NODE\_BLACKLISTED\_KEY\_IMAGES

Get information on blacklisted Master Node key images.

**Endpoints:** _get\_master\_node\_blacklisted\_key\_images_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/json_rpc -d '{ "jsonrpc":"2.0", "id":"0", "method":"get_master_node_blacklisted_key_images"}' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "blacklist": [{
      "key_image": "8d1bd8181bf7d857bdb281e0153d84cd55a3fcaa57c3e570f4a49f935850b5e3",
      "unlock_height": 123
    }, ...],
  "status": "OK"
}
```

**Inputs:**

**Outputs:**

* `blacklist - entry[]`: Array of blacklisted key images, i.e. unspendable transactions
  * `key_image - string`: The key image of the transaction that is blacklisted on the network.
  * `unlock_height - uint64`: The height at which the key image is removed from the blacklist and becomes spendable.
* `status - string`: Generic RPC error code. "OK" is the success value.

### COMMAND\_RPC\_GET\_OUTPUT\_BLACKLIST

Get information on output blacklist.

**Endpoints:** _/get\_output\_blacklist.bin_

**Example Request:**

```
curl -X POST http://127.0.0.1:22023/get_output_blacklist.bin -d '{ }' -H 'Content-Type: application/json'
```

**Example Response:**

```
{
  "blacklist": [123, ...],
  "status": "OK",
  "untrusted": false
}
```

**Inputs:**

**Outputs:**

* `blacklist - uint64[]`: (Developer): Array of indexes from the global output list, corresponding to blacklisted key images.
* `status - string`: Generic RPC error code. "OK" is the success value.
* `untrusted - bool`: If the result is obtained using bootstrap mode, and therefore not trusted `true`, or otherwise `false`.

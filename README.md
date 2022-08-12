# IPFS practice

## Quick start
```shell
$ cd docker
$ make run
```

and you can connect link: [http://localhost:5001/webui](http://localhost:5001/webui)  

### Monitor

```shell
$ make monitor
```

### Upload file

```shell
# go to stage floder
$ cd stage
$ echo zonda test > test.txt
```

```shell
# in docker floder, attach in container
$ make attach
/ # ipfs add -r /export/test.txt
added QmZnmqt5P3WVwL1odjpWsucFf3QUt7in3rxdPpHUhhg3um test.txt
 11 B / 11 B [===============================================================]
 ```

### Get file

```shell
# in docker floder, attach in container
$ make attach
/ # ipfs cat /ipfs/QmZnmqt5P3WVwL1odjpWsucFf3QUt7in3rxdPpHUhhg3um
zonda test
```

### Get node id

```shell
# in docker floder, attach in container
$ make attach
/ # ipfs id
{
        "ID": "12D3......2Bje",
        "PublicKey": "CAE........F1W5",
        "Addresses": [
                "/ip4/127.0.0.1/tcp/4001/p2p/12D3......2Bje",
                "/ip4/127.0.0.1/udp/4001/quic/p2p/12D3......2Bje",
                "/ip4/172.17.0.3/tcp/4001/p2p/12D3......2Bje",
                "/ip4/172.17.0.3/udp/4001/quic/p2p/12D3......2Bje"
        ],
        "AgentVersion": "kubo/0.14.0/e0fabd6/docker",
        "ProtocolVersion": "ipfs/0.1.0",
        "Protocols": [
                "/ipfs/bitswap",
                "/ipfs/bitswap/1.0.0",
                "/ipfs/bitswap/1.1.0",
                "/ipfs/bitswap/1.2.0",
                "/ipfs/id/1.0.0",
                "/ipfs/id/push/1.0.0",
                "/ipfs/lan/kad/1.0.0",
                "/ipfs/ping/1.0.0",
                "/libp2p/autonat/1.0.0",
                "/libp2p/circuit/relay/0.1.0",
                "/libp2p/circuit/relay/0.2.0/stop",
                "/libp2p/dcutr",
                "/p2p/id/delta/1.0.0",
                "/x/"
        ]
}
```

### Found peers

```shell
# in docker floder, attach in container
$ make attach
/ # ipfs swarm peers
/ip4/1.36.235.249/tcp/36613/p2p/QmXfL....a5xwTpsz
/ip4/103.1.33.196/udp/4001/quic/p2p/12D3....2dTA
/ip4/103.82.230.154/udp/4001/quic/p2p/12D3....w9HC
/ip4/103.82.230.192/udp/4001/quic/p2p/12D3....asF4
/ip4/104.131.131.82/udp/4001/quic/p2p/Qma....uvuJ
/ip4/104.156.231.222/udp/4001/quic/p2p/12D3....u99
/ip4/104.206.255.242/udp/4001/quic/p2p/12D3....A1gmd
/ip4/104.248.243.115/tcp/4001/p2p/12D3....QToy
/ip4/107.170.200.4/udp/4001/quic/p2p/12D3....aDG
/ip4/107.173.251.88/udp/4001/quic/p2p/12D3....GGk
```

### Clean

```shell
make clean
```

## Reference

[Run IPFS inside Docker](https://docs.ipfs.tech/how-to/run-ipfs-inside-docker/#set-up)  

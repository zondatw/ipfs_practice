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

### Clean

```shell
make clean
```

## Reference

[Run IPFS inside Docker](https://docs.ipfs.tech/how-to/run-ipfs-inside-docker/#set-up)  
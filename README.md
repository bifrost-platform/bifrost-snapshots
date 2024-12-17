# bifrost-snapshots

## Archive

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [20256743](https://explorer.mainnet.bifrostnetwork.com/block/20256743/) (Dec 17 2024 11:00:24 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/archive/bifrost-mainnet-20241217.tar.lz4)
| Size | 615G <-> 720G |


### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [22894264](https://explorer.testnet.bifrostnetwork.com/block/22894264/) (Dec 17 2024 11:00:27 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/archive/bifrost-testnet-20241217.tar.lz4)
| Size | 218G <-> 235G |

## Full

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [20256743](https://explorer.mainnet.bifrostnetwork.com/block/20256743/) (Dec 17 2024 11:00:24 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/full/bifrost-mainnet-20241217.tar.lz4)
| Size | 42G <-> 45G |

### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [22894264](https://explorer.testnet.bifrostnetwork.com/block/22894264/) (Dec 17 2024 11:00:27 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/full/bifrost-testnet-20241217.tar.lz4)
| Size | 15G <-> 15G |

## How to download

### Download and export snapshot simultaneously
This method allows you to download and export the snapshot simultaneously. If there is no reason to save the snapshot, you can save time and disk space using this method. Change <YOUR-BASE-PATH-DIRECTORY> to the chain data directory before executing (`/var/lib/bifrost-data` according to the operation manual). The expected download duration will take up to an **hour**.

For instances that has not installed `lz4`, it should be manually installed by the following command.

```bash
apt install lz4
```

```bash
cd <YOUR-BASE-PATH-DIRECTORY>
wget -q -O - $LINK | tar -I lz4 -xvf -
```

Return to the process in the operation manual once complete.

### Multithreaded download

```bash
aria2c -s14 -x14 -k100M $LINK -o $PATH
tar -I lz4 -xvf $FILE -C <YOUR-BASE-PATH-DIRECTORY>
```

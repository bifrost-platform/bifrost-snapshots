# bifrost-snapshots

## Archive

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [21954607](https://explorer.mainnet.bifrostnetwork.com/block/21954607/) (Feb 14 2025 10:44:18 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/archive/bifrost-mainnet-20250214.tar.lz4)
| Size | 717G <-> 842G |


### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [24592668](https://explorer.testnet.bifrostnetwork.com/block/24592668/) (Feb 14 2025 10:44:42 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/archive/bifrost-testnet-20250214.tar.lz4)
| Size | 244G <-> 265G |

## Full

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [21954607](https://explorer.mainnet.bifrostnetwork.com/block/21954607/) (Feb 14 2025 10:44:18 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/full/bifrost-mainnet-20250214.tar.lz4)
| Size | 49G <-> 52G |

### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [24592668](https://explorer.testnet.bifrostnetwork.com/block/24592668/) (Feb 14 2025 10:44:42 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/full/bifrost-testnet-20250214.tar.lz4)
| Size | 16G <-> 17G |

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

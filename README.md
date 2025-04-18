# bifrost-snapshots

## Archive

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [23656199](https://explorer.mainnet.bifrostnetwork.com/block/23656199/) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-mainnet-20250414.tar.zst) |
| Size | 516G <-> 945G |


### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [26294494](https://explorer.testnet.bifrostnetwork.com/block/26294494/) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-testnet-20250414.tar.zst) |
| Size | 228G <-> 296G |

## Full

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [23656199](https://explorer.mainnet.bifrostnetwork.com/block/23656199/) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-mainnet-20250414.tar.zst) |
| Size | 48G <-> 57G |

### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [26294494](https://explorer.testnet.bifrostnetwork.com/block/26294494/) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-testnet-20250414.tar.zst) |
| Size | 16G <-> 19G |

## How to download

### Download and export snapshot simultaneously
This method allows you to download and export the snapshot simultaneously. If there is no reason to save the snapshot, you can save time and disk space using this method. Change <YOUR-BASE-PATH-DIRECTORY> to the chain data directory before executing (`/var/lib/bifrost-data` according to the operation manual). The expected download duration will take up to an **hour**.

For instances that has not installed `zstd`, it should be manually installed by the following command.

```bash
sudo apt install -y aria2c zstd
```

```bash
cd <YOUR-BASE-PATH-DIRECTORY>
wget -q -O - $LINK | zstd -cd | tar xf -
```

Return to the process in the operation manual once complete.

### Multithreaded download

```bash
aria2c -s14 -x14 -k1024M $LINK -o $PATH
zstd -cd $FILE | tar xf -
```

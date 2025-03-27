# bifrost-snapshots

## Archive

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [22737851](https://explorer.mainnet.bifrostnetwork.com/block/22737851/) (Mar 13 2025 16:07:42 PM (+09:00 UTC)) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-mainnet-20250313.tar.lz4)
| Size | 820G <-> 898G |


### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [25376627](https://explorer.testnet.bifrostnetwork.com/block/25376627/) (Mar 13 2025 16:07:30 PM (+09:00 UTC)) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-testnet-20250313.tar.lz4)
| Size | 274G <-> 279G |

## Full

### Mainnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [22737851](https://explorer.mainnet.bifrostnetwork.com/block/22737851/) (Mar 13 2025 16:07:42 PM (+09:00 UTC)) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-mainnet-20250313.tar.lz4)
| Size | 55G <-> 55G |

### Testnet
| Field | Value |
| --- | --- |
| Version | [v2.0.1](https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1) |
| Block | [25376627](https://explorer.testnet.bifrostnetwork.com/block/25376627/) (Mar 13 2025 16:07:30 PM (+09:00 UTC)) |
| Link | [Download](https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-testnet-20250313.tar.lz4)
| Size | 17G <-> 18G |

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

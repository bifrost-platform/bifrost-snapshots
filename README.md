# bifrost-snapshots

## Mainnet
| Field | Value |
| --- | --- |
| Version | [v1.3.0](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.3.0) |
| Block | [16801880](https://explorer.mainnet.bifrostnetwork.com/block/16801880/) (Aug 19 2024 11:06:06 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/bifrost-mainnet-20240819.tar.lz4)
| Size | 418G <-> 489G |


## Testnet
| Field | Value |
| --- | --- |
| Version | [v1.3.0](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.3.0) |
| Block | [19460665](https://explorer.testnet.bifrostnetwork.com/block/19460665/) (Aug 19 2024 11:06:18 AM (+09:00 UTC)) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/bifrost-testnet-20240819.tar.lz4)
| Size | 166G <-> 178G |


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

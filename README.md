# bifrost-snapshots

## Mainnet
| Field | Value |
| --- | --- |
| Version | [v1.3.0](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.3.0) |
| Block | [13184897](https://explorer.mainnet.bifrostnetwork.com/block/13184897/) (April-15-2024 07:23:15 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/bifrost-mainnet-20240415.tar.lz4)
| Size | 297G <-> 360G |


## Testnet
| Field | Value |
| --- | --- |
| Version | [v1.3.0](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.3.0) |
| Block | [15842344](https://explorer.testnet.bifrostnetwork.com/block/15842344/) (April-15-2024 07:23:00 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/bifrost-testnet-20240415.tar.lz4)
| Size | 146G <-> 162G |


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

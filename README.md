# bifrost-snapshots

## Mainnet
| Field | Value |
| --- | --- |
| Version | [v1.2.4](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.2.4) |
| Block | [7653600](https://explorer.mainnet.bifrostnetwork.com/block/7653600/) (October-6-2023 17:28:27 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/bifrost-mainnet-20231006.tar.lz4)
| Size | 87G <-> 92G |


## Testnet
| Field | Value |
| --- | --- |
| Version | [v1.2.4](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.2.4) |
| Block | [9672820](https://explorer.testnet.bifrostnetwork.com/block/9672820/) (September-14-2023 01:44:15 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/bifrost-testnet-20230914.tar.lz4)
| Size | 94G <-> 100G |


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

# bifrost-snapshots

## Mainnet
| Field | Value |
| --- | --- |
| Version | [v1.2.3](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.2.3) |
| Block | [5234881](https://explorer.mainnet.bifrostnetwork.com/block/5234881/) (July-14-2023 12:24:51 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/mainnet/bifrost-mainnet-20230714.tar.lz4)
| Size | 65G <-> 76G |


## Testnet
| Field | Value |
| --- | --- |
| Version | [v1.2.3](https://github.com/bifrost-platform/bifrost-node/releases/tag/v1.2.3) |
| Block | [7888435](https://explorer.mainnet.bifrostnetwork.com/block/7888435/) (July-14-2023 12:35:33 PM +9 UTC) |
| Link | [Download](https://bifrost-chaindata.s3.ap-northeast-2.amazonaws.com/testnet/bifrost-testnet-20230714.tar.lz4)
| Size | 81G <-> 86G |


## How to download

### Download and export snapshot simultaneously
This method allows you to download and export the snapshot simultaneously. If there is no reason to save the snapshot, you can save time and disk space using this method. Change <YOUR-BASE-PATH-DIRECTORY> to the chain data directory before executing (```/var/lib/bifrost-data``` according to the operation manual). The expected download duration will take up to an **hour**.

For instances that has not installed ```lz4```, it should be manually installed by the following command.
```
apt install lz4
```

```
cd <YOUR-BASE-PATH-DIRECTORY>
wget -q -O - $LINK | tar -I lz4 -xvf -
```

Return to the process in the operation manual once complete.

### Multithreaded download

```
aria2c -s14 -x14 -k100M $LINK -o $PATH
tar -I lz4 -xvf $FILE -C <YOUR-BASE-PATH-DIRECTORY>
```

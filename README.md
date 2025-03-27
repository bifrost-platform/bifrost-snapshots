# bifrost-snapshots

| Network   | Mode    | Size           | Download      |
|-----------|---------|----------------|---------------|
| Mainnet   | Archive | 626G <-> 1.2T  | [Download][1] |
| Mainnet   | Full    | 68G <–> 98G    | [Download][2] |
| Testnet   | Archive | 269G <–> 392G  | [Download][3] |
| Testnet   | Full    | 25G <-> 32G    | [Download][4] |

- Version: [v2.0.1][version]

[1]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-mainnet-250714.tar.zst
[2]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-mainnet-250714.tar.zst
[3]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-testnet-250714.tar.zst
[4]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-testnet-250714.tar.zst
[version]: https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.0.1

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
aria2c -s14 -x14 -k1024M $LINK -o $OUTFILE
zstd -cd $OUTFILE | tar xf -
# $LINK: Download URL, $OUTFILE: output filename (e.g., bifrost-mainnet-snapshot.tar.zst)
```

# bifrost-snapshots

Bifrost node chain data snapshots for fast node synchronization.

## Available Snapshots

| Network | Mode    | Compressed | Extracted | Download |
|---------|---------|------------|-----------|----------|
| Mainnet | Archive | 833 GB     | 1.7 TB    | [mainnet.archive.33408325.tar.zst][1] |
| Mainnet | Full    | 80 GB      | 94 GB     | [mainnet.full.33407302.tar.zst][2] |
| Testnet | Archive | 329 GB     | 472 GB    | [testnet.archive.36069834.tar.zst][3] |
| Testnet | Full    | 23 GB      | 28 GB     | [testnet.full.36069539.tar.zst][4] |

> **Node Version:** [v2.1.0][version]

[1]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-mainnet-260320.tar.zst
[2]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-mainnet-260320.tar.zst
[3]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-testnet-260320.tar.zst
[4]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-testnet-260320.tar.zst
[version]: https://github.com/bifrost-platform/bifrost-node/releases/tag/v2.1.0

## Prerequisites

```bash
sudo apt install -y aria2 zstd
```

## Usage

### Option 1: Stream directly (recommended)

Downloads and extracts simultaneously, saving disk space.

```bash
LINK="<DOWNLOAD_URL>"  # Copy from table above
cd /var/lib/bifrost-data
wget -q -O - $LINK | zstd -cd | tar xf -
```

### Option 2: Multithreaded download

Faster download with parallel connections. Requires extra disk space for the compressed file.

```bash
LINK="<DOWNLOAD_URL>"  # Copy from table above
OUTFILE="bifrost-snapshot.tar.zst"

aria2c -s14 -x14 -k1024M $LINK -o $OUTFILE
zstd -cd $OUTFILE | tar xf -
rm $OUTFILE  # Optional: remove compressed file after extraction
```

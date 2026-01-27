# bifrost-snapshots

Bifrost node chain data snapshots for fast node synchronization.

## Available Snapshots

| Network | Mode    | Compressed | Extracted | Download |
|---------|---------|------------|-----------|----------|
| Mainnet | Archive | 771 GB     | 1.6 TB    | [mainnet.archive.31766253.tar.zst][1] |
| Mainnet | Full    | 74 GB      | 91 GB     | [mainnet.full.31765307.tar.zst][2] |
| Testnet | Archive | 308 GB     | 443 GB    | [testnet.archive.34399995.tar.zst][3] |
| Testnet | Full    | 22 GB      | 32 GB     | [testnet.full.34399717.tar.zst][4] |

> **Node Version:** [v2.1.0][version]

[1]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-mainnet-260122.tar.zst
[2]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-mainnet-260122.tar.zst
[3]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-testnet-260121.tar.zst
[4]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-testnet-260121.tar.zst
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

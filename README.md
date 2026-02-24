# bifrost-snapshots

Bifrost node chain data snapshots for fast node synchronization.

## Available Snapshots

| Network | Mode    | Compressed | Extracted | Download |
|---------|---------|------------|-----------|----------|
| Mainnet | Archive | 802 GB     | 1.6 TB    | [mainnet.archive.32597485.tar.zst][1] |
| Mainnet | Full    | 80 GB      | 93 GB     | [mainnet.full.32596432.tar.zst][2] |
| Testnet | Archive | 318 GB     | 457 GB    | [testnet.archive.35241142.tar.zst][3] |
| Testnet | Full    | 22 GB      | 28 GB     | [testnet.full.35240856.tar.zst][4] |

> **Node Version:** [v2.1.0][version]

[1]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-mainnet-260220.tar.zst
[2]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-mainnet-260220.tar.zst
[3]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/archive/bifrost-archivenode-testnet-260219.tar.zst
[4]: https://pub-af47211e285e4c41ab47c161353e5c13.r2.dev/full/bifrost-fullnode-testnet-260219.tar.zst
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

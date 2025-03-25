---
title: Bismuth Node Database Snapshots (June 2024)
date: 2024-06-20
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: /favicon-32x32.png
tags:
  - snapshot
  - database
---
![](/images/2024-06-20/database-snapshot.webp)
Using the provided snapshots significantly reduces syncing time for both the main-net and hypernode databases.
<!--more-->

Bismuth provides two networks:

* Main-Net: Proof-of-Work based.

* Hypernode: Proof-of-Stake based (side-chain).

Each network maintains its own database. If you encounter database corruption or need to set up a new node, you can either synchronize from the genesis block or speed up the process using the June 2024 snapshot files.  

---

### Main-Net Snapshot
1. Download the snapshot
```
wget https://bismuth.world/snapshot/ledger-3822000.tar.gz
```

2. Remove old data
* Clear any existing database files from your `Bismuth/static` folder.

3. Extract the new snapshot
```
tar -xvzf ledger-3822000.tar.gz
```

4. Start the node
```
python3 node.py
```

--- 

### Hypernode Snapshot
1. Remove corrupted data
* Navigate to `~/hypernode/main/data` and remove or rename all old files.

2. Download the snapshot
```
wget https://bismuth.world/snapshot/hypernode_2024_06_17.tar.gz
```

3. Extract the new snapshot
```
tar -xvzf hypernode_2024_06_16.tar.gz
```

4. Run the check
This process will
* create a new poswallet.json
* display some info
* check the ledger.db is readable
```
python3 hn_check.py
```
5. Launch the hypernode
* Use your existing Hypernode startup command, which will now load from the fresh snapshot.
```
python3 hn_instance.py -v
```




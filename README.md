# CEPH_Backup-Script-RBD

This script was made based on the script available in this URL: https://www.rapide.nl/blog/item/ceph_-_rbd_replication.html

Bash script to synchronize CEPH pools between servers.

In our case we are using CEPH RBD volumes for Virtual Machines.

The main purpose of this script is to take snapshots from a production CEPH pool and send them over SSH to your destination backup server.

This script checks if there is a copy of your yesterday's snapshot on your destination pool, and starts doing incremental backup on snapshots everyday. If the snapshot or initial volume is not present, the script will create it for you.

IT will also keep the two last days of snapshots on your Source and Destination pool.


REPLACE:


[DEST-POOLNAME] = Name of you destination Pool
[SOURCE-POOLNAME] = Name of you destination Pool
[SOURCE-HOST] = user @ ip address / hostname of your source server
[DEST-HOST] = user @ ip address / hostname of your destination server


For example:

#!/bin/bash

SOURCEPOOL="vms"
DESTPOOL="vms"
DESTHOST="root@backup.example.com"




Credits: https://www.rapide.nl/blog/item/ceph_-_rbd_replication.html







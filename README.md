#### Vagrant files to reproduce wal-e seg fault

When running newer builds of python that patch `CVE-2013-1752`, `CVE-2013-1753`, `CVE-2014-4616`, `CVE-2014-4650`, and `CVE-2014-7185`, I get the following

```
wal_e.main   INFO     MSG: starting WAL-E
        DETAIL: The subcommand is "backup-list".
        STRUCTURED: time=2015-12-06T19:48:22.198343-00 pid=28818
name	last_modified	expanded_size_bytes	wal_segment_backup_start	wal_segment_offset_backup_start	wal_segment_backup_sto	wal_segment_offset_backup_stop
Segmentation fault
```

##### CentOS 7 [CESA-2015:2101](https://lists.centos.org/pipermail/centos-cr-announce/2015-November/002560.html)

1. Run `vagrant up` from the `centos7` directory
1. Set your aws access keys as environment variables
1. Run `wal-e --s3-prefix=<s3_prefix> backup-list`


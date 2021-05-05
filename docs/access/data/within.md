# Data Transfers Within UMN

## Tier 1 (MSI-hot storage) <--> Tier 2 (S3)

Tier 2 storage is maintained for all PIs at 120 TB per PI. We have a total of 480 TB free between MSI leadership. Access to the S3 drive is secure and maintained per PI via policies, which they can implement using [this guide](https://www.msi.umn.edu/support/faq/how-do-i-use-s3-buckets-share-data-tier-2-storage-other-users). Tier 2 stored data can be transferred to the MSI via the s3cmd command - [details here](https://www.msi.umn.edu/support/faq/how-do-i-use-second-tier-storage-command-line).

## Tier 1 (MSI-hot storage) <--> Tier 1 (MSI-hot storage)

Tier 1 storage is available on MSI for all the PIs, with up to 80 TB available. Standard linux commands (e.g. mv/cp/rsync) can be used to move files between different PIs. Please refer to the data and location documentation below for more information on what is stored where.

## Tier 1 (MSI-hot storage) <--> Local storage

Your UMN computer has a local storage space that you may want to use for working on specific files. You can transfer files between local and MSI Tier 1 systems via [winSCP](https://www.msi.umn.edu/support/faq/how-do-i-use-winscp-transfer-data) or [FileZilla](https://www.msi.umn.edu/support/faq/how-do-i-use-filezilla-transfer-data).

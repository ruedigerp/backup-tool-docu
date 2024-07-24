# BackupItAll

![BackupItAll](images/IMG_9569.webp)

BackupItAll creates a current copy of the source directory when executed. Depending on the configuration (Daily, Weekly), the target directory is named by date or weekday (Monday 1, Tuesday 2, ... Sunday 7). The target directories and files are created using hard links. Even if the source directory is, for example, 2 GB and the changes from the previous day are only a few MB, the directory will show 2 GB when checking disk usage. However, it contains only the MB of data that has changed. If the backup from the previous day or from one/more days is deleted, these data are still included in the current backup. This approach saves storage space while ensuring all data is included.

BackupItAll can back up data locally on the hard drive or remotely, e.g., via SSH from another computer. The configuration is done through individual configuration files and symbolic links for each backup job.

Daily Backup creates a folder named YYYY-MM-DD for each day. Weekly Backup always creates a folder for each weekday (1-7). In Weekly Backup, the current backup is copied on Monday (1), so a backup is stored for the entire week. The same will happen with monthly backups in the future, ensuring that backups are available for a longer period. Daily backups are always overwritten.

In both variants, the daily backup can be run multiple times. If the backup runs hourly, all changes from the previous day to the current time are included. A feature in an upcoming version will ensure that files are not deleted in intermediate runs; only during the final run of the day will deleted files be removed from the backup. This way, deleted data can still be restored from the backup during the day.

Currently, backups are not encrypted. This function will also be available shortly.

For backing up data from a remote computer, an SSH key is required, and SSH login must work.

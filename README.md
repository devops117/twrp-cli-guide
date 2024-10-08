# TWRP cli guide

## Citation:
backup/restore flags
> https://twrp.me/faq/openrecoveryscript.html

O (backup compression) flag
> https://pocketables.com/2014/10/using-twrps-new-adb-interface.html

## Important note regarding passing path arguments to twrp commands
- while passing a path to twrp, make sure to not pass a trailing forward slash (/).
- twrp wipe /cache/ will not work
- twrp wipe /cache will work

## Backup and Restore Guide
Use a combination of these characters to Backup or Restore the listed partitions

```
S: system,
D: data,
C: cache,
R: recovery,
B: boot,
A: and-sec,
E: sd-ext,
```

Extras

```
O: enable compression (only for backup)
M: skip md5 creation.
```

Backup system and boot partitions with compression enabled (O flag)

```
twrp backup SBO <path-to-backup.zip>
```

Restore all partitions in backup

```
twrp restore <path-to-backup.zip>
```

Restore "boot and system" partition from backup

```
twrp restore <path-to-backup.zip> SB
```

## Example commands
Installing a package

```
twrp install /sdcard/<package>.zip
```

Wipe (on some devices wipe is more recommended than format)

```
twrp wipe /sdcard
```

Sideloading a package

```
twrp sideload
```

## twrp --help
```
TWRP openrecoveryscript command line tool, TWRP version 3.7.0_9-0

Allows command line usage of TWRP via openrecoveryscript commands.
Some common commands include:
  install /path/to/update.zip
  backup <SDCRBAEM> [backupname] # CORRECTION: O flag: compression
  restore <SDCRBAEM> [backupname] # CORRECTION: restore [backupname] <SDCRBAEM>
  wipe <partition name>
  format data
  sideload
  set <variable> [value]
  decrypt <password> [USER ID]
  remountrw
  fixperms
  mount <path>
  unmount <path>
  print <value>
  mkdir <directory>
  reboot [recovery|poweroff|bootloader|download|edl]

See more documentation at https://twrp.me/faq/openrecoveryscript.html
```

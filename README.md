# ![Backuppc logo small] BackupPC for FreeBSD

*Install and configure BackupPC 4.*

[Backuppc logo small]:lib/images/backuppc-logo-small.png

**Only works with FreeBSD.**

![FreeBSD logo medium]

[FreeBSD logo medium]:lib/images/freebsd-logo-medium.png

## Requirements

Run:

- `ansible` >=  `2.9`
- `python-passlib` (on the remote host)

## Supported OS

- `FreeBSD` == `11.2`, `12`

The FreeBSD version of BackupPC Web UI use Apache24 + SCGI mod.

Access is restricted by htpasswd, but everyone is admin.

## Quick start

```yaml
roles:
  - ansible-backuppc

vars:
  backuppc__apache24_listen: 3000 # Optionnal.
  backuppc__htpasswd:
    - name: backuppc
      password: backuppc # Should be in a vault.
```

The `backuppc__htpasswd` is required.

## Variables

|       **Variable**        | **Mandatory** | **Type** |       **Example**        |
|--------------------------:|:-------------:|:--------:|:-------------------------|
| backuppc__apache24_listen |      yes      |  number  | 3000                     |
| backuppc__htpasswd        |      yes      |  dict    | See usage example above. |
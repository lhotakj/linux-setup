# linux-setup

<pre>
  _     ___ _   _ _   ___  __           _               
| |   |_ _| \ | | | | \ \/ /  ___  ___| |_ _   _ _ __  
| |    | ||  \| | | | |\  /  / __|/ _ \ __| | | | '_ \
| |___ | || |\  | |_| |/  \  \__ \  __/ |_| |_| | |_) |
|_____|___|_| \_|\___//_/\_\ |___/\___|\__|\__,_| .__/
                                                |_|
</pre>

Collection of idempotent bash scripts for setting up and maintaining Ubuntu systems.
All scripts support a `--dry-run` flag (aliases: `--dryrun`, `-d`) to preview actions without making changes.

---

## Scripts

### `bootstrap`
Initial system setup — installs common packages, configures SSH and adds the current user to the sudo group.

```bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/bootstrap | bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/bootstrap | bash -s -- --dry-run
```

---

### `install-docker`
Installs Docker CE and the latest Docker Compose (version fetched dynamically from GitHub).
Idempotent — skips steps already completed.

```bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/install-docker | bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/install-docker | bash -s -- --dry-run
```

---

### `system-clean`
Comprehensive system cleanup — apt, snap, journals, logs, caches, thumbnails, Docker leftovers, orphaned packages and Flatpak.

```bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/system-clean | bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/system-clean | bash -s -- --dry-run
```

---

### `clean-kernels`
Removes old unused kernels while keeping the currently active one, then runs `apt autoremove`.

```bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/clean-kernels | bash
wget -qO- https://raw.githubusercontent.com/lhotakj/linux-setup/main/clean-kernels | bash -s -- --dry-run
```

---

## Dry run

All scripts accept `--dry-run` (or `--dryrun` / `-d`) to print commands without executing them:

```bash
./bootstrap --dry-run
./install-docker --dry-run
./system-clean --dry-run
./clean-kernels --dry-run
```

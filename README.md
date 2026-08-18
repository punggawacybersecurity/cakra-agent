# Cakra Agent — Installation Guide

## Requirements

- Linux, `x86_64` architecture
- Root privileges (run with `sudo` or as `root`)
- A supported package manager: `apt-get`, `yum`, or `zypper`
- Outbound internet access (the installer downloads packages during setup)
- `wget` or `curl` available on the system

## Getting the installer

Clone this repository or copy `cakra-agent.sh` to the target host, then make it executable:

```bash
chmod +x cakra-agent.sh
```

## Install

```bash
sudo ./cakra-agent.sh -i \
  --manager <manager-host> \
  --manager-port <manager-port> \
  --registration-port <registration-port> \
  --key <customer-key> \
  --customer <customer-id>
```

| Flag | Description |
|---|---|
| `--manager` | Manager address (IP or FQDN) |
| `--manager-port` | Manager port |
| `--registration-port` | Registration port |
| `--key` | Customer registration key |
| `--customer` | Customer identifier |

## Patch / Update

```bash
sudo ./cakra-agent.sh -p --key <customer-key>
```

## Uninstall

```bash
sudo ./cakra-agent.sh -u
```

## Help

```bash
./cakra-agent.sh -h
```

## Logs

Installation, patch, and uninstall activity is logged under `/var/log/`:

- `cakra-edr-install.log`
- `cakra-edr-patch.log`
- `cakra-edr-uninstall.log`

Check these logs first if the installer reports a failure.

# SUBFINDER

<img width="928" height="289" alt="image" src="https://github.com/user-attachments/assets/1559e923-3754-45b4-8d2c-47130b06a347" />

If you just want `subfinder` working fast, use the Debian package that Kali suggested:

```bash
sudo apt update
sudo apt install subfinder
```

Then verify:

```bash
subfinder -h
```

This is the easiest and safest option — apt will handle dependencies for you.

---

## If you prefer to install from the official upstream (via Go) — recommended for latest version

1. Make sure you have the normal Go toolchain (`golang-go`) installed (it already is on your system):

```bash
sudo apt update
sudo apt install golang-go
```

2. Install `subfinder` with `go install` (puts binary under $GOPATH/bin or $HOME/go/bin):

```bash
# install latest (Go 1.18+):
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest

# ensure Go bin is on your PATH (add to ~/.profile or ~/.bashrc if needed)
export PATH=$PATH:$(go env GOPATH)/bin
```

3. Verify:

```bash
subfinder -h
```

This gives you the newest release directly from the project and keeps system packages intact.

---

## Why apt showed `gccgo-go` removing `golang-go`

* `gccgo-go` is an alternative Go compiler/runtime. The package manager marks them as conflicting — installing `gccgo-go` will remove `golang-go`.
* **You do not need `gccgo-go`** to run `subfinder`. Keep `golang-go` (the standard toolchain) or simply install `subfinder` via apt.

---

## About the “automatically installed and are no longer required” list

Apt listed a bunch of packages that were installed as dependencies earlier but aren’t required anymore. If you want to clean them up safely:

```bash
sudo apt autoremove
```

(Review the list before confirming.)

---

## Summary — which to choose

* **Fast & safe:** `sudo apt install subfinder` ✔️
* **Latest upstream version / control:** install via `go install` ✔️
* **Avoid installing `gccgo-go`** unless you specifically need that compiler (it will remove `golang-go`).

---

Want me to give the exact `go install` + PATH lines to add to your `~/.bashrc` (so `subfinder` works every new shell)?

If you do want gccgo-go

Run it (you’ll be prompted to confirm the package changes):
```bash
sudo apt update
sudo apt install gccgo-go
```

Or to auto-accept (be careful):
```bash
sudo apt install -y gccgo-go
```


## Quick useful commands

Save found subdomains to a file:

```bash
subfinder -d rakuten.com -o rakuten_subs.txt
```

Show findings in real time (verbose) and save:

```bash
subfinder -v -d rakuten.com -o rakuten_subs.txt
```

Increase concurrency (faster enumeration):

```bash
subfinder -d rakuten.com -t 100 -o rakuten_subs.txt
```

Run quietly (only results, no info logs):

```bash
subfinder -silent -d rakuten.com -o rakuten_subs.txt
```

Chain with `httpx` to probe live hosts on common web ports (install httpx first if you don’t have it):

```bash
# produce file of live hosts on ports 80 & 443
subfinder -d rakuten.com -o - | httpx -ports 80,443 -silent -o rakuten_live.txt
```

Explanation: `-o -` makes `subfinder` print to stdout, which we pipe into `httpx`.

---

## Update `subfinder` (you saw a message that v2.6.0 is outdated)

Install the latest upstream release with Go (recommended):

```bash
# ensure you have golang-go installed
sudo apt update
sudo apt install golang-go

# install latest subfinder (Go 1.18+)
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest

# make sure Go bin is in PATH for future shells
echo 'export PATH=$PATH:$(go env GOPATH)/bin' >> ~/.bashrc
source ~/.bashrc

# verify
subfinder -version
```

Or update the Debian package (may be older than upstream):

```bash
sudo apt update
sudo apt install subfinder
```

---

## Improve results with API provider keys

Add API keys (VirusTotal, Shodan, SecurityTrails, etc.) to:

```
~/.config/subfinder/provider-config.yaml
```

This unlocks more sources and increases discovery. The config file has comments showing how to add keys.

---

## Helpful workflow (practical pentest flow)

1. Enumerate and save:

   ```bash
   subfinder -d rakuten.com -o rakuten_subs.txt
   ```
2. Remove duplicates / sort:

   ```bash
   sort -u rakuten_subs.txt -o rakuten_subs.txt
   ```
3. Probe for live web services:

   ```bash
   cat rakuten_subs.txt | httpx -ports 80,443 -silent -o rakuten_live.txt
   ```
4. Run quick vuln checks with `nuclei` (after installing templates):

   ```bash
   cat rakuten_live.txt | nuclei -t /path/to/nuclei-templates/ -o rakuten_nuclei_results.txt
   ```

---

## Troubleshooting tips

* If `subfinder` prints provider errors, check `~/.config/subfinder/provider-config.yaml` for valid API keys.
* If it’s slow: increase `-t` (threads) or add more provider API keys.
* If you want the most recent features, prefer the `go install ...@latest` method shown above.

---

Want me to:

* give the exact `provider-config.yaml` example with placeholders for API keys, or
* produce a one-line script to enumerate → probe → run nuclei and save outputs?

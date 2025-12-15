# Attack Strategy

High-level playbook used to quickly find **initial access** and collect **credentials** in an internal AD lab.

## Workflow

1. **Start early with poisoning**
   - Run **mitm6** or **Responder** to catch hashes while the network generates traffic.

2. **Scan to generate traffic + map services**
   - Identify exposed services (SMB/LDAP/WinRM/HTTP) and prioritize reachable targets.

3. **If scans are slow: pivot to web**
   - Fast web discovery/version checks (e.g., Metasploit `http_version`).

4. **Check common web logins**
   - Look for default/weak creds on internal portals (printers, Jenkins, admin panels).

## Typical chaining

`LLMNR` → captured hash → crack → spray → new creds → `secretsdump` → local admin hashes → pivot with local accounts

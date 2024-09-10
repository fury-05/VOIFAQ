# VOI Network F.A.Q.

### Q. How to Run Node?
**Ans.** Preferred: A VPS with minimum configuration [Getting Started with VOI Network](https://voinetwork.github.io/voi-swarm/getting-started/introduction/)

- To create a new wallet, run the following command:
```bash
/bin/bash -c "$(curl -fsSL https://get.voi.network/swarm)"
```

- To import an existing wallet using a phrase, use this command:
```bash
export VOINETWORK_IMPORT_ACCOUNT=1
/bin/bash -c "$(curl -fsSL https://get.voi.network/swarm)"
```
---

### Q. I ran the node, but it is not online?
**Ans.** Ask the user to run this node status check command:
```bash
~/voi/bin/get-node-status
```

- Depending on the output, address the problem. For example, for the "Expiring Participating Keys" issue, ask the user to run:
  
```bash
  ~/voi/bin/generate-participation-key <account_address>
```

- After generating keys, verify once the old key term expires by running the node status check command again. If not applied automatically, run:

```bash
~/voi/bin/go-online <account_address>
```

- Follow this with:
  
```bash
  ~/voi/bin/set-telemetry-name <telemetry_name>
```

- Ask the user to check node status again.

---

### Q. How to get my GUID long version?
**Ans.** Ask the user to run this command:

```bash
~/voi/bin/get-telemetry-status
```
---

### Q. How to get my wallet phrase from a node I didn't save before?
**Ans.** Ask the user to run this command:

```bash
~/voi/bin/get-account-mnemonic <account_address>
```

---

### Q. I need to restart my Node?
**Ans.** Ask the user to run this command:

```bash
~/voi/bin/goal node restart
```
---

### Q. What is Taco, UNITS, Chubs, GM, and Points?
**Ans.** These are projects built on the VOI chain and can be collected through Discord activity like rains, sends, or drops, or bought on Humble or Nomadex using testnet VOI tokens.

- Tacos will be converted 1:1 ratio for mainnet. A user can hold a max of 25 million Tacos or Old Tacos combined.

- Asset Id for Tacos:
- New TacoCoin: 40427782
- Old TacoCoin: 6795477
  
- UNITS are limited to 100 per user and will also convert to mainnet 1:1.

- Asset Id for UNITS: 48703447
- wUNITS: 49512907
- Chubs can be bought on Nautilus, and users shouldn't hold more than 10.

- GM tokens will convert 1:1 and can only be collected (not bought). No limit on collection.

- Points won’t be transferred to mainnet, but holding them boosts VOI testnet rewards by contributing to your final testnet score.

---

### Q. When will users get their testnet rewards to sell?
**Ans.** As per the current schedule, rewards are set for release on October 28, 2024. You will be able to sell them on exchanges on or after this date.
---

### Q. What is the lockup period and how long before we get our rewards?
**Ans.** All testnet rewards will have a 12-month lockup period with linear release mechanics. For example, if you earned 12,000 VOI as rewards, you will receive 1,000 VOI per month for the next 12 months.

The lockup period varies depending on how many years each individual selected to lock their rewards.

---



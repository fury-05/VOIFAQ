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

### Q. How do I keep my node healthy?
**Ans.** It's essential to regularly monitor the health of your node. You can use tools like Voi CLI to check system metrics, node status, and participation key validity. Keeping an eye on CPU usage, disk space, and network bandwidth will help ensure that your node stays online and performs optimally. You can also use the Voi Checker tool to automate some of this monitoring.

Commands:
```bash
~/voi/bin/get-node-status
```
- For participation key expiration:
```bash
~/voi/bin/generate-participation-key <account_address>
```
- Ensure to use the latest cli tools and stay updated to avoid problems with key expiration​.
---

### Q. What happens if my participation key expires?
**Ans.** When your participation key expires, your node stops participating in the network, which can affect both its performance and your rewards. To fix this, generate a new participation key using the command:
```bash
~/voi/bin/generate-participation-key <account_address>
```
- Ensure the new key is applied and check your node's status again​(

---

### Q. How can I check my node's health in real time?
**Ans.** You can use Voi CLI or third-party monitoring tools like Voi Node Health Checker or Voi Proposer Data. These tools allow you to track metrics like node participation, GUID, and network health in real time. It’s advisable to monitor these weekly to ensure your node is performing well and participating correctly
- [NODE DASHBOARD](https://voi-nodes.dev/)
- [24 Hrs Data Chris Api] (https://cswenor.github.io/voi-proposer-data/index.html)
---

### Q. How do I restart my node if it's stuck?
**Ans.*** If your node is not responding or stuck in an offline state, restarting it may help. Use the following command:
```bash
~/voi/bin/goal node restart
```
- This will restart your node and clear any potential issues preventing it from syncing​.

---

### Q. What are the node running options in Voi?
**Ans.** Voi offers multiple ways to run a node depending on your hardware and technical capabilities:

Voi Swarm for Linux-based systems with a single command install.
Aust’s 1-Click Node for Windows, MacOS, and Linux, which provides a more graphical interface for easy setup,

---

### Q. User is running Windows OS and Ubunt on Virtual Machine.
**Ans.** VOI swarm doest not suppport this kind of virtulization you need to have a machine with ubunt installed on it directly.

---

### Q. My node score is low ?
**Ans.** Check the hosting provider first if its Contabo then ask user to change it.
Check VOI in address connected to node you need minimum 2100VOI
Check if telemetry is enabled and true.

---

### Q. How to Removing Your Installation ?
**Ans.** To uninstall, execute the following commands:
- Leave the Swarm
```docker swarm leave --force```
- Remove the ~/voi directory
```rm -rf ~/voi/```
- Remove the /var/lib/voi directory
```rm -rf /var/lib/voi```

---

### Q. If user are not able to login in VPS ?
**Ans.** Ask them to contact hosting provider support for login vps problem and SSH key problem.

---

### Q. I want to migrate my node to diffrent vps ?
**Ans.** First login to existing vps and take backup of Wallet phrase if not already taken. Then take backup of long GUID version using following commands :
- For Wallet phrase 
```~/voi/bin/get-account-mnemonic <account_address>```
- For GUID
```~/voi/bin/get-telemetry-status```

- Then Login to new vps and use import existing wallet command 
```export VOINETWORK_IMPORT_ACCOUNT=1
/bin/bash -c "$(curl -fsSL https://get.voi.network/swarm)"```

- Name its Telemetry as same before 
- Continue with prompts 
- Create a password for wallet 
- Enter Wallet Phrase of old address
- Let blocks Catch up
- Now run Telemetry and guid set command 
```~/voi/bin/set-telemetry-name <telemetry_name> <telemetry_guid>```
- Check using node status command 
```~/voi/bin/get-node-status```
- If all is online no problem is you get any error refer above trouble shooting.

---


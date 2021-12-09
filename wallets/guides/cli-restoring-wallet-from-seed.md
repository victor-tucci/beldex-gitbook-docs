---
description: Restoring your wallet from seed
---

# CLI Restoring Wallet from Seed

To fully restore your wallet and be able to view balance and make transactions, having your seed stored will be enough. You don't need your wallet password or other keys to restore the wallet once you have a seed phrase.

### Step 1: Download and unzip CLI wallet <a href="#step-1-download-and-unzip-cli-wallet" id="step-1-download-and-unzip-cli-wallet"></a>

* Download the latest release of wallet CLI software for your desired operating system: [https://github.com/beldex-coin/beldex/releases](https://github.com/beldex-coin/beldex/releases)
* Unzip `beldex-[operating-system]-[platform]-[version].zip` file

![](../../.gitbook/assets/cliwalletfolder.jpg)

### Step 2: Run wallet in restore mode <a href="#step-2-run-wallet-in-restore-mode" id="step-2-run-wallet-in-restore-mode"></a>

* Open a [Command Prompt](https://en.wikipedia.org/wiki/Cmd.exe) (Windows) or [Terminal](https://en.wikipedia.org/wiki/Terminal\_emulator) (Linux / OSX) and navigate to the wallet folder
* Run wallet with `--restore-deterministic-wallet` argument: `./beldex-wallet-cli --restore-deterministic-wallet`

### Step 3: Enter wallet name <a href="#step-3-enter-wallet-name" id="step-3-enter-wallet-name"></a>

You will be prompted to enter a wallet name and click \[Enter]. You can enter any name here, use something rememberable and meaningful.

![](../../.gitbook/assets/cliwalletrestore.jpg)

### Step 4: Enter your seed phrase <a href="#step-4-enter-your-seed-phrase" id="step-4-enter-your-seed-phrase"></a>

* You will be prompted to enter 25 word mnemonic seed you have stored. Paste it and press \[Enter].&#x20;
* If you have a seed encryption passphrase, enter it on the next step. Otherwise, press \[Enter].

### Step 5: Enter wallet password <a href="#step-5-enter-wallet-password" id="step-5-enter-wallet-password"></a>

* You will be prompted for a password. Enter a new password that follows the [Password Policy](https://en.wikipedia.org/wiki/Password\_policy) and press \[Enter].
* Confirm password and press \[Enter].

### Step 6: Specify a blockchain height <a href="#step-6-specify-a-blockchain-height" id="step-6-specify-a-blockchain-height"></a>

If you know the block height at which wallet was created or a first transaction was made, you can enter it here. Specifying a blockchain height will help to scan the wallet faster.

If you don't know a specific blockchain height, press \[Enter] for scanning from block height 0.

### Step 7: Wait for the refresh process to finish <a href="#step-7-wait-for-the-refresh-process-to-finish" id="step-7-wait-for-the-refresh-process-to-finish"></a>

For refresh process to start, you need to have your daemon running. Another option would be to use a remote node. For that, use the following command, replacing and with the host and port number of the remote node you are connecting to:

```
./beldex-wallet-cli --daemon-address <host>:<port>
```

Once refresh is done, you can use your full functioning restored wallet. Your public wallet address will remain the same.

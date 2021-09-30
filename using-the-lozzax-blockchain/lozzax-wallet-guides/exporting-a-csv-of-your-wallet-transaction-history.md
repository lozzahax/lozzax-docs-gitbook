# Exporting a CSV of your wallet transaction history

The Lozzax Wallet allows you to export a CSV of transactions that have occurred in the wallet. The process for both the GUI wallet and the CLI wallet are as follows:

### **GUI Wallet**

The Lozzax GUI wallet as of v1.6.0 supports the exporting of your transactions. After logging into your wallet:

* Click on SETTINGS at the top right of the app
* Click on Export Transfers

![](https://github.com/lozzahax/lozzax-docs-gitbook/raw/master/.gitbook/assets/export.jpg)

* The wallet will then prompt you for a folder to save the CSV to. This defaults to a CSV directory within the Lozzax folder \(Same directory your wallet keys are stored\) but you can edit this to any location.

![](https://github.com/lozzahax/lozzax-docs-gitbook/raw/master/.gitbook/assets/export.jpg)

* Click Export and you will be prompted for your wallet password
* You will then see a green notification at the bottom of the window if the export is successful. For example: “Transfers exported to /home/sean/Desktop/transfers.csv”

### CLI Wallet

Note you will either need to be running a local daemon \(lozzaxd\) or have a remote node that the CLI wallet can communicate with. 

Navigate to the directory that the lozzax-wallet-cli executable is stored in:

```bash
sean@sean-MS-7A33:~/lozzax-core/build$ cd bin/
sean@sean-MS-7A33:~/lozzax-core/build/bin$ ls
lozzax-blockchain-ancestry  lozzax-blockchain-import              lozzax-blockchain-usage      lozzax-sn-keys
lozzax-blockchain-depth     lozzax-blockchain-mark-spent-outputs  lozzaxd                      lozzax-wallet-cli
lozzax-blockchain-export    lozzax-blockchain-stats               lozzax-gen-trusted-multisig  lozzax-wallet-rpc
```

Run the lozzax-wallet-cli:

```bash
sean@sean-MS-7A33:~/loki-core/build/bin$ ./lozzax-wallet-cli
```

If you are using a remote node instead of a local daemon you will need to add additional command line arguments here:

```bash
sean@sean-MS-7A33:~/loki-core/build/bin$ ./lozzax-wallet-cli --daemon-address public.lozzax.xyz:22123

```

The wallet will ask you to enter the name of your wallet file. If you are coming from the GUI wallet these are stored in the following locations

1. Linux: ~/Lozzax/wallets/MyWallet.keys
2. Windows: C:\Users\&lt;username&gt;\Documents\Lozzax\wallets
3. Mac: ~/Lozzax/wallets/MyWallet.keys

These can alternatively be included as command line flags

```bash
sean@sean-MS-7A33:~/loki-core/build/bin$ ./lozzax-wallet-cli --daemon-address public.lozzax.xyz:22123 --wallet-file ~/Lozzax/wallets/MyWallet --password "password"
```

Once the wallet has synced you will be able to call \`export\_transfers\` which saves the CSV to the same location as where you ran the lozzax-wallet-cli \(Most likely the same location as the executable\).

```bash
[wallet T6SjAL (has locked stakes)]: export_transfers all output=lozzax.csv
```


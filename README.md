# DreamLedger Masternode Setup Tutorial

Welcome to the DreamLedger Masternode setup guide. Follow these steps to get your masternode up and running on a Linux server.

## 1. Open Your Windows Wallet

- Navigate to `Tools` -> `Debug console`.
- Type `getnewaddress` to create an address for the masternode fee.

    Example output:
    ```
    TRPLV4dXmEFMSgXg2Xu6skN9pmw8TAo4N5
    ```

## 2. Transfer the Masternode Fee

- Go back to your wallet overview.
- Click on the "Send" toolbar button.
- Enter the address you got from `getnewaddress` in the "Pay To:" field.
- Enter "5" in the "Amount:" field.
- Click "Send".

## 3. Wait for Confirmations

- Wait until the transaction is confirmed by 6 blocks.

## 4. Set Up the Masternode on Your Server

### Connect to Your Server

- Use SSH to connect to your Ubuntu server.

### Update Your Server

Download & Install the Wallet Daemon
cd $HOME
wget "https://dl.walletbuilders.com/download?customer=973453a6cf9305a664c18c3f856b15b9b52084c26af76620e2&filename=dreamledger-daemon-linux.tar.gz" -O dreamledger-daemon-linux.tar.gz
tar -xzvf dreamledger-daemon-linux.tar.gz
sudo mv dreamledgerd dreamledger-cli dreamledger-tx /usr/bin/

Configure Your Wallet
mkdir $HOME/.dreamledger
nano $HOME/.dreamledger/dreamledger.conf


Paste the following configuration, replacing <externalip> with your VPS's IP address and <masternodeblsprivkey> with your masternode's BLS private key:

rpcuser=rpc_dreamledger
rpcpassword=<RANDOM_PASSWORD>
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
listen=1
server=1
daemon=1
maxconnections=125
masternode=1
masternodeblsprivkey=<masternodeblsprivkey>
externalip=<externalip>


Start Your Masternode

dreamledgerd

Please, remember, security first! Always be careful when handling private keys and personal information. We look forward to having you as part of our growing community. Join us on Discord and Telegram for support and more information.



Remember to replace placeholders like `<RANDOM_PASSWORD>`, `<externalip>`, and `<masternodeblsprivkey>` with actual values specific to your setup. This markdown guide is structured for clarity, making it easier for users to follow the steps to set up a DreamLedger masternode.



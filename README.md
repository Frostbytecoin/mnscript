# Frostbyte
Shell script to install a [Frostbyte Masternode]() on a Linux server running Ubuntu 16.04.
***

## Installation
```
wget https://raw.githubusercontent.com/Frostbytecoin/mnscript/master/fstx_install.sh
```
```
chmod +x fstx_install.sh
```
```
./fstx_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Frostbyte Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **2500** FSTX to **MN1**. You need to send all 2500 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open bytepay Core Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
startmasternode alias false <name>  # Start masternode replace <name> with your masternode alias
frostbyte-cli getblockcount #To get blockcount
frostbyte-cli stop #To stop masternode
./frostbyted -resync &  #To Resync
watch frostbyte-cli getinfo  # Check syncing blocks
./frostbyted -reindex # To Reindex
systemctl status frostbyte.service  #o check Frostbyte service status
systemctl start frostbyte.service  #To start Frostbyte service
systemctl stop frostbyte.service  #To stop Frostbyte service
frostbyte-cli masternode count  #To check masternode list
```

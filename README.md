# BLibrary Masternode install (Ubuntu 16.04)
***

## Installation
```
wget -q https://raw.githubusercontent.com/blockchain-library/BLibrary-install/master/install.sh
bash install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the BLibrary Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000** BLIB to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start "alias" "0" "MN1"
```
14. Login to your VPS and check your masternode status by running the following command:.
```
blibrary-cli masternode status
```
***

## Usage:
```
blibrary-cli mnsync status
blibrary-cli masternode status  
blibrary-cli getinfo
```
Also, if you BLibrary to check/start/stop **BLibrary**, run one of the following commands as **root**:

```
systemctl status blibrary.service #To check if BLibrary service is running  
systemctl start blibrary.service #To start BLibrary service  
systemctl stop blibrary.service #To stop BLibrary service  
systemctl is-enabled blibrary.service #To check if BLibrary service is enabled on boot  
```  
***

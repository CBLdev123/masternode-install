# CBSLCOIN
Shell script to install a [CBSLCoin Masternode](https://www.cbsl.com/) on a Linux server running Ubuntu 14.04,16.04 or 18.04. Use it on your own risk.  
This script will instal version 1.0
***

## VPS installation:
```
wget -N https://github.com/CBLdev123/masternode-install/blob/master/masternode-install.sh
bash masternode-install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Smelter Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **CBSL** to **MN1**.
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
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Open **Debug Console** and type:
```
startmasternode "alias" "0" "MN1"
```
***

## Usage:
```
CBSL-cli mnsync status
CBSL-cli getinfo
CBSL-cli masternode status
```
Also, if you want to check/start/stop **CBSLCoin** , run one of the following commands as **root**:

```
systemctl status CBSL #To check the service is running.
systemctl start CBSL #To start CBSL service.
systemctl stop CBSL #To stop CBSL service.
systemctl is-enabled CBSL #To check whetether CBSL service is enabled on boot or not.
```
***
## Old CBSLCoin delete:
In order to delete your CBSL Masternode,  please run the following commands:
```
systemctl stop CBSL
systemctl disable CBSL
rm -r /root/.CBSL*
rm -r /usr/local/bin/CBSL*
rm -r /etc/systemd/system/CBSL.service
```
***


## Donations:

Any donation is highly appreciated.

**BTC**:   
**ETH**:   
**LTC**:   

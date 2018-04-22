# Motile

Linux Daemon: Compiled for Ubuntu 17.10 - https://github.com/ecs87/Motile/releases

Hot/Cold Masternode Notes:
  In your Windows wallet open up the debug console (Help -> Debug Window -> Console (tab))

  Type masternode outputs, take note of this.

  Type masternode genkey, also take note of this.

  Login to your masternode and go to (or create) the directory where you want the daemon to reside. Run this: wget https://github.com/ecs87/Motile/releases/download/1/Motiled
  
  Then gain permissions by running: chmod 700 Motiled
  
  Run the daemon with: ./Motiled -daemon
  
  If you're not used to setting up .conf files for masternodes here's a template for Motile:
  
  rpcuser=YourRPCUserName
  rpcpassword=YourRPCPassword
  rpcport=7217
  port=7218
  daemon=1
  server=1
  rpcallowip=127.0.0.1
  testnet=0
  masternode=1
  masternodesoftlock=1
  masternodeprivkey=WhatYouGotFromMasternodeGenkeyEarlier

  Run "nano /root/.Motile/Motile.conf" and add your "masternode genkey" from the previous step into the masternodeprivkey= field. Then Save it (CTRL+X -> Y -> ENTER) and stop the daemon: ./Motiled stop, then restart it: ./Motiled -daemon (press CTRL+C after the server has started to return back to the cmd line).

  NOW on your windows wallet go to the Masternodes tab and click the Create... button.

  Enter a name/alias for your masternode, enter the IP address of your masternode and port (IE: 11.11.11.11:7218, DO NOT FORGET THE PORT), the privkey (what you got from masternode genkey), the TX Hash (the first long hexadecimal string you got from "masternode outputs"), and the Output Index (the second single digit number you got from "masternode outputs").
  
  Then restart your Windows wallet, go back to the Masternodes tab (unlock your wallet) and click Start All. If your 5000MIE transaction has over 7 confirmations, then you should be finished (if your 5000MIE transaction does not have over 7 confirmations, then you'll need to wait till it does, then click Start All again; only when ./Motiled masternode status on your VPS shows "status: 9" are you completely finished).

# Motile

Windows Masternode Notes:
  In your Windows wallet open up the debug console (Help -> Debug Window -> Console (tab))

  Type masternode outputs, take note of this.

  Type masternode genkey, also take note of this.

  On your masternode type "nano /root/.Motile/Motile.conf" and add your "masternode genkey" from the previous step into the masternodeprivkey= field. Then Save it (CTRL+X -> Y -> ENTER) and stop the daemon: ./Motiled stop, then restart it: ./Motiled -daemon (press CTRL+C after the server has started to return back to the cmd line).

  NOW on your windows wallet go to the Masternodes tab and click the Create... button.

  Enter a name/alias for your masternode, enter the IP address of your masternode and port (IE: 11.11.11.11:7218, DO NOT FORGET THE PORT), the privkey (what you got from masternode genkey), the TX Hash (the first long hexadecimal string you got from "masternode outputs"), and the Output Index (the second single digit number you got from "masternode outputs").
  
  Then restart your Windows wallet, go back to the Masternodes tab and click Start All. If your 5000MIE transaction has over 7 confirmations, then you should be finished (if your 5000MIE transaction does not have over 7 confirmations, then you'll need to wait till it does, then click Start All again; only when ./Motiled masternode status on your VPS shows "status: 9" are you completely finished).

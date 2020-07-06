
# Bitcoin

## watching the tech
+ [BTC Pay Server](http://docs.btcpayserver.org/) .. [What is BTC Pay?](https://www.youtube.com/watch?v=q7xJMno_B3U) (video)
+ [CryptoTrader Taxes](https://cryptotrader.tax/?fpr=altcoindaily)
+ [Mining by rPI](https://www.instructables.com/id/Bitcoin-Mining-using-Raspberry-Pi/)

## Compliling Bitcon
+ Build instructions in doc/README.md
+ Wants Berkely 4.8 but 5.3 is installed.  add:  --with-incompatible-bdb
+ install requirements
    + sudo apt-get install build-essential libtool autotools-dev automake pkg-config bsdmainutils python3
    + sudo apt-get install libevent-dev libboost-system-dev libboost-filesystem-dev libboost-test-dev libboost-thread-dev
+ ./configure --with-incompatible-bdb --disable-wallet
+ ./configure --help

## Related
+ https://www.linux.com/news/how-install-packages-source-linux/

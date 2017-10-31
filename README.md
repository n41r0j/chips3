What is CHIPS?
--------------

CHIPS is a Bitcoin fork, developed by SuperNET on the Komodo Platform. 
CHIPS will be used as playing chips in decentralized betting games, 
of which Pangea Poker will be the first implementation. 
CHIPS uses the Lightning Network in order to make fast transactions happen in various betting games.

For more information see the [ANN](https://bitcointalk.org/index.php?topic=2078449) on bitcointalk.org.

License
-------

Bitcoin Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.


### Build instructions

#### Dependencies:
`sudo apt-get install software-properties-common autoconf git build-essential libtool libprotobuf-c-dev libgmp-dev libsqlite3-dev python python3 zip jq libevent-dev pkg-config libssl-dev libcurl4-gnutls-dev cmake`
`add-apt-repository ppa:bitcoin/bitcoin`
`sudo apt-get update`
`sudo apt-get install -y libdb4.8-dev libdb4.8++-dev`

#### Boost
`cd`
`wget https://dl.bintray.com/boostorg/release/1.64.0/source/boost_1_64_0.zip`
`unzip boost_1_64_0.zip`
`cd boost_1_64_0`
`./bootstrap.sh`
`./b2`
`./b2 install`

#### CHIPS daemon
`cd`
`git clone https://github.com/jl777/chips3`
`cd ~/chips3`
`./autogen.sh`
`./configure --with-boost=/usr/local/`
`cd src`
`make chipsd`
`make chips-cli`
`cp chips-cli /usr/bin` 
make -> will build everything, including QT wallet
`sudo ldconfig /usr/local/lib`

Run CHIPS daemon:
`./chipsd -daemon`

#### Lightning Network
`cd`
`git clone https://github.com/jl777/lightning`
`cd lightning`
`make`
`daemon/lightning-cli stop; lightningd/lightningd --log-level=debug &`
`cd privatebet`
`./m_bet`
`./client or ./host`



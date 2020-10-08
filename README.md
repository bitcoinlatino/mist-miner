# BTCL Bitcoin Latino

*Primer moneda virtual mineable usando el estándar SLP y la prueba de trabajo del contrato covenant_1 introducido por* **[mistcoin.org](https://mistcoin.org)**

## Ambiente de minería de BTCL

* **BTCL id:** [`20e8e13347a76f6041bf7d31b04a7bbb7e2deb5d95e15ae8619179b3552ca02a`](https://simpleledger.info/token/20e8e13347a76f6041bf7d31b04a7bbb7e2deb5d95e15ae8619179b3552ca02a)
* **BTCL contrato covenant script:**
`MINER_COVENANT_V1`=`"5779820128947f777601207f75597982012c947f757601687f777678827758947f7576538b7f77765c7982777f011179011179ad011179828c7f756079a8011279bb011479815e7981788c88765b79968b0114795e795279965480880400000000011579bc7e0112790117797eaa765f797f757681008854011a797e56797e170000000000000000396a04534c50000101044d494e54200113797e030102087e54797e0c22020000000000001976a914011879a97e0288ac7e0b220200000000000017a9145379a97e01877e527952797e787eaa607988587901127993b175516b6d6d6d6d6d6d6d6d6d6d6d6d6d6d6d6c"`
`TOKEN_INIT_REWARD_V1`=800000000
TOKEN_HALVING_INTERVAL_V1=4320
MINER_DIFFICULTY_V1=3
TOKEN_START_BLOCK_V1=645065
TOKEN_ID_V1="bb553ac2ac7af0fcd4f24f9dfacc7f925bfb1446c6e18c7966db95a8d50fb378"

## Introduction a la minería con el Minero Mist

Esta es una continuación de la versión 0.0.2 del minero que se usa en Mistcoin www.mistcoin.org

## Configuración del Minero Mist en Windows

### 1.Instala los Paquetes

- 

click Launchpad icon in the Dock

type Terminal in the search field

then click Terminal

### 2. Install homebrew

Paste this into the terminal:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`

### 3. Install nodejs with homebrew

brew install node

### 4. Download mist-miner

`git clone https://github.com/blockparty-sh/mist-miner.git`

### 5. Copy example.env file

Go into the downloaded directory

`cd mist-miner`

Paste this into the terminal:

`cp example.env .env`

### 6. Install the dependencies for the project

`npm install`

### 7. Set up Electron Cash SLP Edition Mining Wallet

Open Electron Cash **SLP Edition** and create a new normal wallet

https://simpleledger.cash/project/electron-cash-slp-edition/

Inside the wallet Click on the "Addresses" pane

Right click on the index 0 address and click on "Private key"

Copy the Private key (Command+c) (⌘ key) 

Open the `.env` file (not example.env) by typing this into the terminal:

`open -a TextEdit .env`

On the third line you will see `WIF=""`

Paste your private key inside the quotes so that it looks like this: `WIF="Kansadjasd767263764"`

Save the file and close the editor.

### 8. Fund the Mining Wallet

Inside Electron Cash SLP again, right click the address at index 0 again and click on "Copy address"

Open a different wallet which has BCH available using Electron Cash SLP

Go to the "Send" pane

Inside the "Pay to" field, paste the address and then add the amount like this:

`simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870`

Now copy everything in the "Pay to" field and paste it many more times, I did ~100

It should look like this:

```
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
```

In the "BCH Amount" field put some small amount of BCH (like 0.0001), this wont be used but was needed for me to make it work

Click "Preview" to ensure that there are no mistakes and that the format was correct.

Then click "Sign" and then "Broadcast"

You can now close this wallet.

### 9. Start Mining

Inside the terminal type:

`npm start`

This will build the application and begin mining Mist!

### 10. Updating the Miner

If there are updates in the future you can update by running:

`git pull origin master`

## Block Notifier

### ZMQ

You need a full node for this to connect to, with hashblock on port 28332.

IE your `bitcoin.conf` should have this:

`zmqpubhashblock=tcp://127.0.0.1:28332`

Install zeromq package:

`npm i zeromq@4.6.0`

In `.env` set `BLOCK_NOTIFIER` to `zmq`

### fastminer

Ensure you have a recent C++17-capable compiler and `cmake`. The below assumes `cmake` generates Makefiles, however you can use any generator such as `Ninja`, etc, so long as you place the compiled binary in the `fastmine/` subfolder of this project when done.

    $ cd fastmine
    $ cmake . && make
    $ cd ..

Then set in `.env`

`USE_FASTMINE="yes"`

**Note:** In order for fast mining to work, the expectation is that the `fastmine` executable will be present in the `fastmine/` subdirectory.

## Setup Instructions (Docker; cross-platform)

Clone the repo as per above instructions, setup your .env file and fund your wallet in the same way. No need to install Homebrew, NodeJS, npm modules etc.

### Install Docker

https://docs.docker.com/engine/install/

### Build Docker Image

Run `docker build -t mistminer .` from the root of the repo.

### Run miner

Run `docker run mistminer` to run the miner in a Docker container. `docker ps` will show you all running containers.

Note: Unsure how to get this playing well with zeromq running on the host machine; I've only run successfully without using zmq.

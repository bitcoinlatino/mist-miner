# BTCL Bitcoin Latino

*Primer moneda virtual mineable de Latinoamérica usando el estándar SLP y la prueba de trabajo del contrato covenant_1 introducido por* **[mistcoin.org](https://mistcoin.org)**

## Ambiente de minería de BTCL

* **BTCL id:** [`20e8e13347a76f6041bf7d31b04a7bbb7e2deb5d95e15ae8619179b3552ca02a`](https://simpleledger.info/token/20e8e13347a76f6041bf7d31b04a7bbb7e2deb5d95e15ae8619179b3552ca02a)

* **BTCL contrato covenant script:**

    - **MINER_COVENANT_V1**=`"5779820128947f777601207f75597982012c947f757601687f777678827758947f7576538b7f77765c7982777f011179011179ad011179828c7f756079a8011279bb011479815e7981788c88765b79968b0114795e795279965480880400000000011579bc7e0112790117797eaa765f797f757681008854011a797e56797e170000000000000000396a04534c50000101044d494e54200113797e030102087e54797e0c22020000000000001976a914011879a97e0288ac7e0b220200000000000017a9145379a97e01877e527952797e787eaa607988587901127993b175516b6d6d6d6d6d6d6d6d6d6d6d6d6d6d6d6c"`

    - **TOKEN_INIT_REWARD_V1**=`800000000`

    - **TOKEN_HALVING_INTERVAL_V1**=`4320`

    - **MINER_DIFFICULTY_V1**=`3`

    - **TOKEN_START_BLOCK_V1**=`655223`

    - **TOKEN_ID_V1**=`"20e8e13347a76f6041bf7d31b04a7bbb7e2deb5d95e15ae8619179b3552ca02a"`

## Introduction a la minería con el Minero Mist

Esta es una continuación de la versión 0.0.2 del minero que se usa en Mistcoin www.mistcoin.org

## Configuración del Minero Mist en Windows

Este tutorial es para empezar a minar BTCL en windows.

### 1.Instala los Paquetes

- Descarga e installa **[NodeJS](https://nodejs.org/en/)**
- Descarga e installa **[Git](https://gitforwindows.org/)**
- Descarga e installa **[Microsoft Visual Studio Community 2019](https://visualstudio.microsoft.com/es/)** con los paquetes por defecto **`Node.js`** y **`C++`** y con los componentes **`CMake, MSVC v.140 - VS 2015`**. Si el minero no funciona con estos paquetes, entonces necesita instalar componentes adicionales como **`MSVC v.142 VS 2019, C++ ATL, C++/CLI, Java Script Diagnostic y Python Panel`**.

### 4. Descarga el mist-miner

* Abre la terminal **`PowerShell de Windows`** y accede a la Unidad de disco local C mediante el comando:
    - **`cd ..`** luego *Enter*.
    - **`cd ..`** luego *Enter*.
* Una vez en a Unidad C copia y pega el siguiente comando en la terminal del símbolo del sistema de PowerShell:

    - **`git clone https://github.com/blockparty-sh/mist-miner.git`** luego *Enter*.
    
    - Esto descargará el **mist-miner** en la Unidad C de la PC.


### 5. Crea el archivo .env

* Ve a la carpeta del minero que recién descargaste, sin salir del símbolo del sistema, escribiendo el siguiente comando:

    - **`cd mist-miner`** luego *Enter*.

    - Luego de acceder a la **`carpeta mist-miner`** pega esto en la terminal del símbolo del sistema:

    - **`cp example.env .env`** luego *Enter*. Esto creará el **`archivo .env`** en la carpeta del minero para que configures la wallet donde recibirás los BTCL que comiences a minar.


### 6. Configura la Wallet para Minar BTCL en la `Electron Cash SLP Edition`

* Descarga la **[`Electron Cash SLP Edition`](https://simpleledger.cash/project/electron-cash-slp-edition/)** y crea una wallet normal; puedes colocarle un nombre relacionado con la moneda que vas a minar que es Bitcoin Latino BTCL. Recuerda que debes asegurarte de guardar tu **`frase semilla de 12 palabras`** ya que como todas las wallet de bitcoin cash y SLP esta es de no custodia.

* Guarda la carpeta de la Electron Cash en la Unidad C de la PC.

* Abre la wallet recién creada y dale click al submenú **`Direcciones`**.

    - Dale **`click derecho`** en la dirección de **`index 0`** y luego click en **`clave privada`** en la subventana que se abre.
    
    - Introduce la contraseña de tu wallet y copia la **`clave privada`** en la ventana que se abre.
    
    - Ve hasta la Unidad C de la PC y abre la carpeta **`mist-miner`**.
    
    - Dale **`click derecho`** a el archivo **`.env`** (ojo no en example.env) y dale editar con un editor de texto como **[`Notepad++`](https://notepad-plus-plus.org/downloads/).**
    
    -  

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

### 6. Instala las dependencias para correr el minero


* Sin salir de la terminal **`PowerShell de Windows`** copia y pega el siguiente comando:

    - **`npm install`** luego *Enter*.

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

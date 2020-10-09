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

Esta es una continuación de la **`versión 0.0.2`** del minero que se usa en Mistcoin www.mistcoin.org

## Configuración del Minero Mist en Windows

Este tutorial es para empezar a minar BTCL en windows.

### 1.Instala los Paquetes

- Descarga e installa **[NodeJS](https://nodejs.org/en/)**
- Descarga e installa **[Git](https://gitforwindows.org/)**
- Descarga e installa **[Microsoft Visual Studio Community 2019](https://visualstudio.microsoft.com/es/)** con los paquetes por defecto **`Node.js`** y **`C++`** y con los componentes **`CMake, MSVC v.140 - VS 2015`**. Si el minero no funciona con estos paquetes, entonces necesita instalar componentes adicionales como **`MSVC v.142 VS 2019, C++ ATL, C++/CLI, Java Script Diagnostic y Python Panel`**.

### 2. Descarga el mist-miner

* Abre la terminal **`PowerShell de Windows`** y accede a la Unidad de disco local C mediante el comando:
    - **`cd ..`** luego *Enter*.
    - **`cd ..`** luego *Enter*.
* Una vez en a Unidad C copia y pega el siguiente comando en la terminal del símbolo del sistema de PowerShell:

    - **`git clone https://github.com/bitcoinlatino/mist-miner.git`** luego *Enter*.
    
    - Esto descargará el **mist-miner** en la Unidad C de la PC.


### 3. Crea el archivo .env

* Ve a la carpeta del minero que recién descargaste, sin salir del símbolo del sistema, escribiendo el siguiente comando:

    - **`cd mist-miner`** luego *Enter*.

    - Luego de acceder a la **`carpeta mist-miner`** pega en la terminal del símbolo del sistema:

    - **`cp example.env .env`** luego *Enter*. Esto creará el **`archivo .env`** en la carpeta del minero para que configures la wallet donde recibirás los BTCL que comiences a minar.


### 4. Configura la Wallet para Minar BTCL en la `Electron Cash SLP Edition`

* Descarga la **[`Electron Cash SLP Edition`](https://simpleledger.cash/project/electron-cash-slp-edition/)** y crea una wallet normal; puedes colocarle un nombre relacionado con la moneda que vas a minar que es Bitcoin Latino BTCL. Recuerda que debes asegurarte de guardar tu **`frase semilla de 12 palabras`** ya que como todas las wallet de bitcoin cash y SLP esta es de no custodia.

* Guarda la carpeta de la Electron Cash en la Unidad C de la PC.

* Abre la wallet recién creada y dale click al submenú **`Direcciones`**.

    - Dale **`click derecho`** en la dirección de **`index 0`** y luego click en **`clave privada`** en la subventana que se abre.
    
    - Introduce la contraseña de tu wallet y copia la **`clave privada`** de la ventana que se abre. Las clave privada empieza con **K** o **L**.
    
    - Ve hasta la Unidad C de la PC y abre la carpeta **`mist-miner`**.
    
    - Dale **`click derecho`** a el archivo **`.env`** (ojo no en example.env) y dale editar con un editor de código. Si no tienes uno instalado, te recomiendo que descargues **[`Notepad++`](https://notepad-plus-plus.org/downloads/).**
    
    - Pega tu clave privada en WIF dentro de las comillas. Debe verse de la siguiente manera: **`WIF="Kansadjasd767263764..."`**
    
    - No modifiques nada más, guarda los cambios y cierra el editor.

### 5. Coloca Fondos en BCH en la wallet de minería

Para recibir la recompensa de la minería de BTCL necesitas pagar una comisión o fee por cada bloque minado exitosamente de BTCL. La comisión es de **`0.00001324`** por cada bloque minado de BTCL, que resulta de la diferencia de **`0.00001870-0.00000546`**.

* Nuevamente dentro de la **`Electron Cash SLP`**, **`click derecho`** en la dirección de **`index 0`** y luego escoge **`copiar dirección`** de la ventana que se abre.

* Abre o crea una nueva wallet (diferente a la de la minería) con la Electron Cash SLP, la cual tenga suficientes fondos en BCH disponibles.

* Ve hasta el submenú **`Enviar`** y en el campo **`Pagar a`** pega la dirección de tu wallet de minería; la que acabas de copiar en el paso anterior.

* Luego añade la cantidad a enviar de 0.00001870 BCH, debe verse de la siguiente manera:

    * **`simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870`**

* Ahora repite **`simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870`** en el mismo campo **`Pagar a`** muchas veces, por ejemplo unas 100 veces.

* Debería verse dela siguiente manera:

    ```
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    simpleledger:qpasd8a7sdasdjkasd7as7dd,0.00001870
    ```

* En el campo **`BCH Amount`** coloca una pequeña cantidad de BCH (0.00001000 estará bien).

* Asegurate de no tener errores y luego dale click en **`Enviar`**.

### 6. Instala las dependencias para correr el minero

* Vuelve a la terminal **`PowerShell de Windows`** copia y pega los siguientes comandos:

    - **`npm install`** luego *Enter*.
    
    - **`npm i`** luego *Enter*.
    
     - **`npm run tsc`** luego *Enter*.
     
     - **`npm install npm@latest -g`** luego *Enter*.

### 7. Inicia la minería de BTCL

* Dentro de la terminal del **`PowerShell`** escribe el comando:

    * **`npm start`** para inciar el minero.
    
    * Si todo lo hiciste bien pronto comenzarás a recibir las recompensas de bloque por minar BTCL.

### 8. Actualizando el Minero Mist

* Si hay alguna actualización en el futuro, corre el siguiente comando para mantener tu minero actualizado:

    * **`git pull origin master`**


### 9. Configurando el Fastminer

Aseguráte de tener la versión reciente de **`C++17-capable compiler y cmake`**. Los siguientes comandos asumen que **`cmake`** genera los archivos, sin embargo busca en la carpeta **`fastmine`** de esta repo el archivo **[`fastmine_1.zip`](https://github.com/bitcoinlatino/mist-miner/blob/master/fastmine/fastmine_1.zip)**, descargalo y descomprimelo en la **`subcarpeta fastmine`** del minero que tienes instalado en el disco local C **`mist-miner`** de tu PC.

* cd fastmine
    
    $ cmake . && make
    $ cd ..

* Luego configura el archivo **`.env`** pasando fastmine a **YES**

    * **`USE_FASTMINE="yes"`**
  
### 10. También BTCL puede ser minado en un teléfono android

* Se ha hecho un fork del repositorio de **[`Maze Mining`](https://github.com/bitcoinlatino/mining)** para minar con el **`BCHD Miner`** y con la **[APP UserLand](https://play.google.com/store/apps/details?id=tech.ula&hl=es)**.

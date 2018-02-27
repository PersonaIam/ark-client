<!-- ![ARK Client](https://i.imgur.com/Sj3s29m.jpg) -->

# persona-client
CLI client for the Persona blockchain.
You can connect to devnet, mainnet or your custom private/public Persona/ARK-derived blockchain.

Features:
- connection to network or a node,
- get stats of a network,
- create or get status of an account,
- register a name with an account,
- verify other acounts` identity,
- create vanity accounts (multi-cpu supported),
- register a delegate,
- vote for a delegate,
- sign and verify message using your address.

# Installation
You need to have node (version 7.6.0 or newer) installed. Then:
```
$> npm install -g personaIam/persona-js#persona-dev
$> persona-client
    ____                                      _________            __
   / __ \___  ______________  ____  ____ _   / ____/ (_)__  ____  / /_
  / /_/ / _ \/ ___/ ___/ __ \/ __ \/ __ `/  / /   / / / _ \/ __ \/ __/
 / ____/  __/ /  (__  ) /_/ / / / / /_/ /  / /___/ / /  __/ / / / /_
/_/    \___/_/  /____/\____/_/ /_/\__,_/   \____/_/_/\___/_/ /_/\__/

persona>
```

# Usage
```
persona> help

  Commands:

    help [command...]                     Provides help for a given command.
    exit                                  Exits application.
    connect <network>                     Connect to network. Network is devnet or mainnet
    connect node <url>                    Connect to a server. For example "connect node 5.39.9.251:4000"
    disconnect                            Disconnect from server or network
    network stats                         Get stats from network
    account status <address>              Get account status
    account vote <name>                   Vote for delegate <name>. Remove previous vote if needed. Leave empty to clear vote
    account send <amount> <recipient>     Send <amount> persona tokens to <recipient>. <amount> format examples: 10
    account delegate <username>           Register new delegate with <username>
    account create                        Generate a new random cold account
    account register <first> <last>       Register the name provided with the account
    account verify <address>              Verify the identity of address
    account vanity <string>               Generate an address containing lowercased <string> (WARNING you could wait for long)
    message sign <message>                Sign a message
    message verify <message> <publickey>  Verify the <message> signed by the owner of <publickey> (you will be prompted to provide the signature)
```



```
persona> connect testnet
Node: 5.135.75.64:4101, height: 1708
persona testnet>
```

```
persona testnet> account create
Seed    - private: forum inch panel balcony beyond note assist seminar bird blame vehicle feel
WIF     - private: S9s7rLszCxEMnDkNPQ8HKBMohCBnnFVF7hsL5HkFaYai3W3tW4P3
Address - public : PMxxtvwbjpdhRgqaBeVjYMMMqRwBQnEQ94
```

```
persona testnet> account send 100 AMUeELFkFtN5obvStkV9Zt44GEjEaYgKhH
passphrase: ************************************************************************
Transaction sent successfully with id 7adbf890c88dd345eacbac63e94610fa5f3905528cdc1c36740c3ba3fa3db302
```

```
persona testnet> account delegate rockingark
passphrase: **************************************************************************
Transaction sent successfully with id b857f302611e4f36a33ea886f7bcb951633406ba1f5e40393893234a46ce54eb
```

```
persona testnet> account register rick sanchez
passphrase: *********************************************************************
? Registering rick sanchez as your name to PNhiYW5Ledtu7wGEdSQGwrns8ddFYCBw1C Yes
Transaction sent successfully with id a68bf5e7b07252005a588c7a35d0a8dacb9b4a26ac853058981680f5b6955b61
```

```
persona testnet> account verify PNhiYW5Ledtu7wGEdSQGwrns8ddFYCBw1C
Id fragments retrieved for address: PNhiYW5Ledtu7wGEdSQGwrns8ddFYCBw1C

ID 0: 677120068a51b2b73e292eaf692cce4881a1fd50fc84fe5e3d2675a5f0bc4a84 - data: {"firstname":"rick","lastname":"sanchez"}
ID 1: f5aee7808a43f214084800715d9dfc3dea65da9cfd3813165e3873fcdca5d4b7 - data: {"firstname":"rick","lastname":"sanchez"}


Please select the ID you wish to certify: 1
passphrase: ****************************************************************************
? Verifying ID: f5aee7808a43f214084800715d9dfc3dea65da9cfd3813165e3873fcdca5d4b7 for address PNhiYW5Ledtu7wGEdSQGwrns8ddFYCBw1C Yes
Transaction sent successfully with id 46dcce01c7dea4a7f1ae7e28cc9c3ac8e0cad782de6c398ea1f69c4d2ec75475
```

```
persona testnet> account status PMxxtvwbjpdhRgqaBeVjYMMMqRwBQnEQ94
{ address: 'PMxxtvwbjpdhRgqaBeVjYMMMqRwBQnEQ94',
  unconfirmedBalance: '7500000000',
  balance: '7500000000',
  publicKey: '020cfc61215f2682bd70cce14aaa6cfa6fa3b0507771cb1943aee071a7dd57bcf6',
  username: 'rockingark',
  vote: '0',
  producedblocks: 0,
  missedblocks: 0,
  rate: 52,
  approval: 0,
  productivity: 0 }
```

# License

**MIT License**

- Copyright © 2017 ARK.io
- Copyright © 2017 FX Thoorens

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

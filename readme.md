### Storage Demo

> This git repository serves the purpose of providing example and facilitating continuous integration (CI) for **forking**, **reading**, **writing** EVM storage with [0xweb](https://github.com/0xweb-org/0xweb) and [hardhat](https://hardhat.org/).

----

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/0xweb-org/examples-storage/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/0xweb-org/examples-storage/tree/master)

----



## 1. How was this project bootstrapped.

```bash
$ npm i 0xweb -g
$ 0xweb init --hardhat
$ 0xweb i 0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48 --name USDC --chain eth
```

## 2. Forking the mainnet in `hardhat.config.js`

> Public Ankr RPC node is used.

## 3. What actions were added in [usdc.act.ts](actions/usdc.act.ts)

- `create-accounts`: Generate `foo` and `bar` accounts (_address+private key_)
- `set-balance`: Modify the EVM storage in `USDC` contract to set the balance for the address `foo` to have `50_000$`
- `transfer-balance`: Execute normal transaction to transfer the balance from `foo` to `bar`


## 4. How we test the actions in [usdc.spec.ts](test/usdc.spec.ts)

- `create-accounts`: Execute action and check the output
- `set-balance`: Execute action and use `0xweb` cli to check the `foo` balance
- `transfer-balance`: Execute action and use `0xweb` cli to ensure `foo` balance is empty, but the `bar` address has funds



----

🏁 [0xweb.org](https://0xweb.org)

# Permit2
Permit2 introduces a low-overhead, next generation token approval/meta-tx system to make token approvals easier, more secure, and more consistent across applications.

## Bug Bounty
This repository is subject to the DerpDEX Bug Bounty program, per the terms defined (here)[https://derpdex.gitbook.io/home/developer-bug-bounty/guidelines].

## Address
| Contract | Testnet Address | Mainnet Address |
| --- | --- | --- |
| `Permit2` | [`0x7dBaee32F615b50B318A8650eE23214768d25b34`](https://goerli.explorer.zksync.io/address/0x7dBaee32F615b50B318A8650eE23214768d25b34#contract) | [`0x37a47BEd105deFc9d4242C8F7232f1fF61e24976`](https://explorer.zksync.io/address/0x37a47BEd105deFc9d4242C8F7232f1fF61e24976) |


## Project structure

- `/contracts`: smart contracts.
- `/deploy`: deployment and contract interaction scripts.
- `/test`: test files
- `hardhat.config.ts`: configuration file.

## Commands

- `yarn hardhat compile` will compile the contracts.
- `yarn run deploy` will execute the deployment script `/deploy/deploy-Permit2.ts`. Requires [environment variable setup](#environment-variables).
- `yarn hardhat verify --network zkSyncTestnet CONTRACT_ADDRESS_HERE` will verify the contracts on the zkSync testnet.

`yarn run deploy` is configured in the `package.json` file and run `yarn hardhat deploy-zksync`.

### Environment variables

In order to prevent users to leak private keys, this project includes the `dotenv` package which is used to load environment variables. It's used to load the wallet private key, required to run the deploy script.

To use it, rename `.env.example` to `.env` and enter your private key.

```
WALLET_PRIVATE_KEY=123cde574ccff....
```

### Local testing

In order to run test, you need to start the zkSync local environment. Please check [this section of the docs](https://v2-docs.zksync.io/api/hardhat/testing.html#prerequisites) which contains all the details.

If you do not start the zkSync local environment, the tests will fail with error `Error: could not detect network (event="noNetwork", code=NETWORK_ERROR, version=providers/5.7.2)`

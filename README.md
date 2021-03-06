# ๐ Emerald Academy

## ๐ฉ Challenge 0: ๐ Hello World Example ๐ค

๐ซ Deploy a simple HelloWorld contract to learn the basics of the Flow blockchain and Cadence. You'll use:
- The local Flow emulator to deploy smart contracts. 
- The local Flow dev wallet to log into test accounts.
- A template Next.js app with sample scripts and transactions to interact with your contract.

๐ The final deliverable is an app that lets users read and change a greeting field on Flow testnet.

๐ฌ Meet other builders working on this challenge and get help in the [Emerald City Discord](https://discord.gg/emeraldcity)!

---

# Checkpoint 0: ๐ฆ Install ๐

Required: 
* [Git](https://git-scm.com/downloads)
* [Node](https://nodejs.org/dist/latest-v16.x/)  (๐งจ Use Node v16 or a previous version as v17 may cause errors ๐งจ)

```sh
git clone https://github.com/emerald-dao/0-hello-world.git
```

> in a terminal window, start your ๐ฑ frontend:

```sh
cd 0-hello-world
npm install
npm run dev
```

> in a second terminal window, start your ๐ทโ local emulator:

```bash
cd 0-hello-world
flow emulator start -v
```

> in a third terminal window, ๐ธ start your local wallet:

```bash
cd 0-hello-world
flow dev-wallet
```

> in a fourth terminal window, ๐พ deploy your contract:

```bash
cd 0-hello-world
flow project deploy
```

> You can `flow project deploy --update` to deploy a new contract any time.

๐ฑ Open http://localhost:3000 to see the app

---

# Checkpoint 1: ๐ Wallets

> ๐ฅ We'll be using **the local Flow dev wallet** on localhost...

> ๐ Click the "Log In" button and notice a window appears with different accounts to select, each with their own FlowToken balance. Select the first account to log in to it.

---

# Checkpoint 2: ๐ Reading the Greeting 

> ๐ Click the `GET GREETING` button to see your greeting:

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

---

# Checkpoint 3: โ๏ธ Changing the Greeting 

> โ๏ธ Change the greeting!  Click the `CHANGE GREETING` button:

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

๐ You should see your greeting change:

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

๐ You can also check out your smart contract `HelloWorld.cdc` in `flow/cadence/HelloWorld.cdc`.

๐ผ Take a quick look at how your contract get deployed in `flow.json`.

๐ If you want to make frontend edits, open `index.js` in `pages/index.js`.

---

# Checkpoint 4: ๐พ Deploy it!

๐ Ready to deploy to a public testnet?!?

> Change the `accessNode.api`, `discovery.wallet`, and `0xDeployer` configurations in `flow/config.js` to their testnet equivalents.

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

๐ Generate a **deployer address** with `flow keys generate --network=testnet`

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

๐ Create your **deployer account** by going to https://testnet-faucet.onflow.org/, pasting in your public key from above, and clicking `CREATE ACCOUNT`: 

๐จ๐จ๐จ TODO: ADD IMAGE HERE ๐จ๐จ๐จ

โฝ๏ธ Add your testnet account to `flow.json` as by modifying the following lines of code:

```json
"accounts": {
  "emulator-account": {
    "address": "f8d6e0586b0a20c7",
    "key": "cdb3410ae829f5e2a29f71f53efbce66bde1187948d6317de6918d5003576ca7"
  },
  "testnet-account": {
    "address": "YOUR GENERATED ADDRESS",
    "key": {
      "type": "hex",
      "index": 0,
      "signatureAlgorithm": "ECDSA_P256",
      "hashAlgorithm": "SHA3_256",
      "privateKey": "YOUR PRIVATE KEY"
    }
  }
},
"deployments": {
  "emulator": {
    "emulator-account": [
      "HelloWorld"
    ]
  },
  "testnet": {
    "testnet-account": [
      "HelloWorld"
    ]
  }
}
```

๐ Deploy your HelloWorld smart contract:

```sh
flow project deploy --network=testnet
```

---

# โ๏ธ Side Quests

> ๐ Head to your next challenge [here](https://github.com/emerald-dao/1-simple-nft).

> ๐ฌ Meet other builders working on this challenge and get help in the [๐ Emerald City Discord](https://discord.gg/emeraldcity)!

> ๐ Problems, questions, comments on the stack? Post them to the [๐ Emerald City Discord](https://discord.gg/emeraldcity).
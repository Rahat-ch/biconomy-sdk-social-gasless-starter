
# Biconomy SDK Social Login + Gasless Transactions

This is a starter kit that implements the Biconomy SDK into a basic React application built with Vite. This Kit comes with everything you need for social login and for making gasless transactions to a contract with the Biconomy SDK. 


## Installation

Navigate to this directory in your terminal and then 

```bash
  cd smartContract
```

You can use npm to install but for these instructions I will be using yarn. It will work the same way with npm or pnpm. 

```bash
  yarn
```

Once dependencies are installed run the following command: 

```bash
  cp .env.example .env;
```

You will need to update the newly created .env file with your wallet's PRIVATE_KEY. Make sure to get API keys from [Etherscan](https://etherscan.io/) or [PolygonScan](https://polygonscan.com/). Create an account to get your API keys, these are free. 

Run the command below to deploy your contract to the Polygon Mumbai Network. Make sure the wallet you got your private key from has a small amount of test matic for deployment. You can get test matic [here](https://faucet.polygon.technology/).

```bash
  npx hardhat run scripts/deploy.ts --network mumbai
```

Once deployed copy the contract address on the terminal and run the command below: 

```bash
  npx hardhat verify --network mumbai <your-contract-address>
```

This will verify your contract on Polygonscan and give you a link to your code on Polygonscan!

## Biconomy Dashboard Registration

Now head over to the [Biconomy SDK Dashboard](https://dashboard-beta.biconomy.io/)

Sign in With Github then register a new dApp. I have some registred dApps already but you might not. 

![Register new dApp](https://bafybeie46e6x5hgmjjirsb5ixapuyi4jscalrtqvjzrmnn6ub64ocism7e.ipfs.w3s.link/Screen%20Shot%202023-04-03%20at%2011.02.14%20AM.png)

Name your dApp and choose a chain, in this case we deployed to Polygon Mumbai so let's choose this one. 

![Register new dApp part 2](https://bafybeieeefki3t3jtybm336nctubdd4gcaxkw5dn4ykt3tkl3urouekrqy.ipfs.w3s.link/Screen%20Shot%202023-04-03%20at%2011.22.31%20AM.png)


You'll see this message on the top right let's click set up gas tank to set up the funds needed to cover users gas costs!

![Register new dApp part 2](https://bafybeifgyakcoem37t7f355rpa3pbjwdvwga2pv6bzceznmg5b6oxmdiga.ipfs.w3s.link/Screen%20Shot%202023-04-03%20at%2011.28.13%20AM.png)

From here its fairly simple, agree to the terms and sign with the your wallet. Its important to note that if you want to withdraw the funds at any point then you will need to make sure that you use the same wallet you sign with at this step. 

Deposit the funds you would like to start with and take note of your api key for later. 

Finally we'll need to authorize the contract we just deployed. 

Head back to the dApp page and click Smart Contracts and then Add Smart Contract. You can add the name of your contract and the address here. Because we verified it the ABI will be automatically fetched. If you do not verify your contract you can also manually paste your ABI here as well. Make sure to select the write method that you would like to authorize for gasless transactions. In this case we just have an incrementCount method. 


![Register new dApp part 3](https://bafybeihrdt7snhnkhffz4slqgcn2u5e65weeyu22kkbio7dmlizhlmrkvq.ipfs.w3s.link/Screen%20Shot%202023-04-03%20at%2011.44.48%20AM.png)

Copy your API key and you will now be all set!

## Frontend Configuration

In your terminal navigate to the root folder of the project and install dependencies and configure the frontend variables as we did for the contract folder. 

```bash
  yarn
```

```bash
  cp .env.example .env;
```

Add your Biconomy API Key and your contract address in the .env file, and use the dev script to run: 

```bash
  yarn dev
```

You should now be all set to try out the starter kit and begin making changes for your own project! 


## Pull requests welcome

Have any improvements to be made? Feel free to make a Pull Request! 

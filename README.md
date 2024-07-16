# Diamante Dex functions

This project demonstrates how to create, distribute, and swap assets on the Diamante blockchain using the `diamante-sdk-js` library.

## Prerequisites

- Node.js installed on your machine.
- Yarn package management.
- An IDE or text editor of your choice.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/diamcircle/diamante-defi-operation-js.git

```

2. Navigate to the project directory:

```bash
cd diamante-defi-operation-js
```

3. Install the dependencies:

```bash
yarn
```

## Configuration

1. Create and fund keypairs with friendbot.
2. Replace the placeholders for the secret keys of your issuer, distributor, and external accounts with actual secret keys:

```js
const issuerKP = Keypair.fromSecret("SECRET_KEY");
const distributorKP = Keypair.fromSecret("SECRET_KEY");
const externalKP = Keypair.fromSecret("SECRET_KEY");
```

## Usage

Run the main script to execute the series of transactions:

```bash
node index.js
```

## Script Description

The script performs the following tasks:

**Create and Distribute Assets:**

- Creates three assets (`ASSET1`, `ASSET2`, `ASSET3`) issued by the `issuerKP` account.
- The `distributorKP` account trusts these assets.
- The issuer sends these assets to the distributor.

**Create Liquidity:**

- The `distributorKP` account creates sell offers for the assets, providing liquidity.

**Swap Diams to an Asset:**

- The `externalKP` account trusts and swaps native currency (Diam) for `ASSET3`.

**Swap Assets Using the Best Path:**

- The `externalKP` account swaps `ASSET3` to `ASSET1` using the best available path.

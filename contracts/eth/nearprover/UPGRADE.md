# Upgradability

This file describes how to upgrade the bridge address in NearProver contract.

## Configuration

1. Create `.env` file inside `eth-custodian` directory: `$ touch .env`.

2. Add to the file your Alchemy API key:
`$ echo "ALCHEMY_API_KEY=YOUR_ALCHEMY_API_KEY_HERE" >> .env` <br/>
RPC access can be easily gained from [Alchemy](https://www.alchemyapi.io/).

3. Add to the file Ropsten Private key:
`$ echo "ROPSTEN_PRIVATE_KEY=YOUR_ROPSTEN_PRIVATE_KEY_HERE" >> .env`

## Mock deployment

In order to have some testing prover contract instance for the testing, it could be useful to deploy some prover
instance to try upgradability.
To deploy the prover with the mock run: <br/>
`$ make deploy-prover-with-mock-bridge`

## Upgrade

1. First, you can fetch the current bridge address from the prover by running:<br/>
`$ make get-provers-bridge-address PROVER=<PROVER_ADDRESS_HERE>`

2. Upgrade the bridge address for the provided prover:<br/>
`$ make upgrade-provers-bridge-address-to PROVER=<PROVER_ADDRESS_HERE> NEW_BRIDGE=<BRIDGE_ADDRESS_HERE>`

3. Repeat the item 1 to ensure the Prover was updated with the new bridge address.




# Stage 0 Requirements

You must complete tasks 11 (publish an app) and 13 (deploy an app) during Stage 0 to be eligible for the Validator/Service Provider role in Stage 1.
* See the [How to Publish a Webapp](/docs/publishing-webapps.md) page for reference: you will complete this workflow as part of Stage 0.

## Steps

* Set up the `testnet-laconicd` Stack Orchestrator stack.
  * [Instructions](https://git.vdb.to/cerc-io/testnet-laconicd-stack/src/branch/main/stack-orchestrator/stacks/testnet-laconicd/README.md)
* Recover your account key using your the wallet mnemonic you obtained through the wallet app.
  * `laconic-so deployment --dir testnet-laconicd-deployment exec laconicd "laconicd keys add <key-name> --recover"`
* Set up `laconic-registry-cli` with your wallet's private key.
  * [Instructions](https://git.vdb.to/cerc-io/testnet-laconicd-stack/src/branch/main/stack-orchestrator/stacks/testnet-laconicd/README.md#perform-operations)
* Create a bond.
  * [Instructions](/docs/instructions.md#create-a-bond)
* Register an authority
  * [Instructions](/docs/instructions.md#register-an-authority)
* Set up Service Provider Infrastructure
  * Use the bond ID and authority created in the previous steps.
  * [Instructions](/docs/service-provider-setup.md)
* Publish an app
  * [Instructions](/docs/service-provider-setup.md#deploy-a-test-webapp)
  * Modify the following variables in the `.env` file before requesting the deployment:
    * Set `CERC_TEST_WEBAPP_CONFIG1` to your account pubkey (`0x...` from the wallet app)
    * Set `CERC_TEST_WEBAPP_CONFIG2` to your account pubkey (`laconic...` from the wallet app)
* Verify the deployment using the URL listed in the [deployer UI](/docs/service-provider-setup.md#deploy-frontend).

## Stage 0 Chain Details

* Chain ID: `laconic_9000-1`
* RPC endpoint: `https://laconicd.laconic.com`
* GraphQL endpoint: `https://laconicd.laconic.com/api`

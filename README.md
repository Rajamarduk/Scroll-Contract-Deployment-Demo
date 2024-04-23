# Scroll-Contract-Deployment-Demo
This project showcases the deployment of a contract on Scroll's rollup network, utilizing either Hardhat or Foundry. 
### Prerequisites

Before proceeding, ensure that you have set up your network as per the instructions outlined in the [Scroll user guide](https://guide.scroll.io/user-guide/setup).

### Deploy with Hardhat

If you haven't already, install Node.js and Yarn.

1. Run `yarn install` to install dependencies.
2. Create a `.env` file following the example `.env.example` in the root directory. Replace `PRIVATE_KEY` with your account's private key.
3. Compile the contract using `yarn compile`.
4. Deploy the contract on the Scroll Alpha Testnet using `yarn deploy:scrollTestnet`.
5. Run `yarn test` for Hardhat tests.

### Deploy with Foundry

To deploy using Foundry:

1. Install Foundry:

    ```bash
    curl -L https://foundry.paradigm.xyz | bash
    foundryup
    ```

2. Build the project using `forge build`.
3. Deploy the contract using the following command:

    ```bash
    forge create --rpc-url https://alpha-rpc.scroll.io/l2 \
      --value <lock_amount> \
      --constructor-args <unlock_time> \
      --private-key <your_private_key> \
      --legacy \
      contracts/Lock.sol:Lock
    ```

    Replace `<lock_amount>` with the amount of ETH to be locked in the contract and `<unlock_time>` with the Unix timestamp after which the locked funds will be available for withdrawal.

    Example:

    ```bash
    forge create --rpc-url https://alpha-rpc.scroll.io/l2 \
      --value 0.00000000002ether \
      --constructor-args 1696118400 \
      --private-key 0xabc123abc123abc123abc123abc123abc123abc123abc123abc123abc123abc1 \
      --legacy \
      contracts/Lock.sol:Lock
    ```

### Support

For further assistance, join our [Discord](https://scroll.io/).

---

This rewritten version aims to provide a clearer and more concise overview of the project and its deployment processes.

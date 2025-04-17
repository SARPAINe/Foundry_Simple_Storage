# 🛠 Foundry Guidelines

This guide contains essential commands and instructions to quickly get started with Foundry and perform common actions like creating projects and deploying smart contracts.

---

## 📁 Create a New Project in Foundry

To initialize a new Foundry project in your current working directory:

```bash
forge init
```

This sets up the basic structure with default directories and files like `src/`, `test/`, and `foundry.toml`.

---

## 🏗 Compile and Build Contracts

```bash
forge build
```

## Clean and recompile

```bash
forge clean
forge build
```

Useful flags:

- `--force`: Forces a rebuild even if no changes were detected.
- `--sizes`: Shows contract size information after build.

---

## 🚀 Deploy a Contract to Local Anvil

Make sure Anvil is running locally on `http://127.0.0.1:8545`. Then use the following command to create and deploy a contract directly:

```bash
forge create SimpleStorage \
  --rpc-url http://127.0.0.1:8545 \
  --private-key your_private_key_starting_with_0x
```

Replace `SimpleStorage` with the path to your contract if it's in a subdirectory like `src/`.

---

## 🧾 Deploy a Contract Using a Script

Foundry lets you deploy contracts using scripts for more complex or customizable deployments. Run:

```bash
forge script script/DeploySimpleStorage.s.sol \
  --rpc-url http://127.0.0.1:8545 \
  --broadcast \
  --private-key your_private_key_starting_with_0x
```

Ensure your script is written using the `Script` contract and contains a `run()` function. If you don't provide broadcast then it will just be a dry run which will be saved inside of broadcast folder

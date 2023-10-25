# Subquery Sandbox Project

This repository is designed to set up a Subquery project for Stellar and Soroban networks. SubQuery is an open-source data indexer offering fast, flexible, and reliable custom APIs for web3 projects across various supported chains.

This project includes code for running and configuring a Subquery project to store data from specific contracts. Additionally, it incorporates Docker-based scripts to eliminate dependency on the host machine's configurations such as Node or Docker versions, and also avoids the need for a global Subql installation.

## Getting Started Locally

### Running Docker Container

Execute the following script to enter a bash shell inside the Docker container running Node:

```bash
bash run.sh
```

### Installing Docker Inside Container

After entering the bash shell, install Docker using the script:

```bash
bash install_docker.sh
```

### Setting Up Subql

To set up Subql, run:

```bash
bash setup_subquery.sh
```

### Initialize Project

Navigate to the `subql-starter` directory and follow these steps:

1. Install dependencies:

   ```bash
   yarn
   ```

2. Run Docker daemon:

   ```bash
   dockerd &
   ```

3. Open another terminal and connect to Docker:

   ```bash
   bash connect.sh
   ```

4. Change to `subql-starter` directory:

   ```bash
   cd subql-starter
   ```

5. Build types:

   ```bash
   yarn codegen
   ```

6. Build project:

   ```bash
   yarn build
   ```

7. Initialize project:

   ```bash
   yarn start:docker
   ```

## Publish to IPFS

To publish your project to IPFS, execute:

```bash
cd subql-starter
subql publish
```

## Configuration Settings

Configuration changes are generally made in the `subql-starter/project.ts` file.

- **Endpoints**: Can be modified under the `network` key.
  
- **Contracts & Data Sources**: Can be modified under the `dataSources` key.

## Notes

If you execute `bash run.sh`, the container will start from scratch, requiring you to reinstall Docker. To avoid this, you can use:

```bash
bash start.sh
```

This will restart the container with previously installed Node and Docker configurations.

## Additional Information

Deployed IPFS address: `QmdRo3aSaYuwdevWJa6Ltev3aKovwTHEyjYnkBqMXsAQbK`
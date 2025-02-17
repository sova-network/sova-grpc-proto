This repository contains the gRPC proto files for Sova, a custom implementation of MEV (Maximal Extractable Value) infrastructure on the TON blockchain. These proto files define the services, messages, and methods used for communication between various Sova components, such as the Block Engine, Validators, Searchers, and other integrated services.

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Generating Code](#generating-code)
- [Proto Files](#proto-files)
- [Contributing](#contributing)
- [License](#license)

## Overview

Sova is a specialized fork of the TON blockchain client with customizations to support MEV functionality. It allows Searchers to submit bundles of transactions to a Block Engine, which then emulates, auctions, and orders these bundles for inclusion in blocks by Validators.

This repository hosts the gRPC proto files used to define the communication interfaces between different components in the Sova ecosystem.

## Getting Started

### Prerequisites

Before you can generate code from these proto files, ensure you have the following tools installed:

- [Protocol Buffers Compiler (protoc)](https://grpc.io/docs/protoc-installation/)
- gRPC plugin for your target language (e.g., `grpc_python_plugin` for Python, `grpc_cpp_plugin` for C++, etc.)
- Your preferred language-specific package manager (e.g., `pip`, `npm`, `cargo`, etc.)

### Installation

Clone the repository to your local machine:

```bash
git clone https://github.com/sova-network/sova-grpc-proto.git
cd sova-grpc-proto
```

### Generating Code
To generate gRPC code from the proto files, run the following command for your specific language:

```bash
protoc --proto_path=proto/ --<lang_out>=<output_directory> --grpc_out=<output_directory> proto/*.proto
```
Replace <lang_out> with the appropriate option for your language (e.g., python_out for Python), and <output_directory> with the directory where you want the generated code to be placed.

Example for Python:

```bash
protoc --proto_path=proto/ --python_out=./generated --grpc_out=./generated proto/*.proto
```

## Proto Files
The proto files are located in the proto/ directory and include definitions for:

* block_engine.proto: Interfaces for communication between Validators and the Sova Block Engine.
* searcher.proto: Interfaces for communication between Searchers and the Sova Block Engine.
* auth.proto: Interfaces for Validators to authenticate themselves or for Searchers to raise the limits.

Each proto file contains detailed comments describing the purpose and structure of the services and messages defined.

## Contributing
We welcome contributions to this project! If you'd like to contribute, please follow these steps:

Fork the repository.
1. Create a new branch (git checkout -b feature/your-feature).
2. Make your changes.
3. Commit your changes (git commit -am 'Add your feature').
4. Push to the branch (git push origin feature/your-feature).
5. Create a new Pull Request.
Please ensure your code adheres to the existing style and that all tests pass.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
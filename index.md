---
title: Getting Started
layout: home
nav_order: 1
---

# Getting Started

To get started with the Access and Transfer components, follow the steps below:

## 1. Contact PhysiKey for Access

Before you can use these components, you'll need to contact PhysiKey to gain access to their services. PhysiKey will provide you with access to the necessary resources, including the node module, which you can integrate into your React Native application.

## 2. Necessary Configuration for Transfer Component

To use the Transfer component, ensure that you access to the necessary configurations:
- **Pimlico endpoint**: Your own Pimlico API endpoint.
- **Token contract address**: The address of the token contract (e.g., USDC).
- **RPC URL**: A valid RPC URL for the Ethereum network (or another supported blockchain network).

These details must be supplied for the Transfer component to function correctly.

## 3. Install the PhysiKey Node Module

Once you have access to the PhysiKey services, you can install the required node module. To install it, run the following command in your project:

npm:
````bash
npm install physikeyRN
````

yarn:
````bash
yarn add physikeyRN
````

## 3. Import Components
After installation, you can begin using the `Access` and `Transfer` components in your React Native project.

### Access Component:
````tsx
import { Access } from "physikeyRN";
````

### Transfer Component:
````tsx
import { Transfer } from "physikeyRN";
````

For detailed usage instructions and examples, check out the full documentation for each component:
- [Access Component Documentation](/access.html)
- [Transfer Component Documentation](/transfer.html)

---


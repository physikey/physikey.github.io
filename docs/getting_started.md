---
title: Getting Started
layout: default
nav_order: 2
---

# Getting Started

Follow these steps to integrate PhysiKey into your React Native application.

## 1. Request Access

To use PhysiKey services, [see the guide](sdk_configuration) to gain access. Once approved you'll receive the necessary resources, including the node module, for integration.

## 2. Configure NFC Support

Ensure your app is set up for **NFC functionality** before using PhysiKey cards. See the [NFC Configuration Guide](nfc_configuration) to enable NFC in your build settings.

## 3. Set Up Accept Component  

Before using the **Accept** component, acquire the required parameters:  
- **Pimlico endpoint**: Your Pimlico API URL.  
- **Token contract**: The ERC-20 token address (e.g., USDC).  
- **RPC URL**: A valid blockchain RPC endpoint.  

## 4. Install the PhysiKey Module

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
After installation, you can begin using the `Issuance` and `Accept` components in your React Native project.

### Issuance Component:
````tsx
import { Issuance } from "physikeyRN";
````

### Accept Component:
````tsx
import { Accept } from "physikeyRN";
````

For detailed usage instructions and examples, check out the full documentation for each component:
- [Issuance Component Documentation](/access.html)
- [Accept Component Documentation](/transfer.html)

---

🚀🚀🚀
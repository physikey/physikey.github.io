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

## 3. Install the PhysiKey Module

Once you have access to the PhysiKey services, you can install the required node module. To install it, run the following command in your project:

npm:
````bash
npm install physikey-rn
````

yarn:
````bash
yarn add physikey-rn
````

## 4. Import Component
After installation, you can begin using the `Sign` component in your React Native project.

### Basic Usage:
````tsx
import React, { useState } from 'react';
import { View, Button } from 'react-native';
import { Sign } from 'physikey-rn';

function App(): React.JSX.Element {
  const [signModal, setSignModal] = useState(false);
  const [transactionData, setTransactionData] = useState<any>(null); // State for storing transaction data

  // Sample transaction data (you would replace this with actual data)
  const exampleTransactionData = {
    to: "0xRecipientAddressHere", 
    value: Web3.utils.toWei("0.01", "ether"), 
    gas: 21000, 
    gasPrice: Web3.utils.toWei("10", "gwei"), 
    nonce: 0, 
    chainId: 1, 
  }

  const openSign = (data) => {
    // Set the transaction data and open the modal
    setTransactionData(data);
    setSignModal(true);
  };

  const closeSign = () => {
    setSignModal(false);
  };

  return (
    <View style={styles.container}>
      <Button onPress={() => { openSign(exampleTransactionData); }}>Sign With PhysiKey</Button>
      <Sign
        rpcURL="https://sepolia.base.org" // Any EVM compatable chain
        transactionData={transactionData}
        accountType="EOA" // choose EOA or SSA
        visible={signModal}
        closeSignModal={closeSign}
      />
    </View>

  );
};
export default App;
````

---

For detailed usage instructions and examples, check out the full documentation for each component:
- [Sign Component Documentation](/sign.html)




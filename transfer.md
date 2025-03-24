---
title: Transfer
layout: default
nav_order: 3
---

# Transfer Component

The **Transfer** component facilitates the transfer of **tokens** by using **PhysiKey cards** to sign crypto transactions. It provides a step by step process for securely handling recipient details, amount input, NFC scanning, password validation, and transaction execution.

This component is displayed as a modal, allowing users to complete the transfer process without leaving the current screen. Its visibility is controlled by state.

## Props
- `color` (string, optional): A hex value that determines the theme color of the component. It allows you to customize the color of buttons to match your theme.
- `pimlicoUrl` (string): The URL of the Pimlico Paymaster service. It is used for sponsoring the transaction.
- `rpcUrl` (string): The URL of the RPC endpoint used to interact with the blockchain network.
- `tokenContract` (string): The address of the ERC-20 token contract that will be used for the transfer.
- `visible` (boolean): Determines if the transfer component is visible or not. It controls the modal's visibility on the screen.
- `closeTransfer` (function): A function to close the transfer modal. This is typically tied to the state change for `visible`.

---

## Usage

### 1. Import 
To use the **Transfer** component, import it into your React component:

````tsx
import { Transfer } from "physikeyRN"
````

### 2. Implement 
Use the modal inside your component and control its visibility with state:

````tsx
const [isVisible, setIsVisible] = useState(false);

return (
  <>
    <Button title="Transfer" onPress={() => setIsVisible(true)} />
    <TransferModal 
        color="#4A90E2"  // (Optional) Custom theme color 
        pimlicoUrl="https://example.com/pimlico"  // Pimlico Paymaster URL
        rpcUrl="https://example.com/rpc"  // RPC URL
        tokenContract="0xYourTokenContractAddress"  // Token contract address
        visible={isVisible} 
        closeTransfer={() => setIsVisible(false)} 
    />
  </>
);
````

### Important Considerations
For transaction execution, we use Permissionless and Pimlico to handle client and paymaster initialization. To ensure the transfer component functions correctly, you will need to provide the following:
- Pimlico endpoint: Your own Pimlico API endpoint.
- Token contract address: The address of the token contract (e.g., USDC).
- RPC URL: A valid RPC URL for the Ethereum network (or another supported blockchain network).

These details must be supplied to the transfer component for it to work properly.
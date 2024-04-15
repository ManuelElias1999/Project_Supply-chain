# Supply Chain Smart Contract with Payments

This Solidity smart contract models a supply chain with payment capabilities. It allows for ETH payments to be held until released by the user for immediate payment to another party involved in the supply chain.

## Description

The `SupplyChain` contract manages the steps of a supply chain, each associated with a product. It supports registering products and updating their status with metadata and associated payments.

## Contract Details

- **Struct Step**: Represents a step in the supply chain, including status, metadata, price, and author.
- **Enum Status**: Defines the possible statuses of a step in the supply chain.
- **Events**: Emits an event `RegisteredStep` when a step is registered.
- **Mappings**: Maps product IDs to arrays of steps.

## Core Features

- **Product Registration**: Allows users to register products in the supply chain.
- **Step Registration**: Enables users to register steps in the supply chain with associated metadata and payments.
- **Payment Handling**: Holds ETH payments until release by the user and ensures immediate payment to another party when updating the status of a product.

## Usage

1. **Product Registration**: Call the `registerProduct` function to register a new product in the supply chain.
2. **Step Registration**: Call the `registerStep` function to register a new step in the supply chain, providing metadata and an optional payment.
3. **Payment Release**: When updating the status of a product, ensure that the required payment is sent to the appropriate party before proceeding.

### Example Usage

```solidity
// Register a new product
supplyChain.registerProduct(productId);

// Register a new step in the supply chain with metadata and payment
supplyChain.registerStep(productId, "Ready for pick-up", 0.1 ether);

// Update the status of a product and release payment to the appropriate party
supplyChain.registerStep(productId, "Picked up", 0.05 ether);

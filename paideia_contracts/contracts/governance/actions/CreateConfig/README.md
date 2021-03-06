# Action Type: Create Config

This action is used to create a new config that is to be governed by the DAO, including initial register values.

---

## Contract: Action Create Config Proxy

The user defines here what the create config action needs to look like.

### Assets

| Token Name | Amount |
| --- | --- |

### Registers

| Register | Type | Index | Description |
| --- | --- | --- | --- |
| R4 | Coll[Long] | 0 | Option index - the option of the proposal which needs to pass for this action to execute |
| | | 1-6 | Data type for registers ([See data type list](../../DataTypes.md)) |
| R5-R9 | Any | - | - |

### Transactions

- [Create Proposal Proxy](../../README.md#transaction-create-proposal-proxy)
- [Create Proposal](../../README.md#transaction-create-proposal)

---

## Contract: Action Create Config

This contract ensures the new config box is filled out with the correct values.

### Assets

Of course the first token needs to be a valid Action token

| Token Name | Amount |
| --- | --- |
| Action | 1 |

### Registers

| Register | Type | Index | Description |
| --- | --- | --- | --- |
| R4 | Coll[Long] | 0 | Proposal index - the proposal this action relates to |
| | | 1 | Option index - the option of the proposal which needs to pass for this action to execute |
| | | 2-7 | Data type for registers ([See data type list](../../DataTypes.md)) |
| R5-R9 | Any | - | - |

### Transactions

- [Create Proposal](../../README.md#transaction-create-proposal)
- [Create Config](#transaction-create-config)

---

## Transaction: Create Config

A config box is created with the registers filled out correctly.

### Data-Inputs

1. [Proposal](../../README.md#contract-proposal)
2. [DAO Config](../../SpecialConfigs.md#dao-config)

### Inputs

1. [DAO](../../README.md#contract-dao)
2. [Action Create Config](#contract-action-create-config)

### Outputs

1. [DAO](../../README.md#contract-dao)
2. [Config](../../README.md#contract-dao-config)
   
---
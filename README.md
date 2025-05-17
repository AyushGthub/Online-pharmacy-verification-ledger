# Online Pharmacy Verification Ledger

This is a simple Aptos Move smart contract that acts as a decentralized ledger to register and verify online pharmacies.

## Overview

The smart contract allows:
- **Registration of a verified pharmacy** by an admin.
- **Public verification** to check if a given address belongs to a registered pharmacy.

## Module Name

```
MyModule::PharmacyLedger
```

## Functions

### `register_pharmacy(admin: &signer, name: string::String, license_id: string::String)`

Registers a new verified pharmacy with a name and license ID. The signer (admin) becomes the owner of the record.
"transaction_hash": "0xcc8f3daea5013abb80df8409bb1e3dc10ef6232283ba37f0c297def35a7b162b"

# Pledge Dev Plan

### 1. Minimal ERC20 Setup
Build `MockERC20`, 'DebtToken' and simple mint/burn permissions.

### 2. Pool Creation
Create `PledgePoolV1` with `PoolState`, `PoolBaseInfo`, `PoolDataInfo`, `createPool`, `poolLength`, `getPoolState`.

### 3. Lender Deposit Flow
Add `depositLend`. Track `userLendInfo`, `lendSupply`, max supply, min amount, ERC20 transfer.
ToDo: How it works in real world project? Let's say lender deposits USDT.

### 4. Borrower Collateral Flow
Add `depositBorrow`. Track `userBorrowInfo`, `borrowSupply`.

### 5. Oracle + Settlement
Add mock oracle and `settle` math.

### 6. Refunds
Add `refundLend` and `refundBorrow`. Users recover unmatched funds after settlement.

### 7. Claim SP / JP Tokens
Add `claimLend` and `claimBorrow`. 
Lenders receive SP (senior/supply pool) tokens. 
Borrowers receive JP (junior poll) tokens and match lendToken loan.

### 8. Repay Flow
Add interest calculation and repay lenders with DEX Swap.

### 9. Liquidation Flow
Add `checkoutLiquidate`. Then add `liquidate`.

### 10. Admin / Multisig Last
First use `Ownable`. After business logic is clear, replace admin with a safer multisig design keyed by:
```
caller + target + function selector + calldata hash + nonce
```


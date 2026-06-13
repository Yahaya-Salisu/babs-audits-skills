## Write a Foundry PoC that demonstrates the confirmed impact.

### WORKFLOW:
1. Inspect existing test files for setUp(), helpers, fixtures, token setup
2. Reuse everything reusable - write only new attack code
3. Keep it short, readable, and direct with no much comments and avoid using bullet dashes at all.

### OUTPUT:
- Full `.t.sol` file
- Exact command to run it

**Before finalizing, verify:**
- Assertion measures the actual bug, not a weaker proxy
- Test fails if bug is fixed
- Attack amount is 30-60% of available liquidity unless finding requires otherwise
- One-two console.log to demonstrate the impact.
# Uranium Finance — Pair Swap Constant Product Error PoC

> **Educational Purpose Only** — This PoC is created for security research and education
> purposes only. It is a simplified simulation, not a fork replay against mainnet.

**Date:** 2021-04-28 | **Loss:** $50M | **Chain:** BSC

## Quick Start
```bash
git clone https://github.com/NomosLabs-Security/poc-uranium-finance-2021
cd poc-uranium-finance-2021
forge install foundry-rs/forge-std --no-git
forge test -vvvv
```

## Vulnerability
During V2.1 migration, the fee precision constant was updated from 1000 to 10000 in the fee calculation but NOT in the K-value invariant check. This 10x mismatch meant the swap function accepted trades that violated the constant product formula.

## Key Contracts
- `src/Exploit.sol` — Vulnerable pair with mismatched constants
- `test/Exploit.t.sol` — Foundry test demonstrating the exploit

## License

MIT — For educational use only.

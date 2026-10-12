# clone-lin-opgeth-ecotone

LIN clone of op-geth `newL1CostFuncEcotone` / Isthmus–Jovian operator fee (tag `v1.101702.3`, LGPL-3.0).

This repository holds **only the LIN kernel**. Auditable proofs live in [kbelludoo/lin-open](https://github.com/kbelludoo/lin-open):

- kernel (also mirrored): `src/lin_opgeth_ecotone.lin`
- harness: `test/prove_opgeth_ecotone_external.py`
- evidence: `examples/opgeth_ecotone/`
- event: `docs/events/EVENT_OPGETH_ECOTONE_CLONE_LIN.rulel`

Class: **EXPERIMENTAL** (real Ecotone/Isthmus/Jovian addends, i64-scale + 128-bit product). Not an op-geth node. Not uint256 / Base mainnet parity.

Commercial hook (honest): a wallet that still prices Base/OP txs with Bedrock (calldata-only) undercharges after Ecotone because `blobBaseFee*blobScalar` is a first-class term (official emptyTx: 960900 vs 960000, **+900 wei**). A wallet that keeps Isthmus operator (`gas*scalar/1e6`) after Jovian undercharges the variable term by **1e8×**.

Upstream: [ethereum-optimism/op-geth](https://github.com/ethereum-optimism/op-geth) commit `7da4560d1fb3045286b70a8dc23360d2626543f2`
`core/types/rollup_cost.go` blob `3266ae13faaabf599feb4417d60893a11b908fb3` sha256 `35a4e1976fca49cb5f328c6bf3f1513458eda450c9e7425c24a78a8750c51dec`

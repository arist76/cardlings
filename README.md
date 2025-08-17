# Cardlings 🦀 Lings for Cardano

**Cardlings is a collection of small, interactive exercises designed to teach you how to build on the Cardano blockchain. Inspired by the highly successful `rustlings` project, Cardlings guides you from foundational concepts to practical application in a hands-on, command-line environment.**

-----

## 📖 Table of Contents

  - [Why Cardlings?](#why-cardlings)
  - [Getting Started](#getting-started)
  - [How to Use](#how-to-use-wip)
  - [Curriculum](#curriculum)
  - [Contributing](#contributing)
  - [Community](#community)
  - [License](#license)

## 🤔 Why Cardlings?

The Cardano ecosystem is powerful, but for new developers, the learning curve can be steep. Resources are often scattered, and bridging the gap between reading theory and writing functional code is a major hurdle.

Cardlings solves this by providing a single, linear path to learn Cardano development. By fixing small, real-world exercises, you build muscle memory and confidence, learning by *doing* rather than just reading.

## 🚀 Getting Started

Coming Soon

## 💻 How to Use (WIP)

The workflow is simple and designed to keep you in your favorite code editor.

1.  **Start the Watcher:**
    Navigate to the project directory and run the `watch` command. This will immediately try to verify your first exercise.

    ```bash
    cardlings watch
    ```

2.  **Solve the Exercises:**
    The watcher will guide you. It will point you to the first unsolved exercise (e.g., `exercises/01_introduction.rs`). Open the file in your code editor.

3.  **Follow the Instructions:**
    Each exercise file contains instructions in the comments. Your task is to modify the code to satisfy the requirements. Once you save the file, `cardlings watch` will automatically re-run the verification process in your terminal.

4.  **Advance to the Next Exercise:**
    If your solution is correct, you'll get a success message, and the watcher will point you to the next exercise. If not, you'll get a helpful error message to guide you.

### Other Commands (WIP)

  * `cardlings list`: View all available exercises and your current progress.
  * `cardlings run <exercise>`: Run verification for a single, specific exercise.

## 📚 Curriculum

Cardlings is structured into several modules that build upon each other. The planned curriculum includes:

1.  **Blockchain Basics:** Keys, addresses, and understanding UTXOs.
2.  **Building Transactions:** Crafting, signing, and submitting simple transactions.
3.  **Native Tokens:** Minting and managing Cardano's native assets.
4.  **Smart Contract Interactions:** Interacting with existing Plutus scripts on-chain.

### Exercises
## 

### 00 — Welcome & tooling (4)

- **00-01 Welcome check:** run the CLI, confirm Docker and binaries.
- **00-02 Watch mode:** fix a trivial failing test to learn the flow. (Hotkeys demo.)
- **00-03 Devnet boot:** learner toggles a flag in YAML to make watcher boot the node; test checks node tip increases.
- **00-04 Read the logs:** fill a shell pipeline to grep node readiness.

#### 01 — Blockchain basics for developers (6)

Concepts via hands-on mini checks (no essays).

- **01-01 UTXO vs accounts (code quiz):** complete true/false constants; tests assert knowledge of “spent once as a whole” property.
- **01-02 Transactions anatomy:** fill fields in a JSON stub; tests parse and validate.
- **01-03 Keys & addresses:** short CLI edits to generate keys/address (variables blank).
- **01-04 Fees & change:** fix a calculation in a small Haskell helper.
- **01-05 Datums/redeemers overview (code quiz).**
- **01-06 Confirm via CLI:** edit a command to query UTxO and parse count.

#### 02 — Cardano CLI basics (8)

- **02-01 Generate payment keys/address (CLI).**
- **02-02 Fund from faucet (devnet):** the test airdrops; learner edits `cardano-cli query utxo` line to verify balance.
- **02-03 Build raw tx:** fix missing `-tx-in`/`-tx-out` placeholders.
- **02-04 Calculate fee:** fill the fee calc step; tests confirm min fee.
- **02-05 Sign & submit:** correct network magic & socket path.
- **02-06 Multi-UTxO consolidation:** add multiple inputs.
- **02-07 Metadata:** attach simple JSON metadata.
- **02-08 Script-free timelock policy (intro).**

#### 03 — Thinking in eUTxO (6)

- **03-01 One-shot consumption:** Haskell test asserts “consume whole UTxO” rule.
- **03-02 Determinism & validation boundary (quiz).**
- **03-03 Splitting value & concurrency:** fix a function that splits change to parallelize.
- **03-04 Script address derivation (stub).**
- **03-05 Inline datum vs hash (fill blanks).**
- **03-06 Reference inputs concept check.**

#### 04 — Haskell primer for Plinth (8)

(Focused on the subset that’s relevant to on-chain code.)

- **04-01 Algebraic data types:** complete a small ADT and pattern-match.
- **04-02 `Maybe`/`Either` in validations:** replace `undefined`.
- **04-03 ByteString & newtypes:** implement safe constructors.
- **04-04 Fold & map in pure code (no IO).**
- **04-05 Typeclasses (`Eq`, `Ord`, `FromData` style mocking).**
- **04-06 Strictness & differences vs normal Haskell (quiz).**
- **04-07 Template Haskell avoidance & allowed extensions (quiz).**
- **04-08 Property-style test for a pure validator helper.**

#### 05 — Plinth prelude & compilation (7)

- **05-01 Importing Plinth Prelude:** fix imports and types.
- **05-02 Compiling to UPLC:** fill GHC plugin flags; watcher inspects compiled code.
- **05-03 Serialization to script CBOR:** complete encoder function.
- **05-04 Inspect compiled code (tool):** learner calls the CLI to dump IR.
- **05-05 Special functions (trace/unsafe constraints) quiz.**
- **05-06 Unit test a small on-chain function with golden UPLC.**
- **05-07 Cost model basics (quiz).** [Plutus Cardano Intersect MBO](https://plutus.cardano.intersectmbo.org/haddock/latest/?utm_source=chatgpt.com)

#### 06 — Validators: the basics (8)

- **06-01 Minimal spending validator skeleton:** replace `undefined` with `True` to pass trivial spend.
- **06-02 Parameterized validator:** implement parameter capturing.
- **06-03 Script context fields:** extract `txInfoValidRange` correctly.
- **06-04 Redeemer shapes (sum types).** [Plutus Cardano Intersect MBO](https://plutus.cardano.intersectmbo.org/docs/auction-smart-contract/on-chain-code?utm_source=chatgpt.com)
- **06-05 Datum decoding & safety:** write `fromBuiltinData` handling.
- **06-06 Compile & hash:** assert script hash equals expected.
- **06-07 Build & submit a script-locked output (CLI).**
- **06-08 Spend from script with correct redeemer.**

#### 07 — Datums & redeemers in depth (6)

- **07-01 Inline vs hashed datum (practical):** create both, compare size/cost.
- **07-02 Redeemer for simple state transition.**
- **07-03 Validator rejects stale datum version (negative test).**
- **07-04 Datum schema evolution pattern.**
- **07-05 Multiple inputs with mixed scripts.**
- **07-06 Collateral & failure semantics.**

#### 08 — Transaction building (off-chain Haskell) (7)

(Use `cardano-api` or minimal helper scripts to craft txs programmatically.)

- **08-01 Create tx with script input & reference input.**
- **08-02 Inline datum write.**
- **08-03 Attach reference script.**
- **08-04 Change address handling.**
- **08-05 Balancing & fee estimation loop.**
- **08-06 Submit & await confirmation.**
- **08-07 Query UTxO & pretty print ledger state snippet.**

#### 09 — Reference inputs & scripts (5)

- **09-01 Consume data via reference input.**
- **09-02 Use reference script to cut tx size.**
- **09-03 Compare costs (assert cheaper with reference).**
- **09-04 Failure mode when reference missing.**
- **09-05 Best-practice checklist (quiz).**

#### 10 — Native tokens & policies (CLI + Plinth) (8)

- **10-01 Script-free timelock policy (CLI).** [Cardano Docs](https://docs.cardano.org/developer-resources/native-tokens?utm_source=chatgpt.com)
- **10-02 Plinth minting policy (constant policy id).** [Cardano Developers](https://developers.cardano.org/docs/native-tokens/minting/?utm_source=chatgpt.com)[Cardano Ledger](https://cardano-ledger.readthedocs.io/en/latest/explanations/policies.html?utm_source=chatgpt.com)
- **10-03 Mint & burn lifecycle on devnet (CLI).** [Cardano Developers](https://developers.cardano.org/docs/native-tokens/minting/?utm_source=chatgpt.com)
- **10-04 Multi-asset outputs; unit tests assert asset quantities.**
- **10-05 Policy that restricts to signer key.**
- **10-06 Policy with deadline (slot range).**
- **10-07 Metadata and token registry format (quiz).**
- **10-08 Error handling & negative tests.**

#### 11 — Script context & costs (6)

- **11-01 Extract signatories from `TxInfo`.**
- **11-02 Validate time range properly.**
- **11-03 Costing: ensure ≤ budget; compare two variants.**
- **11-04 Bench an optimization (pattern match vs map).**
- **11-05 Golden cost reports.**
- **11-06 Common pitfalls (quiz).**

#### 12 — State machines (CEM) (6)

- **12-01 Encode states & inputs.**
- **12-02 Single-step transition validator.**
- **12-03 Locking rules enforce invariants.**
- **12-04 Multi-step flow (bid → close for auction).**
- **12-05 Safety properties (negative tests).**
- **12-06 Discussion of CEM & EUTxO formalism (quiz).** [Plutus Cardano Intersect MBO](https://plutus.cardano.intersectmbo.org/resources/eutxo-paper.pdf?utm_source=chatgpt.com)

#### 13 — Patterns library: auction, vesting, oracles (9)

- **13-01 English auction minimal validator.** [Plutus Cardano Intersect MBO](https://plutus.cardano.intersectmbo.org/docs/auction-smart-contract/on-chain-code?utm_source=chatgpt.com)
- **13-02 Anti-sniping via time bounds.**
- **13-03 Vesting with cliff & linear release.**
- **13-04 Oracle read via reference input.**
- **13-05 Escrow with cancel path.**
- **13-06 NFT-gated access.**
- **13-07 Multi-sig via signatories.**
- **13-08 Admin parameter update via datum versioning.**
- **13-09 Partial order books sketch (bonus).**

#### 14 — Testing & simulation (7)

- **14-01 Script evaluation without submit (dry-run).**
- **14-02 Golden vectors for datum/redeemer serialization.**
- **14-03 Property-style tests for invariants.**
- **14-04 CLI integration tests (bash).**
- **14-05 Mock chain vs devnet parity tests.**
- **14-06 Failure snapshot debugging.**
- **14-07 Trace logs parsing & assertions.**

#### 15 — Security & best practices (6)

- **15-01 Replay & double-spend considerations (quiz).**
- **15-02 Datum validation & unsafe deserialization pitfalls.**
- **15-03 Signature & signer checks.**
- **15-04 Time range misuse pitfalls.**
- **15-05 Policy lock-in mistakes.**
- **15-06 Cost-exhaustion & DoS angles.**

#### 16 — Capstone: a small DApp end-to-end (10)

(Uses everything: on-chain Plinth validator, off-chain builder, CLI submit, reference script.)

- **16-01 Define spec & roles.**
- **16-02 On-chain module skeleton.**
- **16-03 Off-chain tx builder.**
- **16-04 Reference inputs & inline datums.**
- **16-05 Mint a utility token for the app.**
- **16-06 Happy-path demo.**
- **16-07 Negative-path suite.**
- **16-08 Cost & size budget tuning.**
- **16-09 Readme + runbook.**
- **16-10 Publish artifacts (script CBOR, policy ID).**

*(This curriculum is under active development.)*

## 🤝 Contributing

This is a community-driven project, and contributions are highly welcome\! Whether you want to fix a typo, add a new exercise, or improve the CLI, your help is appreciated.

Please read our **[CONTRIBUTING.md](CONTRIBUTING.md)** file for guidelines on how to get started.

## 💬 Community

Join our community channels to ask questions, share your progress, and connect with other Cardano developers:

  * **Discord:** [Link to your Discord server]
  * **Telegram:** [Link to your Telegram group]

## 📜 License

This project is licensed under the **MIT License**.

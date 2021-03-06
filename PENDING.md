## PENDING

BREAKING CHANGES

* Gaia REST API (`gaiacli advanced rest-server`)

* Gaia CLI  (`gaiacli`)
  * [cli] [\#2728](https://github.com/cosmos/cosmos-sdk/pull/2728) Seperate `tx` and `query` subcommands by module
  * [cli] [\#2727](https://github.com/cosmos/cosmos-sdk/pull/2727) Fix unbonding command flow
  * [cli] [\#2786](https://github.com/cosmos/cosmos-sdk/pull/2786) Fix redelegation command flow
  * [cli] [\#2829](https://github.com/cosmos/cosmos-sdk/pull/2829) add-genesis-account command now validates state when adding accounts
  * [cli] [\#2804](https://github.com/cosmos/cosmos-sdk/issues/2804) Check whether key exists before passing it on to `tx create-validator`.

* Gaia

* SDK
  * [\#2752](https://github.com/cosmos/cosmos-sdk/pull/2752) Don't hardcode bondable denom.
  * [\#2019](https://github.com/cosmos/cosmos-sdk/issues/2019) Cap total number of signatures. Current per-transaction limit is 7, and if that is exceeded transaction is rejected.
  * [\#2801](https://github.com/cosmos/cosmos-sdk/pull/2801) Remove AppInit structure.

* Tendermint


FEATURES

* Gaia REST API (`gaiacli advanced rest-server`)
  * [gov] [\#2479](https://github.com/cosmos/cosmos-sdk/issues/2479) Added governance parameter
    query REST endpoints.

* Gaia CLI  (`gaiacli`)
  * [gov][cli] [\#2479](https://github.com/cosmos/cosmos-sdk/issues/2479) Added governance
    parameter query commands.
  * [stake][cli] [\#2027] Add CLI query command for getting all delegations to a specific validator.
  * [\#2840](https://github.com/cosmos/cosmos-sdk/pull/2840) Standardize CLI exports from modules

* Gaia
  * [app] \#2791 Support export at a specific height, with `gaiad export --height=HEIGHT`.
  * [x/gov] [#2479](https://github.com/cosmos/cosmos-sdk/issues/2479) Implemented querier
  for getting governance parameters.
  * [app] \#2663 - Runtime-assertable invariants
  * [app] \#2791 Support export at a specific height, with `gaiad export --height=HEIGHT`.

* SDK
    * [simulator] \#2682 MsgEditValidator now looks at the validator's max rate, thus it now succeeds a significant portion of the time

* Tendermint


IMPROVEMENTS

* Gaia REST API (`gaiacli advanced rest-server`)
  * [\#2836](https://github.com/cosmos/cosmos-sdk/pull/2836) Expose LCD router to allow users to register routes there.

* Gaia CLI  (`gaiacli`)
  * [\#2749](https://github.com/cosmos/cosmos-sdk/pull/2749) Add --chain-id flag to gaiad testnet

* Gaia
  - #2772 Update BaseApp to not persist state when the ante handler fails on DeliverTx.
  - #2773 Require moniker to be provided on `gaiad init`.
  - #2672 [Makefile] Updated for better Windows compatibility and ledger support logic, get_tools was rewritten as a cross-compatible Makefile.
  - [#110](https://github.com/tendermint/devops/issues/110) Updated CircleCI job to trigger website build when cosmos docs are updated.

* SDK
 - [x/mock/simulation] [\#2720] major cleanup, introduction of helper objects, reorganization
 - \#2821 Codespaces are now strings
 - [types] #2776 Improve safety of `Coin` and `Coins` types. Various functions
 and methods will panic when a negative amount is discovered.
 - #2815 Gas unit fields changed from `int64` to `uint64`.

* Tendermint
 - #2796 Update to go-amino 0.14.1


BUG FIXES

* Gaia REST API (`gaiacli advanced rest-server`)

* Gaia CLI  (`gaiacli`)

* Gaia
  * [\#2723] Use `cosmosvalcons` Bech32 prefix in `tendermint show-address`
  * [\#2742](https://github.com/cosmos/cosmos-sdk/issues/2742) Fix time format of TimeoutCommit override

* SDK

  - \#2733 [x/gov, x/mock/simulation] Fix governance simulation, update x/gov import/export
  - \#2854 [x/bank] Remove unused bank.MsgIssue, prevent possible panic

* Tendermint
  * [\#2797](https://github.com/tendermint/tendermint/pull/2797) AddressBook requires addresses to have IDs; Do not crap out immediately after sending pex addrs in seed mode

# @solana/rpc-transformers

## 5.0.1

### Patch Changes

- Updated dependencies []:
    - @solana/errors@5.0.1
    - @solana/functional@5.0.1
    - @solana/nominal-types@5.0.1
    - @solana/rpc-spec-types@5.0.1
    - @solana/rpc-types@5.0.1

## 5.0.0

### Patch Changes

- Updated dependencies [[`0fed638`](https://github.com/anza-xyz/kit/commit/0fed6389886639a48b44a09e129ac1b264c44389)]:
    - @solana/rpc-types@5.0.0
    - @solana/errors@5.0.0
    - @solana/functional@5.0.0
    - @solana/nominal-types@5.0.0
    - @solana/rpc-spec-types@5.0.0

## 4.0.0

### Patch Changes

- Updated dependencies [[`5408f52`](https://github.com/anza-xyz/kit/commit/5408f524ae22293cb7b497310440019be5a98c55), [`cb11699`](https://github.com/anza-xyz/kit/commit/cb11699d77536e5901c62d32e43c671b044e4aa1), [`9fa8465`](https://github.com/anza-xyz/kit/commit/9fa8465bf0f264f5a9181c805a0d85cb1ecc2768), [`ce7f91c`](https://github.com/anza-xyz/kit/commit/ce7f91c522118bd929f69f581d2d48e90d18c99a), [`22f18d0`](https://github.com/anza-xyz/kit/commit/22f18d0ce8950b26eaa897b146bfe8c1a025b3bb), [`c87cada`](https://github.com/anza-xyz/kit/commit/c87cada3ddf0a8c5fa27ed7122b901b17392c2df)]:
    - @solana/errors@4.0.0
    - @solana/rpc-types@4.0.0
    - @solana/functional@4.0.0
    - @solana/nominal-types@4.0.0
    - @solana/rpc-spec-types@4.0.0

## 3.0.0

### Patch Changes

- Updated dependencies [[`6a183bf`](https://github.com/anza-xyz/kit/commit/6a183bf9e9d672e2d42f3aecc589a9e54d01cb1a), [`23d2fa1`](https://github.com/anza-xyz/kit/commit/23d2fa14cbd5197473eca94a1ac6c5abf221b052), [`9feba85`](https://github.com/anza-xyz/kit/commit/9feba8557b64dd3199cd88af2c17b7ccd5d18fec), [`01f159a`](https://github.com/anza-xyz/kit/commit/01f159a436d7a29479aa1a1877c9b4c77da1170f), [`81c83b1`](https://github.com/anza-xyz/kit/commit/81c83b12dd0e145bf7d08182e01824f2f14e5ee5)]:
    - @solana/errors@3.0.0
    - @solana/rpc-spec-types@3.0.0
    - @solana/rpc-types@3.0.0
    - @solana/functional@3.0.0
    - @solana/nominal-types@3.0.0

## 2.3.0

### Patch Changes

- Updated dependencies [[`363e3cc`](https://github.com/anza-xyz/kit/commit/363e3cc45db77a731bab1435b925fe0ad0af01df), [`eeac21d`](https://github.com/anza-xyz/kit/commit/eeac21d5fe4d8fb3ed3addee87872679ee37b4c4), [`93609aa`](https://github.com/anza-xyz/kit/commit/93609aa31dbd83086d0debd41aa2f8e9a0809761), [`b7dfe03`](https://github.com/anza-xyz/kit/commit/b7dfe033a8e929d7a598d8bfea546e9ef4207639)]:
    - @solana/errors@2.3.0
    - @solana/rpc-types@2.3.0
    - @solana/functional@2.3.0
    - @solana/nominal-types@2.3.0
    - @solana/rpc-spec-types@2.3.0

## 2.2.1

### Patch Changes

- Updated dependencies []:
    - @solana/errors@2.2.1
    - @solana/functional@2.2.1
    - @solana/nominal-types@2.2.1
    - @solana/rpc-spec-types@2.2.1
    - @solana/rpc-types@2.2.1

## 2.2.0

### Patch Changes

- Updated dependencies [[`85925d6`](https://github.com/anza-xyz/kit/commit/85925d64308e91b59fb748c75e4b414012eb4893)]:
    - @solana/nominal-types@2.2.0
    - @solana/rpc-types@2.2.0
    - @solana/errors@2.2.0
    - @solana/functional@2.2.0
    - @solana/rpc-spec-types@2.2.0

## 2.1.1

### Patch Changes

- [#353](https://github.com/anza-xyz/kit/pull/353) [`7e7b2ef`](https://github.com/anza-xyz/kit/commit/7e7b2efebfd8de431e4381cc3d3fa117d3228030) Thanks [@steveluscher](https://github.com/steveluscher)! - Removed `OPTIONS_OBJECT_POSITION_BY_METHOD`, `downcastNodeToNumberIfBigint()`, `applyDefaultCommitment()`, `getIntegerOverflowNodeVisitor()`, `getBigIntUpcastVisitor()`, and `getTreeWalker()` from the exports of `@solana/rpc-transformer`

- [#473](https://github.com/anza-xyz/kit/pull/473) [`36a9dee`](https://github.com/anza-xyz/kit/commit/36a9dee4e6cbd72020dc74777fe394130b9a5f46) Thanks [@steveluscher](https://github.com/steveluscher)! - The identity of all branded types has changed in such a way that the types from v2.1.1 will be compatible with any other version going forward, which is not the case for versions v2.1.0 and before.

    If you end up with a mix of versions in your project prior to v2.1.1 (eg. `@solana/addresses@2.0.0` and `@solana/addresses@2.1.0`) you may discover that branded types like `Address` raise a type error, even though they are runtime compatible. Your options are:
    1. Always make sure that you have exactly one instance of each `@solana/*` dependency in your project at any given time
    2. Upgrade all of your `@solana/*` dependencies to v2.1.1 at minimum, even if their minor or patch versions differ.
    3. Suppress the type errors using a comment like the following:
        ```ts
        const myAddress = address('1234..5678'); // from @solana/addresses@2.0.0
        const myAccount = await fetchEncodedAccount(
            // imports @solana/addresses@2.1.0
            rpc,
            // @ts-expect-error Address types mismatch between installed versions of @solana/addresses
            myAddress,
        );
        ```

- [#236](https://github.com/anza-xyz/kit/pull/236) [`ca1d4ec`](https://github.com/anza-xyz/kit/commit/ca1d4ec7ddd641ca813f79f8ca06d225f29419e2) Thanks [@steveluscher](https://github.com/steveluscher)! - The minimum TypeScript version is now 5.3.3

- Updated dependencies [[`36a9dee`](https://github.com/anza-xyz/kit/commit/36a9dee4e6cbd72020dc74777fe394130b9a5f46), [`41b679c`](https://github.com/anza-xyz/kit/commit/41b679c2646029c9c7f005de55fba687e3c89e8a), [`ca1d4ec`](https://github.com/anza-xyz/kit/commit/ca1d4ec7ddd641ca813f79f8ca06d225f29419e2)]:
    - @solana/rpc-spec-types@2.1.1
    - @solana/nominal-types@2.1.1
    - @solana/functional@2.1.1
    - @solana/rpc-types@2.1.1
    - @solana/errors@2.1.1

## 2.1.0

### Patch Changes

- Updated dependencies [[`1adf435`](https://github.com/anza-xyz/kit/commit/1adf435cfc724303f64e509a6fda144ec8f5019d), [`c7b7dd9`](https://github.com/anza-xyz/kit/commit/c7b7dd99aca878d2450760c214dbea593ddbadc0), [`9b179dc`](https://github.com/anza-xyz/kit/commit/9b179dc6b7c7e6e4d51481a396567f17665abbc3), [`400f4d5`](https://github.com/anza-xyz/kit/commit/400f4d5673286a197561033bba63bac9a433cc6a), [`5af7f20`](https://github.com/anza-xyz/kit/commit/5af7f2013135a79893a0f190a905c6dd077ac38c), [`704d8a2`](https://github.com/anza-xyz/kit/commit/704d8a220592a5a472bd7726013814b50c991f5b)]:
    - @solana/errors@2.1.0
    - @solana/rpc-types@2.1.0
    - @solana/functional@2.1.0
    - @solana/rpc-spec-types@2.1.0

## 2.0.0

### Patch Changes

- [#3407](https://github.com/solana-labs/solana-web3.js/pull/3407) [`10b08ac`](https://github.com/solana-labs/solana-web3.js/commit/10b08ac8cdb61aa1412475426cfcaf0eefe32722) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Use `RpcRequest`, `RpcResponse` and their transformers in RPC Subscriptions packages

    This change makes the RPC and RPC Subscriptions architecture more consistent by using the same `RpcRequest` and `RpcResponse` types and transformers as the basis for handling user requests (RPC calls or subscriptions) and returning responses to them.

    See the following PRs for more details:
    - [PR #3393](https://github.com/solana-labs/solana-web3.js/pull/3393)
    - [PR #3394](https://github.com/solana-labs/solana-web3.js/pull/3394)
    - [PR #3403](https://github.com/solana-labs/solana-web3.js/pull/3403)
    - [PR #3404](https://github.com/solana-labs/solana-web3.js/pull/3404)
    - [PR #3405](https://github.com/solana-labs/solana-web3.js/pull/3405)

- [#3161](https://github.com/solana-labs/solana-web3.js/pull/3161) [`9dfca45`](https://github.com/solana-labs/solana-web3.js/commit/9dfca454355819444bad29e48602886428ba4cac) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Change first argument of `onIntegerOverflow` handler from `methodName: string` to `request: RpcRequest`

- [#3163](https://github.com/solana-labs/solana-web3.js/pull/3163) [`29d5113`](https://github.com/solana-labs/solana-web3.js/commit/29d5113b2c6f8c7907127ad992bad1329edbd7e7) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getThrowSolanaErrorResponseTransformer`, `getResultResponseTransformer`, `getBigIntUpcastResponseTransformer` and `getTreeWalkerResponseTransformer` helpers

- [#2950](https://github.com/solana-labs/solana-web3.js/pull/2950) [`29821df`](https://github.com/solana-labs/solana-web3.js/commit/29821df246b14eb41dd4606913f44fac40183957) Thanks [@mcintyre94](https://github.com/mcintyre94)! - Refactor rpc-spec to remove requirement for transports to implement parts of JSON RPC spec

- [#3150](https://github.com/solana-labs/solana-web3.js/pull/3150) [`a705413`](https://github.com/solana-labs/solana-web3.js/commit/a705413e357fb5c5907c5fc1df17d241bc5c0f76) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Make `RpcApi` use new `RpcRequestTransformer` and `RpcResponseTransformer`

- [#3541](https://github.com/solana-labs/solana-web3.js/pull/3541) [`135dc5a`](https://github.com/solana-labs/solana-web3.js/commit/135dc5ad43f286380a4c3a689668016f0d7945f4) Thanks [@steveluscher](https://github.com/steveluscher)! - Drop the Release Candidate label and publish `@solana/web3.js` at version 2.0.0

- [#3161](https://github.com/solana-labs/solana-web3.js/pull/3161) [`9dfca45`](https://github.com/solana-labs/solana-web3.js/commit/9dfca454355819444bad29e48602886428ba4cac) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getIntegerOverflowRequestTransformer`, `getBigIntDowncastRequestTransformer` and `getTreeWalkerRequestTransformer` helpers

- [#3159](https://github.com/solana-labs/solana-web3.js/pull/3159) [`747b9ab`](https://github.com/solana-labs/solana-web3.js/commit/747b9abb90c6baeec73a284d87a324bf3caeab03) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getDefaultCommitmentRequestTransformer` helper

- [#3184](https://github.com/solana-labs/solana-web3.js/pull/3184) [`28ca5d1`](https://github.com/solana-labs/solana-web3.js/commit/28ca5d17d4c574a690a5bf29d4f1fe0ad8f5883c) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Remove temporary fix for Agave issue 479

    The fix is now deployed on mainnet-beta (See https://github.com/anza-xyz/agave/issues/479 and https://github.com/anza-xyz/agave/pull/483).

- [#2606](https://github.com/solana-labs/solana-web3.js/pull/2606) [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Use commonjs package type

- [#2415](https://github.com/solana-labs/solana-web3.js/pull/2415) [`c801637`](https://github.com/solana-labs/solana-web3.js/commit/c801637bcf94930be832c57817166da2d2fdb1a4) Thanks [@steveluscher](https://github.com/steveluscher)! - Improve transaction sending reliability for those who skip preflight (simulation) when calling `sendTransaction`

- [#3137](https://github.com/solana-labs/solana-web3.js/pull/3137) [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a) Thanks [@mcintyre94](https://github.com/mcintyre94)! - The build is now compatible with the Vercel Edge runtime and Cloudflare Workers through the addition of `edge-light` and `workerd` to the package exports.

- Updated dependencies [[`9370133`](https://github.com/solana-labs/solana-web3.js/commit/9370133e414bfa863517248d97905449e9a867eb), [`31916ae`](https://github.com/solana-labs/solana-web3.js/commit/31916ae5d4fb29f239c63252a59745e33a6979ea), [`10b08ac`](https://github.com/solana-labs/solana-web3.js/commit/10b08ac8cdb61aa1412475426cfcaf0eefe32722), [`3834d82`](https://github.com/solana-labs/solana-web3.js/commit/3834d82eb1dd150f261612d742c3105194689c13), [`45df702`](https://github.com/solana-labs/solana-web3.js/commit/45df7028d872e65759dad86b97cd9d4a9a3a545e), [`3c02c35`](https://github.com/solana-labs/solana-web3.js/commit/3c02c3582f5b87151b7ac1d9cd24b9d20f6945ea), [`1c25dd4`](https://github.com/solana-labs/solana-web3.js/commit/1c25dd4069a3a8f5599285c9b0eaeb71a2f897d1), [`89f399d`](https://github.com/solana-labs/solana-web3.js/commit/89f399d474abac463b1daaa864c88305d7b8c21f), [`ebb03cd`](https://github.com/solana-labs/solana-web3.js/commit/ebb03cd8270027db957d4cecc7d2374d468d4ccb), [`002cc38`](https://github.com/solana-labs/solana-web3.js/commit/002cc38a99cd4c91c7ce9023e1b4fb28f7e10832), [`0245265`](https://github.com/solana-labs/solana-web3.js/commit/024526554fa0145e31e62a0d47f1eea556a30e71), [`ce1be3f`](https://github.com/solana-labs/solana-web3.js/commit/ce1be3fe37ea9b744fd836f3d6c2c8e5e31efd77), [`82cf07f`](https://github.com/solana-labs/solana-web3.js/commit/82cf07f4e905f6b056e70a0463a94222c3e7cadd), [`2d54650`](https://github.com/solana-labs/solana-web3.js/commit/2d5465018d8060eceb00efbf4f718df26d145199), [`135dc5a`](https://github.com/solana-labs/solana-web3.js/commit/135dc5ad43f286380a4c3a689668016f0d7945f4), [`bef9604`](https://github.com/solana-labs/solana-web3.js/commit/bef960435eb2303395bfa76e44f84d3348c5722d), [`7e86583`](https://github.com/solana-labs/solana-web3.js/commit/7e86583da68695076ec62033f3fe078b3890f026), [`4f19842`](https://github.com/solana-labs/solana-web3.js/commit/4f198423997d28d927f982333d268e19940656df), [`677a9c4`](https://github.com/solana-labs/solana-web3.js/commit/677a9c4eb88a8ac6a9ede8d82f367c5ac8d69ff4), [`38faba0`](https://github.com/solana-labs/solana-web3.js/commit/38faba05fab479ddbd95d0e211744d203f8aa823), [`73bd5a9`](https://github.com/solana-labs/solana-web3.js/commit/73bd5a9e0b32846cd5d76f2d2d1b21661eab0677), [`2e5af9f`](https://github.com/solana-labs/solana-web3.js/commit/2e5af9f1a9410f15108863342b48225fdf9a0c83), [`2798061`](https://github.com/solana-labs/solana-web3.js/commit/27980617e4f8d34dbc7b6da4507e4bca68a68090), [`be36bab`](https://github.com/solana-labs/solana-web3.js/commit/be36babd752b1c987a2f53b4ff83ac8c045a3418), [`288029a`](https://github.com/solana-labs/solana-web3.js/commit/288029a55a5eeb863b6df960027a59214ffc37f1), [`4ae78f5`](https://github.com/solana-labs/solana-web3.js/commit/4ae78f5cdddd6772b25351beb813483d4e52cea6), [`478443f`](https://github.com/solana-labs/solana-web3.js/commit/478443fedac06678f12e8ac285aa7c7fcf503ee8), [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b), [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a), [`db144da`](https://github.com/solana-labs/solana-web3.js/commit/db144da362e3389837b56f97abfb766cc8c847c2)]:
    - @solana/errors@2.0.0
    - @solana/rpc-types@2.0.0
    - @solana/rpc-spec-types@2.0.0
    - @solana/functional@2.0.0

## 2.0.0-rc.4

### Patch Changes

- Updated dependencies [[`2798061`](https://github.com/solana-labs/solana-web3.js/commit/27980617e4f8d34dbc7b6da4507e4bca68a68090)]:
    - @solana/errors@2.0.0-rc.4
    - @solana/rpc-types@2.0.0-rc.4
    - @solana/functional@2.0.0-rc.4
    - @solana/rpc-spec-types@2.0.0-rc.4

## 2.0.0-rc.3

### Patch Changes

- Updated dependencies [[`45df702`](https://github.com/solana-labs/solana-web3.js/commit/45df7028d872e65759dad86b97cd9d4a9a3a545e)]:
    - @solana/rpc-spec-types@2.0.0-rc.3
    - @solana/errors@2.0.0-rc.3
    - @solana/functional@2.0.0-rc.3
    - @solana/rpc-types@2.0.0-rc.3

## 2.0.0-rc.2

### Patch Changes

- [#3407](https://github.com/solana-labs/solana-web3.js/pull/3407) [`10b08ac`](https://github.com/solana-labs/solana-web3.js/commit/10b08ac8cdb61aa1412475426cfcaf0eefe32722) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Use `RpcRequest`, `RpcResponse` and their transformers in RPC Subscriptions packages

    This change makes the RPC and RPC Subscriptions architecture more consistent by using the same `RpcRequest` and `RpcResponse` types and transformers as the basis for handling user requests (RPC calls or subscriptions) and returning responses to them.

    See the following PRs for more details:
    - [PR #3393](https://github.com/solana-labs/solana-web3.js/pull/3393)
    - [PR #3394](https://github.com/solana-labs/solana-web3.js/pull/3394)
    - [PR #3403](https://github.com/solana-labs/solana-web3.js/pull/3403)
    - [PR #3404](https://github.com/solana-labs/solana-web3.js/pull/3404)
    - [PR #3405](https://github.com/solana-labs/solana-web3.js/pull/3405)

- [#3161](https://github.com/solana-labs/solana-web3.js/pull/3161) [`9dfca45`](https://github.com/solana-labs/solana-web3.js/commit/9dfca454355819444bad29e48602886428ba4cac) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Change first argument of `onIntegerOverflow` handler from `methodName: string` to `request: RpcRequest`

- [#3163](https://github.com/solana-labs/solana-web3.js/pull/3163) [`29d5113`](https://github.com/solana-labs/solana-web3.js/commit/29d5113b2c6f8c7907127ad992bad1329edbd7e7) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getThrowSolanaErrorResponseTransformer`, `getResultResponseTransformer`, `getBigIntUpcastResponseTransformer` and `getTreeWalkerResponseTransformer` helpers

- [#3150](https://github.com/solana-labs/solana-web3.js/pull/3150) [`a705413`](https://github.com/solana-labs/solana-web3.js/commit/a705413e357fb5c5907c5fc1df17d241bc5c0f76) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Make `RpcApi` use new `RpcRequestTransformer` and `RpcResponseTransformer`

- [#3161](https://github.com/solana-labs/solana-web3.js/pull/3161) [`9dfca45`](https://github.com/solana-labs/solana-web3.js/commit/9dfca454355819444bad29e48602886428ba4cac) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getIntegerOverflowRequestTransformer`, `getBigIntDowncastRequestTransformer` and `getTreeWalkerRequestTransformer` helpers

- [#3159](https://github.com/solana-labs/solana-web3.js/pull/3159) [`747b9ab`](https://github.com/solana-labs/solana-web3.js/commit/747b9abb90c6baeec73a284d87a324bf3caeab03) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Add `getDefaultCommitmentRequestTransformer` helper

- [#3184](https://github.com/solana-labs/solana-web3.js/pull/3184) [`28ca5d1`](https://github.com/solana-labs/solana-web3.js/commit/28ca5d17d4c574a690a5bf29d4f1fe0ad8f5883c) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Remove temporary fix for Agave issue 479

    The fix is now deployed on mainnet-beta (See https://github.com/anza-xyz/agave/issues/479 and https://github.com/anza-xyz/agave/pull/483).

- [#3137](https://github.com/solana-labs/solana-web3.js/pull/3137) [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a) Thanks [@mcintyre94](https://github.com/mcintyre94)! - The build is now compatible with the Vercel Edge runtime and Cloudflare Workers through the addition of `edge-light` and `workerd` to the package exports.

- Updated dependencies [[`10b08ac`](https://github.com/solana-labs/solana-web3.js/commit/10b08ac8cdb61aa1412475426cfcaf0eefe32722), [`3834d82`](https://github.com/solana-labs/solana-web3.js/commit/3834d82eb1dd150f261612d742c3105194689c13), [`3c02c35`](https://github.com/solana-labs/solana-web3.js/commit/3c02c3582f5b87151b7ac1d9cd24b9d20f6945ea), [`1c25dd4`](https://github.com/solana-labs/solana-web3.js/commit/1c25dd4069a3a8f5599285c9b0eaeb71a2f897d1), [`0245265`](https://github.com/solana-labs/solana-web3.js/commit/024526554fa0145e31e62a0d47f1eea556a30e71), [`38faba0`](https://github.com/solana-labs/solana-web3.js/commit/38faba05fab479ddbd95d0e211744d203f8aa823), [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a), [`db144da`](https://github.com/solana-labs/solana-web3.js/commit/db144da362e3389837b56f97abfb766cc8c847c2)]:
    - @solana/rpc-spec-types@2.0.0-rc.2
    - @solana/rpc-types@2.0.0-rc.2
    - @solana/errors@2.0.0-rc.2
    - @solana/functional@2.0.0-rc.2

## 2.0.0-rc.1

### Patch Changes

- Updated dependencies []:
    - @solana/errors@2.0.0-rc.1
    - @solana/functional@2.0.0-rc.1
    - @solana/rpc-spec@2.0.0-rc.1
    - @solana/rpc-subscriptions-spec@2.0.0-rc.1
    - @solana/rpc-types@2.0.0-rc.1

## 2.0.0-rc.0

### Patch Changes

- [#2950](https://github.com/solana-labs/solana-web3.js/pull/2950) [`29821df`](https://github.com/solana-labs/solana-web3.js/commit/29821df246b14eb41dd4606913f44fac40183957) Thanks [@mcintyre94](https://github.com/mcintyre94)! - Refactor rpc-spec to remove requirement for transports to implement parts of JSON RPC spec

- Updated dependencies [[`29821df`](https://github.com/solana-labs/solana-web3.js/commit/29821df246b14eb41dd4606913f44fac40183957), [`677a9c4`](https://github.com/solana-labs/solana-web3.js/commit/677a9c4eb88a8ac6a9ede8d82f367c5ac8d69ff4)]:
    - @solana/rpc-spec@2.0.0-rc.0
    - @solana/errors@2.0.0-rc.0
    - @solana/rpc-subscriptions-spec@2.0.0-rc.0
    - @solana/rpc-types@2.0.0-rc.0
    - @solana/functional@2.0.0-rc.0

## 2.0.0-preview.4

### Patch Changes

- [#2606](https://github.com/solana-labs/solana-web3.js/pull/2606) [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b) Thanks [@lorisleiva](https://github.com/lorisleiva)! - Use commonjs package type

- Updated dependencies [[`73bd5a9`](https://github.com/solana-labs/solana-web3.js/commit/73bd5a9e0b32846cd5d76f2d2d1b21661eab0677), [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b), [`6340744`](https://github.com/solana-labs/solana-web3.js/commit/6340744e5cf0ea91ae677f381d5a187638a19597)]:
    - @solana/rpc-types@2.0.0-preview.4
    - @solana/rpc-subscriptions-spec@2.0.0-preview.4
    - @solana/functional@2.0.0-preview.4
    - @solana/rpc-spec@2.0.0-preview.4

## 2.0.0-preview.3

### Patch Changes

- [#2415](https://github.com/solana-labs/solana-web3.js/pull/2415) [`c801637`](https://github.com/solana-labs/solana-web3.js/commit/c801637bcf94930be832c57817166da2d2fdb1a4) Thanks [@steveluscher](https://github.com/steveluscher)! - Improve transaction sending reliability for those who skip preflight (simulation) when calling `sendTransaction`

- Updated dependencies [[`31916ae`](https://github.com/solana-labs/solana-web3.js/commit/31916ae5d4fb29f239c63252a59745e33a6979ea), [`002cc38`](https://github.com/solana-labs/solana-web3.js/commit/002cc38a99cd4c91c7ce9023e1b4fb28f7e10832), [`2e5af9f`](https://github.com/solana-labs/solana-web3.js/commit/2e5af9f1a9410f15108863342b48225fdf9a0c83)]:
    - @solana/rpc-types@2.0.0-preview.3
    - @solana/rpc-spec@2.0.0-preview.3
    - @solana/rpc-subscriptions-spec@2.0.0-preview.3
    - @solana/functional@2.0.0-preview.3

## 2.0.0-preview.2

### Patch Changes

- The first Technology Preview of `@solana/web3.js` 2.0 was [released at the Breakpoint conference](https://www.youtube.com/watch?v=JUJtAPhES5g) in November 2023. Based on your feedback, we want to get a second version of it into your hands now with some changes, bug fixes, and new features.

    To install the second Technology Preview:

    ```shell
    npm install --save @solana/web3.js@tp2
    ```

    Most notably, this release integrates with the new JavaScript client generator for on-chain programs. Instruction creators and account decoders can now be autogenerated for any program, including your own! Read more [here](https://github.com/solana-program/create-solana-program), and check out the growing list of autogenerated core programs [here](https://www.npmjs.com/search?q=%40solana-program).

    Try a demo of Technology Preview 2 in your browser at https://sola.na/web3tp2demo.
    - Renamed `Base58EncodedAddress` to `Address` (#1814) [63683a4bc](https://github.com/solana-labs/solana-web3.js/commit/63683a4bc)
    - Renamed `Ed25519Signature` and `TransactionSignature` to `SignatureBytes` and `Signature` (#1815) [205c09268](https://github.com/solana-labs/solana-web3.js/commit/205c09268)
    - Fixed return type of `getSignaturesForAddress` (#1821) [36c7263bd](https://github.com/solana-labs/solana-web3.js/commit/36c7263bd)
    - `signTransaction` now asserts that the transaction is fully signed; added `partiallySignTransaction` that does not (#1820) [7d54c2dad](https://github.com/solana-labs/solana-web3.js/commit/7d54c2dad)
    - The `@solana/webcrypto-ed25519-polyfill` now sets the `crypto` global in Node [17a54d24a](https://github.com/solana-labs/solana-web3.js/commit/17a54d24a)
    - Added `assertIsBlockhashLifetimeTransaction` that asserts transaction has a blockhash lifetime (#1908) [ae94ca38d](https://github.com/solana-labs/solana-web3.js/commit/ae94ca38d)
    - Added a `createPrivateKeyFromBytes` helper (#1913) [85b7dfe13](https://github.com/solana-labs/solana-web3.js/commit/85b7dfe13)
    - Added `@solana/accounts`; types and helper methods for representing, fetching and decoding Solana accounts (#1855) [e1ca3966e](https://github.com/solana-labs/solana-web3.js/commit/e1ca3966e)
    - Export the TransactionError type (#1964) [4c009bf5b](https://github.com/solana-labs/solana-web3.js/commit/4c009bf5b)
    - Export all RPC method XApi types from `@solana/rpc-core` (#1965) [ed98b3d9c](https://github.com/solana-labs/solana-web3.js/commit/ed98b3d9c)
    - Added a generic `createJsonRpcApi` function for custom APIs [1e2106f21](https://github.com/solana-labs/solana-web3.js/commit/1e2106f21)
    - Added a generic `createJsonRpcSubscriptionsApi` function for custom APIs [ae3f1f087](https://github.com/solana-labs/solana-web3.js/commit/ae3f1f087)
    - RPC commitment now defaults to `confirmed` when not explicitly specified [cb7702ca5](https://github.com/solana-labs/solana-web3.js/commit/cb7702ca5)
    - Added `ClusterUrl` types and handlers (#2084) [61f7ba0](https://github.com/solana-labs/solana-web3.js/commit/61f7ba0)
    - RPC transports can now be cluster-specific, ie. `RpcDevnet<TRpcMethods>` & `RpcSubscriptionsDevnet<TRpcMethods>` (#2053) [e58bb22](https://github.com/solana-labs/solana-web3.js/commit/e58bb22), (#2056) [cbf8f38](https://github.com/solana-labs/solana-web3.js/commit/cbf8f38)
    - RPC APIs can now be cluster-specific, ie. `SolanaRpcMethodsDevnet` (#2054) [5175d8a](https://github.com/solana-labs/solana-web3.js/commit/5175d8a)
    - Added cluster-level RPC support for `@solana/web3.js` (#2055) [5a6335d](https://github.com/solana-labs/solana-web3.js/commit/5a6335d), (#2058) [0e03ca9](https://github.com/solana-labs/solana-web3.js/commit/0e03ca9)
    - Added `@solana/signers`; an abstraction layer over signing messages and transactions in Solana (#1710) [7c29a1e](https://github.com/solana-labs/solana-web3.js/commit/7c29a1e)
    - Updated codec such that only one instance of `Uint8Array` is created when encoding data. This allows `Encoders` to set data at different offsets and therefore enables non-linear serialization (#1865) [7800e3b](https://github.com/solana-labs/solana-web3.js/commit/7800e3b)
    - Added `FixedSize*` and `VariableSize*` type variants for `Codecs`, `Encoders` and `Decoders` (#1883) [5e58d5c](https://github.com/solana-labs/solana-web3.js/commit/5e58d5c)
    - Repaired some inaccurate RPC method signatures (#2137) [bb65ba9](https://github.com/solana-labs/solana-web3.js/commit/bb65ba9)
    - Renamed transaction/airdrop sender factories with the ‘Factory’ suffix (#2130) [2d1d49c](https://github.com/solana-labs/solana-web3.js/commit/2d1d49c5467e5cb13871067c3dc0f9c87f007b9f)
    - All code now throws coded exceptions defined in `@solana/errors` which can be refined using `isSolanaError()` and decoded in production using `npx @solana/errors decode` (#2160) [3524f2c](https://github.com/solana-labs/solana-web3.js/commit/3524f2c583dbc663cf6dcb73a01b0beed6cfd136), (#2161) [94944b](https://github.com/solana-labs/solana-web3.js/commit/94944b65b9d957ca95653d66dc1f4805f1a36740), (#2213) [8541c2e](https://github.com/solana-labs/solana-web3.js/commit/8541c2ef860535514fa39c4b9a6a75276417ffaa), (#2220) [c9b2705](https://github.com/solana-labs/solana-web3.js/commit/c9b2705318724bbccb05efdb1ddc088dd82921b2), (#2207) [75a18e3](https://github.com/solana-labs/solana-web3.js/commit/75a18e30524078ea1e8c07133fd6c75fad357db3), (#2224) [613053d](https://github.com/solana-labs/solana-web3.js/commit/613053deab85e5a8703e241ab138ec51cc54885a), (#2226) [94fee67](https://github.com/solana-labs/solana-web3.js/commit/94fee67560faae1f41aeddb2e7c3d0d9078ab851), (#2228) [483c674](https://github.com/solana-labs/solana-web3.js/commit/483c674a8b19f146c7dba5f1eb64182f01fdcdc4), (#2235) [803b2d8](https://github.com/solana-labs/solana-web3.js/commit/803b2d88e9e39cecf18f03b2130507dea7230423), (#2236) [cf9c20c](https://github.com/solana-labs/solana-web3.js/commit/cf9c20ceed7186f5af704ee646344c42d4ec0084), (#2242) [9084fdd](https://github.com/solana-labs/solana-web3.js/commit/9084fddec79eebb9c00c70738e43b4bfb01bf352), (#2245) [e374ac6](https://github.com/solana-labs/solana-web3.js/commit/e374ac67ad48a121470d125a1d08485b8b529b2b), (#2186) [546263e](https://github.com/solana-labs/solana-web3.js/commit/546263e251c8a7b08949b01d0d51fa2398dc7fff), (#2187) [bea19d2](https://github.com/solana-labs/solana-web3.js/commit/bea19d209ea6b02351c21a878200f87da1e9b4be), (#2188) [2e0ae95](https://github.com/solana-labs/solana-web3.js/commit/2e0ae95ffc2738ae047249c7f64c46a95e9573d1), (#2189) [7712fc3](https://github.com/solana-labs/solana-web3.js/commit/7712fc32ef33bfe7f235d85d3ba2308ba6884143), (#2190) [7d67615](https://github.com/solana-labs/solana-web3.js/commit/7d67615ac1ae771810dfc544ecc17d664a0fc11d), (#2191) [0ba8f21](https://github.com/solana-labs/solana-web3.js/commit/0ba8f216d962d61e0f653404c4a9289e59712cc2), (#2192) [91a360d](https://github.com/solana-labs/solana-web3.js/commit/91a360daf5c66ac0f1bae7347298f25ae89329b2), (#2202) [a71a2db](https://github.com/solana-labs/solana-web3.js/commit/a71a2db4c35136c8650b56985bbd33c5413e1bbd), (#2286) [52a5d3d](https://github.com/solana-labs/solana-web3.js/commit/52a5d3db60e702ccf77b4d17b8a3fd388e6e8584), and more
    - You can now supply a custom Undici dispatcher for use with the `fetch` API when creating an RPC transport in Node (#2178) [a2fc5a3](https://github.com/solana-labs/solana-web3.js/commit/a2fc5a3fda252cccc6ee62f2f7163d1578a20113)
    - Added functions to assert a value is an `IInstructionWithAccounts` and IInstructionWithData` (#2212) [07c30c1](https://github.com/solana-labs/solana-web3.js/commit/07c30c14c7d5efd6121290db62fa40371f108778)
    - Added a function to assert an instruction is for a given program (#2234) [fb655dd](https://github.com/solana-labs/solana-web3.js/commit/fb655ddd217e4c4f55c5c8a81a08177e20ef5431)
    - You can now create an RPC using only a URL (#2238) [cd0b6c6](https://github.com/solana-labs/solana-web3.js/commit/cd0b6c616ded7d1fdee33e33d3e44ce9bce48cef), (#2239) [fc11993](https://github.com/solana-labs/solana-web3.js/commit/fc119937ade7e46f487c99f254ff5a874e524c2c)
    - You can now resize codec with the `resizeCodec` helper (#2293) [606de63](https://github.com/solana-labs/solana-web3.js/commit/606de638e21eebd0535806dee445e6d046cfb074)
    - You can now skip bytes while writing byte buffers using the `offsetCodec` helper (#2294) [09d8cc8](https://github.com/solana-labs/solana-web3.js/commit/09d8cc815d133d70da0db93c9a0c0092e0d9a929)
    - You can now now pad the beginning or end of byte buffers using the `padLeftCodec` and `padRightCodec` helpers (#2314) [f9509c7](https://github.com/solana-labs/solana-web3.js/commit/f9509c77dd6ec92357edbbe18acbb76c5a33e4b2)
    - Added a new `@solana/sysvars` package for fetching, decoding, and building transactions with sysvar accounts (#2041)

- Updated dependencies [[`0546a8c`](https://github.com/solana-labs/solana-web3.js/commit/0546a8ce95b6852324d58bb32ac31480506193a7)]:
    - @solana/rpc-spec@2.0.0-preview.2
    - @solana/rpc-subscriptions-spec@2.0.0-preview.2
    - @solana/rpc-types@2.0.0-preview.2

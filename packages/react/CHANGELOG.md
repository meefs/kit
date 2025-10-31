# @solana/react

## 5.0.1

### Patch Changes

- Updated dependencies []:
    - @solana/addresses@5.0.1
    - @solana/errors@5.0.1
    - @solana/keys@5.0.1
    - @solana/promises@5.0.1
    - @solana/signers@5.0.1
    - @solana/transaction-messages@5.0.1
    - @solana/transactions@5.0.1

## 5.0.0

### Patch Changes

- Updated dependencies [[`0fed638`](https://github.com/anza-xyz/kit/commit/0fed6389886639a48b44a09e129ac1b264c44389)]:
    - @solana/errors@5.0.0
    - @solana/signers@5.0.0
    - @solana/transaction-messages@5.0.0
    - @solana/transactions@5.0.0
    - @solana/addresses@5.0.0
    - @solana/keys@5.0.0
    - @solana/promises@5.0.0

## 4.0.0

### Major Changes

- [#927](https://github.com/anza-xyz/kit/pull/927) [`c035ab8`](https://github.com/anza-xyz/kit/commit/c035ab8a488486d160ca0361408493115cd09383) Thanks [@mcintyre94](https://github.com/mcintyre94)! - Update the signer API to return Transaction & TransactionWithLifetime

    The `modifyAndSignTransactions` function for a `TransactionModifyingSigner` must now return a `Transaction & TransactionWithLifetime & TransactionWithinSizeLimit`. Previously it technically needed to return a type derived from the input `TransactionMessage`, but this wasn't checked.

    If you have written a `TransactionModifyingSigner` then you should review the changes to `useWalletAccountTransactionSigner` in the React package for guidance. You may need to use the new `getTransactionLifetimeConstraintFromCompiledTransactionMessage` function to obtain a lifetime for the transaction being returned.

    If you are using a `TransactionModifyingSigner` such as `useWalletAccountTransactionSigner`, then you will now receive a transaction with `TransactionWithLifetime` when you would previously have received a type with a lifetime matching the input transaction message. This was never guaranteed to match at runtime, but we incorrectly returned a stronger type than can be guaranteed. You may need to use the new `isTransactionWithBlockhashLifetime` or `isTransactionWithDurableNonceLifetime` functions to check the lifetime type of the returned transaction. For example, if you want to pass it to a function returned by `sendAndConfirmTransactionFactory` then you must use `isTransactionWithBlockhashLifetime` or `assertIsTransactionWithBlockhashLifetime` to check its lifetime first.

### Patch Changes

- [#919](https://github.com/anza-xyz/kit/pull/919) [`c87cada`](https://github.com/anza-xyz/kit/commit/c87cada3ddf0a8c5fa27ed7122b901b17392c2df) Thanks [@mcintyre94](https://github.com/mcintyre94)! - Update useWalletAccountTransactionSigner to return a LifetimeConstraint for the updated transaction

- Updated dependencies [[`5408f52`](https://github.com/anza-xyz/kit/commit/5408f524ae22293cb7b497310440019be5a98c55), [`f591dea`](https://github.com/anza-xyz/kit/commit/f591dead4a3d5871fd02460f6301bb4bdf6b508e), [`cb11699`](https://github.com/anza-xyz/kit/commit/cb11699d77536e5901c62d32e43c671b044e4aa1), [`9fa8465`](https://github.com/anza-xyz/kit/commit/9fa8465bf0f264f5a9181c805a0d85cb1ecc2768), [`af01f27`](https://github.com/anza-xyz/kit/commit/af01f2770e4b3a94f3ef3360677b27aa08175c1b), [`c035ab8`](https://github.com/anza-xyz/kit/commit/c035ab8a488486d160ca0361408493115cd09383), [`22f18d0`](https://github.com/anza-xyz/kit/commit/22f18d0ce8950b26eaa897b146bfe8c1a025b3bb), [`c87cada`](https://github.com/anza-xyz/kit/commit/c87cada3ddf0a8c5fa27ed7122b901b17392c2df), [`54d8445`](https://github.com/anza-xyz/kit/commit/54d8445bbef207b6d84da0ea91a1c091251ee013)]:
    - @solana/transactions@4.0.0
    - @solana/errors@4.0.0
    - @solana/keys@4.0.0
    - @solana/transaction-messages@4.0.0
    - @solana/signers@4.0.0
    - @solana/addresses@4.0.0
    - @solana/promises@4.0.0

## 3.0.0

### Patch Changes

- Updated dependencies [[`93ae6f9`](https://github.com/anza-xyz/kit/commit/93ae6f96859019b6c7ea9a596ffb9b1be7a35e64), [`6a183bf`](https://github.com/anza-xyz/kit/commit/6a183bf9e9d672e2d42f3aecc589a9e54d01cb1a), [`760fb83`](https://github.com/anza-xyz/kit/commit/760fb8319f6b53fa1baf05f9aa1246cb6c2caceb), [`23d2fa1`](https://github.com/anza-xyz/kit/commit/23d2fa14cbd5197473eca94a1ac6c5abf221b052), [`771f8ae`](https://github.com/anza-xyz/kit/commit/771f8aef1f8c096450c6e4ac05b8611150201485), [`a894d53`](https://github.com/anza-xyz/kit/commit/a894d53192d50b5d2217ada2cb715d71ef4f8f02), [`9feba85`](https://github.com/anza-xyz/kit/commit/9feba8557b64dd3199cd88af2c17b7ccd5d18fec), [`00d66fb`](https://github.com/anza-xyz/kit/commit/00d66fbec15288bb531f7459b6baa48aead1cdc6), [`01f159a`](https://github.com/anza-xyz/kit/commit/01f159a436d7a29479aa1a1877c9b4c77da1170f), [`0bd053b`](https://github.com/anza-xyz/kit/commit/0bd053bfa40b095d37bea7b7cd695259ba5a9cdc), [`55d6b04`](https://github.com/anza-xyz/kit/commit/55d6b040764f5e32de9c94d1844529855233d845), [`a74ea02`](https://github.com/anza-xyz/kit/commit/a74ea0267bf589fba50bb2ebe72dc4f73da9adcf), [`771f8ae`](https://github.com/anza-xyz/kit/commit/771f8aef1f8c096450c6e4ac05b8611150201485)]:
    - @solana/signers@3.0.0
    - @solana/errors@3.0.0
    - @solana/transactions@3.0.0
    - @solana/addresses@3.0.0
    - @solana/keys@3.0.0
    - @solana/promises@3.0.0

## 2.3.0

### Patch Changes

- Updated dependencies [[`6ccbf01`](https://github.com/anza-xyz/kit/commit/6ccbf012703fce1cb40388b0f4e1ffaeffea838a), [`363e3cc`](https://github.com/anza-xyz/kit/commit/363e3cc45db77a731bab1435b925fe0ad0af01df), [`eeac21d`](https://github.com/anza-xyz/kit/commit/eeac21d5fe4d8fb3ed3addee87872679ee37b4c4), [`bbcb913`](https://github.com/anza-xyz/kit/commit/bbcb913839d33abc746f38d6e65e7bfd30cd2ac6), [`93609aa`](https://github.com/anza-xyz/kit/commit/93609aa31dbd83086d0debd41aa2f8e9a0809761), [`b7dfe03`](https://github.com/anza-xyz/kit/commit/b7dfe033a8e929d7a598d8bfea546e9ef4207639), [`810d6ab`](https://github.com/anza-xyz/kit/commit/810d6abafe1b7ea46ed63c491db1f5d6c16397ab)]:
    - @solana/transactions@2.3.0
    - @solana/signers@2.3.0
    - @solana/errors@2.3.0
    - @solana/addresses@2.3.0
    - @solana/keys@2.3.0
    - @solana/promises@2.3.0

## 2.2.1

### Patch Changes

- Updated dependencies []:
    - @solana/addresses@2.2.1
    - @solana/errors@2.2.1
    - @solana/keys@2.2.1
    - @solana/promises@2.2.1
    - @solana/signers@2.2.1
    - @solana/transactions@2.2.1

## 2.2.0

### Patch Changes

- Updated dependencies [[`85925d6`](https://github.com/anza-xyz/kit/commit/85925d64308e91b59fb748c75e4b414012eb4893)]:
    - @solana/addresses@2.2.0
    - @solana/keys@2.2.0
    - @solana/signers@2.2.0
    - @solana/transactions@2.2.0
    - @solana/errors@2.2.0
    - @solana/promises@2.2.0

## 2.1.1

### Patch Changes

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

- Updated dependencies [[`36a9dee`](https://github.com/anza-xyz/kit/commit/36a9dee4e6cbd72020dc74777fe394130b9a5f46), [`ca1d4ec`](https://github.com/anza-xyz/kit/commit/ca1d4ec7ddd641ca813f79f8ca06d225f29419e2)]:
    - @solana/transactions@2.1.1
    - @solana/addresses@2.1.1
    - @solana/promises@2.1.1
    - @solana/signers@2.1.1
    - @solana/errors@2.1.1
    - @solana/keys@2.1.1

## 2.1.0

### Patch Changes

- [`1adf435`](https://github.com/anza-xyz/kit/commit/1adf435cfc724303f64e509a6fda144ec8f5019d) Thanks [@leantOnSol](https://github.com/leantOnSol)! - A two-versions-old version of Node LTS is now specified everywhere via the `engines` field, including the one in the root of the `pnpm` workspace, and engine-strictness is delegated to the `.npmrc` files.

- Updated dependencies [[`a1e45a1`](https://github.com/anza-xyz/kit/commit/a1e45a1d91ba1ac530eea0986b2ffeafb9713aec), [`1adf435`](https://github.com/anza-xyz/kit/commit/1adf435cfc724303f64e509a6fda144ec8f5019d), [`d1c787c`](https://github.com/anza-xyz/kit/commit/d1c787c447bd134e6a6da8be059c8353f92b2f9a), [`0c577eb`](https://github.com/anza-xyz/kit/commit/0c577eb03fa5db8b817f209d52a19a36976c7c12), [`c7b7dd9`](https://github.com/anza-xyz/kit/commit/c7b7dd99aca878d2450760c214dbea593ddbadc0), [`5af7f20`](https://github.com/anza-xyz/kit/commit/5af7f2013135a79893a0f190a905c6dd077ac38c), [`704d8a2`](https://github.com/anza-xyz/kit/commit/704d8a220592a5a472bd7726013814b50c991f5b)]:
    - @solana/signers@2.1.0
    - @solana/addresses@2.1.0
    - @solana/errors@2.1.0
    - @solana/keys@2.1.0
    - @solana/transactions@2.1.0
    - @solana/promises@2.1.0

## 2.0.0

### Minor Changes

- [#2928](https://github.com/solana-labs/solana-web3.js/pull/2928) [`bac3747`](https://github.com/solana-labs/solana-web3.js/commit/bac37479dcfad3da86ccd01da5095759f449eb3d) Thanks [@steveluscher](https://github.com/steveluscher)! - Added a `useSignIn` hook that, given a `UiWallet` or `UiWalletAccount`, returns a function that you can call to trigger a wallet's [&lsquo;Sign In With Solana&rsquo;](https://phantom.app/learn/developers/sign-in-with-solana) feature.

    #### Example

    ```tsx
    import { useSignIn } from '@solana/react';

    function SignInButton({ wallet }) {
        const csrfToken = useCsrfToken();
        const signIn = useSignIn(wallet);
        return (
            <button
                onClick={async () => {
                    try {
                        const { account, signedMessage, signature } = await signIn({
                            requestId: csrfToken,
                        });
                        // Authenticate the user, typically on the server, by verifying that
                        // `signedMessage` was signed by the person who holds the private key for
                        // `account.publicKey`.
                        //
                        // Authorize the user, also on the server, by decoding `signedMessage` as the
                        // text of a Sign In With Solana message, verifying that it was not modified
                        // from the values your application expects, and that its content is sufficient
                        // to grant them access.
                        window.alert(`You are now signed in with the address ${account.address}`);
                    } catch (e) {
                        console.error('Failed to sign in', e);
                    }
                }}
            >
                Sign In
            </button>
        );
    }
    ```

### Patch Changes

- [#2795](https://github.com/solana-labs/solana-web3.js/pull/2795) [`ce876d9`](https://github.com/solana-labs/solana-web3.js/commit/ce876d99f04d539292abd810acd77a319c52f50d) Thanks [@steveluscher](https://github.com/steveluscher)! - Added React hooks to which you can pass a Wallet Standard `UiWalletAccount` and obtain a `MessageModifyingSigner`, `TransactionModifyingSigner`, or `TransactionSendingSigner` for use in constructing, signing, and sending Solana transactions and messages

- [#2772](https://github.com/solana-labs/solana-web3.js/pull/2772) [`8fe4551`](https://github.com/solana-labs/solana-web3.js/commit/8fe4551217a3ad8bfdcd1609ac7b23e8fd044c72) Thanks [@steveluscher](https://github.com/steveluscher)! - Added a series of React hooks to which you can pass a Wallet Standard `UiWalletAccount` to extract its `signMessage`, `signTransaction`, and `signAndSendTransaction` features

- [#3541](https://github.com/solana-labs/solana-web3.js/pull/3541) [`135dc5a`](https://github.com/solana-labs/solana-web3.js/commit/135dc5ad43f286380a4c3a689668016f0d7945f4) Thanks [@steveluscher](https://github.com/steveluscher)! - Drop the Release Candidate label and publish `@solana/web3.js` at version 2.0.0

- [#3137](https://github.com/solana-labs/solana-web3.js/pull/3137) [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a) Thanks [@mcintyre94](https://github.com/mcintyre94)! - The build is now compatible with the Vercel Edge runtime and Cloudflare Workers through the addition of `edge-light` and `workerd` to the package exports.

- Updated dependencies [[`9370133`](https://github.com/solana-labs/solana-web3.js/commit/9370133e414bfa863517248d97905449e9a867eb), [`31916ae`](https://github.com/solana-labs/solana-web3.js/commit/31916ae5d4fb29f239c63252a59745e33a6979ea), [`292487d`](https://github.com/solana-labs/solana-web3.js/commit/292487da00ee57350e8faf49ccf961203aed6403), [`7d310f6`](https://github.com/solana-labs/solana-web3.js/commit/7d310f6f9cd7d02fca4d6f8e311b857c9dd84e61), [`1ad523d`](https://github.com/solana-labs/solana-web3.js/commit/1ad523dc5792d9152a66e9dc2b83294e3eba4db0), [`89f399d`](https://github.com/solana-labs/solana-web3.js/commit/89f399d474abac463b1daaa864c88305d7b8c21f), [`ebb03cd`](https://github.com/solana-labs/solana-web3.js/commit/ebb03cd8270027db957d4cecc7d2374d468d4ccb), [`002cc38`](https://github.com/solana-labs/solana-web3.js/commit/002cc38a99cd4c91c7ce9023e1b4fb28f7e10832), [`ce1be3f`](https://github.com/solana-labs/solana-web3.js/commit/ce1be3fe37ea9b744fd836f3d6c2c8e5e31efd77), [`82cf07f`](https://github.com/solana-labs/solana-web3.js/commit/82cf07f4e905f6b056e70a0463a94222c3e7cadd), [`2d54650`](https://github.com/solana-labs/solana-web3.js/commit/2d5465018d8060eceb00efbf4f718df26d145199), [`135dc5a`](https://github.com/solana-labs/solana-web3.js/commit/135dc5ad43f286380a4c3a689668016f0d7945f4), [`bef9604`](https://github.com/solana-labs/solana-web3.js/commit/bef960435eb2303395bfa76e44f84d3348c5722d), [`7e86583`](https://github.com/solana-labs/solana-web3.js/commit/7e86583da68695076ec62033f3fe078b3890f026), [`4f19842`](https://github.com/solana-labs/solana-web3.js/commit/4f198423997d28d927f982333d268e19940656df), [`677a9c4`](https://github.com/solana-labs/solana-web3.js/commit/677a9c4eb88a8ac6a9ede8d82f367c5ac8d69ff4), [`38faba0`](https://github.com/solana-labs/solana-web3.js/commit/38faba05fab479ddbd95d0e211744d203f8aa823), [`2e5af9f`](https://github.com/solana-labs/solana-web3.js/commit/2e5af9f1a9410f15108863342b48225fdf9a0c83), [`cec9048`](https://github.com/solana-labs/solana-web3.js/commit/cec9048b2f83535df7e499db5488c336981dfb5a), [`b4bf318`](https://github.com/solana-labs/solana-web3.js/commit/b4bf318d7d4bdd639e4c126c70350993a8540fe8), [`e3e82d9`](https://github.com/solana-labs/solana-web3.js/commit/e3e82d909825e958ae234ed18500335a621773bd), [`2798061`](https://github.com/solana-labs/solana-web3.js/commit/27980617e4f8d34dbc7b6da4507e4bca68a68090), [`54d68c4`](https://github.com/solana-labs/solana-web3.js/commit/54d68c482feebf4e62a9896b3badd77dab615941), [`be36bab`](https://github.com/solana-labs/solana-web3.js/commit/be36babd752b1c987a2f53b4ff83ac8c045a3418), [`cb49bfa`](https://github.com/solana-labs/solana-web3.js/commit/cb49bfa28f412376a41e758eeda59e7e90983147), [`f2bb4e8`](https://github.com/solana-labs/solana-web3.js/commit/f2bb4e8c7f7efd049cb1c3810291c99e9293c25d), [`288029a`](https://github.com/solana-labs/solana-web3.js/commit/288029a55a5eeb863b6df960027a59214ffc37f1), [`4ae78f5`](https://github.com/solana-labs/solana-web3.js/commit/4ae78f5cdddd6772b25351beb813483d4e52cea6), [`478443f`](https://github.com/solana-labs/solana-web3.js/commit/478443fedac06678f12e8ac285aa7c7fcf503ee8), [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b), [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a), [`4decebb`](https://github.com/solana-labs/solana-web3.js/commit/4decebb9b619972f49c740323b59cf470696e105), [`d4965ec`](https://github.com/solana-labs/solana-web3.js/commit/d4965ece9abaf81e3006442db15f3f77d89a622c), [`0158b31`](https://github.com/solana-labs/solana-web3.js/commit/0158b3181ed96996f269f3bff689f76411e460b3), [`22a34aa`](https://github.com/solana-labs/solana-web3.js/commit/22a34aa08d1be7e9b43ccfea94a99eaa2694e491), [`f9a8446`](https://github.com/solana-labs/solana-web3.js/commit/f9a84460670a97d4ab6514b28fe0d29c6fac3302), [`125fc15`](https://github.com/solana-labs/solana-web3.js/commit/125fc1540cfbc0a4afdba5aabac0884c750e58c1)]:
    - @solana/errors@2.0.0
    - @solana/transactions@2.0.0
    - @solana/addresses@2.0.0
    - @solana/keys@2.0.0
    - @solana/signers@2.0.0
    - @solana/promises@2.0.0

## 2.0.0-rc.4

### Patch Changes

- Updated dependencies [[`2798061`](https://github.com/solana-labs/solana-web3.js/commit/27980617e4f8d34dbc7b6da4507e4bca68a68090)]:
    - @solana/errors@2.0.0-rc.4
    - @solana/addresses@2.0.0-rc.4
    - @solana/keys@2.0.0-rc.4
    - @solana/signers@2.0.0-rc.4
    - @solana/transactions@2.0.0-rc.4
    - @solana/promises@2.0.0-rc.4

## 2.0.0-rc.3

### Patch Changes

- Updated dependencies []:
    - @solana/addresses@2.0.0-rc.3
    - @solana/errors@2.0.0-rc.3
    - @solana/keys@2.0.0-rc.3
    - @solana/promises@2.0.0-rc.3
    - @solana/signers@2.0.0-rc.3
    - @solana/transactions@2.0.0-rc.3

## 2.0.0-rc.2

### Patch Changes

- [#3137](https://github.com/solana-labs/solana-web3.js/pull/3137) [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a) Thanks [@mcintyre94](https://github.com/mcintyre94)! - The build is now compatible with the Vercel Edge runtime and Cloudflare Workers through the addition of `edge-light` and `workerd` to the package exports.

- Updated dependencies [[`292487d`](https://github.com/solana-labs/solana-web3.js/commit/292487da00ee57350e8faf49ccf961203aed6403), [`38faba0`](https://github.com/solana-labs/solana-web3.js/commit/38faba05fab479ddbd95d0e211744d203f8aa823), [`fd72c2e`](https://github.com/solana-labs/solana-web3.js/commit/fd72c2ed1edad488318fa5d3e285f04852f4210a), [`4decebb`](https://github.com/solana-labs/solana-web3.js/commit/4decebb9b619972f49c740323b59cf470696e105), [`d4965ec`](https://github.com/solana-labs/solana-web3.js/commit/d4965ece9abaf81e3006442db15f3f77d89a622c), [`0158b31`](https://github.com/solana-labs/solana-web3.js/commit/0158b3181ed96996f269f3bff689f76411e460b3)]:
    - @solana/addresses@2.0.0-rc.2
    - @solana/errors@2.0.0-rc.2
    - @solana/transactions@2.0.0-rc.2
    - @solana/promises@2.0.0-rc.2
    - @solana/signers@2.0.0-rc.2
    - @solana/keys@2.0.0-rc.2

## 2.0.0-rc.1

### Patch Changes

- Updated dependencies [[`7d310f6`](https://github.com/solana-labs/solana-web3.js/commit/7d310f6f9cd7d02fca4d6f8e311b857c9dd84e61), [`1ad523d`](https://github.com/solana-labs/solana-web3.js/commit/1ad523dc5792d9152a66e9dc2b83294e3eba4db0), [`b4bf318`](https://github.com/solana-labs/solana-web3.js/commit/b4bf318d7d4bdd639e4c126c70350993a8540fe8), [`f2bb4e8`](https://github.com/solana-labs/solana-web3.js/commit/f2bb4e8c7f7efd049cb1c3810291c99e9293c25d), [`f9a8446`](https://github.com/solana-labs/solana-web3.js/commit/f9a84460670a97d4ab6514b28fe0d29c6fac3302)]:
    - @solana/keys@2.0.0-rc.1
    - @solana/signers@2.0.0-rc.1
    - @solana/promises@2.0.0-rc.1
    - @solana/transactions@2.0.0-rc.1
    - @solana/addresses@2.0.0-rc.1
    - @solana/errors@2.0.0-rc.1

## 2.0.0-rc.0

### Minor Changes

- [#2928](https://github.com/solana-labs/solana-web3.js/pull/2928) [`bac3747`](https://github.com/solana-labs/solana-web3.js/commit/bac37479dcfad3da86ccd01da5095759f449eb3d) Thanks [@steveluscher](https://github.com/steveluscher)! - Added a `useSignIn` hook that, given a `UiWallet` or `UiWalletAccount`, returns a function that you can call to trigger a wallet's [&lsquo;Sign In With Solana&rsquo;](https://phantom.app/learn/developers/sign-in-with-solana) feature.

    #### Example

    ```tsx
    import { useSignIn } from '@solana/react';

    function SignInButton({ wallet }) {
        const csrfToken = useCsrfToken();
        const signIn = useSignIn(wallet);
        return (
            <button
                onClick={async () => {
                    try {
                        const { account, signedMessage, signature } = await signIn({
                            requestId: csrfToken,
                        });
                        // Authenticate the user, typically on the server, by verifying that
                        // `signedMessage` was signed by the person who holds the private key for
                        // `account.publicKey`.
                        //
                        // Authorize the user, also on the server, by decoding `signedMessage` as the
                        // text of a Sign In With Solana message, verifying that it was not modified
                        // from the values your application expects, and that its content is sufficient
                        // to grant them access.
                        window.alert(`You are now signed in with the address ${account.address}`);
                    } catch (e) {
                        console.error('Failed to sign in', e);
                    }
                }}
            >
                Sign In
            </button>
        );
    }
    ```

### Patch Changes

- Updated dependencies [[`677a9c4`](https://github.com/solana-labs/solana-web3.js/commit/677a9c4eb88a8ac6a9ede8d82f367c5ac8d69ff4)]:
    - @solana/errors@2.0.0-rc.0
    - @solana/signers@2.0.0-rc.0
    - @solana/transactions@2.0.0-rc.0
    - @solana/addresses@2.0.0-rc.0
    - @solana/keys@2.0.0-rc.0

## 2.0.0-preview.4

### Patch Changes

- [#2795](https://github.com/solana-labs/solana-web3.js/pull/2795) [`ce876d9`](https://github.com/solana-labs/solana-web3.js/commit/ce876d99f04d539292abd810acd77a319c52f50d) Thanks [@steveluscher](https://github.com/steveluscher)! - Added React hooks to which you can pass a Wallet Standard `UiWalletAccount` and obtain a `MessageModifyingSigner`, `TransactionModifyingSigner`, or `TransactionSendingSigner` for use in constructing, signing, and sending Solana transactions and messages

- [#2772](https://github.com/solana-labs/solana-web3.js/pull/2772) [`8fe4551`](https://github.com/solana-labs/solana-web3.js/commit/8fe4551217a3ad8bfdcd1609ac7b23e8fd044c72) Thanks [@steveluscher](https://github.com/steveluscher)! - Added a series of React hooks to which you can pass a Wallet Standard `UiWalletAccount` to extract its `signMessage`, `signTransaction`, and `signAndSendTransaction` features

- Updated dependencies [[`4f19842`](https://github.com/solana-labs/solana-web3.js/commit/4f198423997d28d927f982333d268e19940656df), [`cec9048`](https://github.com/solana-labs/solana-web3.js/commit/cec9048b2f83535df7e499db5488c336981dfb5a), [`be36bab`](https://github.com/solana-labs/solana-web3.js/commit/be36babd752b1c987a2f53b4ff83ac8c045a3418), [`cb49bfa`](https://github.com/solana-labs/solana-web3.js/commit/cb49bfa28f412376a41e758eeda59e7e90983147), [`367b8ad`](https://github.com/solana-labs/solana-web3.js/commit/367b8ad0cce55a916abfb0125f36b6e844333b2b), [`22a34aa`](https://github.com/solana-labs/solana-web3.js/commit/22a34aa08d1be7e9b43ccfea94a99eaa2694e491)]:
    - @solana/errors@2.0.0-preview.4
    - @solana/signers@2.0.0-preview.4
    - @solana/keys@2.0.0-preview.4
    - @solana/transactions@2.0.0-preview.4
    - @solana/addresses@2.0.0-preview.4

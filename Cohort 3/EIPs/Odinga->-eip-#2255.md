 EIP-2255: Wallet Permissions System
An interface to restrict access to sensitive methods
Authors 	Dan Finlay (@danfinlay), Erik Marks (@rekmarks), Gavin John (@Pandapip1)
Created 	2019-08-22

 Abstract

This EIP adds two new wallet-namespaced RPC endpoints, wallet_getPermissions and wallet_requestPermissions, providing a standard interface for requesting and checking permissions.

Motivation 
Crypto wallets require users to approve every action, ensuring security but causing friction. A better approach would be a single permissions request, similar to OAuth2 (e.g., "Log in with Facebook/Apple"), improving user experience while maintaining security.

Web3 apps often ask for multiple permissions (e.g., revealing wallet addresses, switching networks, signing transactions). Instead, these could be consolidated into a single, human-readable permissions prompt during sign-in, with users able to approve, reject, or modify each request as needed.

 Specification 
This proposal introduces two new methods for web3 wallets to improve permission management:
wallet_getPermissions – Retrieves the current permissions granted to a dapp.
Returns a list of Permission objects, which include:
Invoker (the requesting website).
ParentCapability (the method being permitted, e.g., eth_accounts).
Caveats (restrictions applied to the permission).
wallet_requestPermissions – Allows dapps to request new permissions from the user.
Takes a PermissionRequest object specifying the method and any restrictions.
Returns a RequestedPermission object, including the requested method and an optional timestamp.
If a request is denied, it throws an error (code 4001).

Why This Matters
Current wallets require user consent for every action, which can be inconvenient.
This new system allows broader, human-readable permissions, improving usability while maintaining security.
uture expansion could allow sites to request accounts with specific abilities (e.g., ensuring compatibility with certain wallets).
 
Additional information
EIP-2255
Ethereum Magicians blog



# Solidity API

## AdminControl

### _admins

```solidity
struct EnumerableSet.AddressSet _admins
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### adminRequired

```solidity
modifier adminRequired()
```

_Only allows approved admins to call the specified function_

### getAdmins

```solidity
function getAdmins() external view returns (address[] admins)
```

_See {IAdminControl-getAdmins}._

### approveAdmin

```solidity
function approveAdmin(address admin) external
```

_See {IAdminControl-approveAdmin}._

### revokeAdmin

```solidity
function revokeAdmin(address admin) external
```

_See {IAdminControl-revokeAdmin}._

### isAdmin

```solidity
function isAdmin(address admin) public view returns (bool)
```

_See {IAdminControl-isAdmin}._

## AdminControlUpgradeable

### _admins

```solidity
struct EnumerableSet.AddressSet _admins
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### adminRequired

```solidity
modifier adminRequired()
```

_Only allows approved admins to call the specified function_

### getAdmins

```solidity
function getAdmins() external view returns (address[] admins)
```

_See {IAdminControl-getAdmins}._

### approveAdmin

```solidity
function approveAdmin(address admin) external
```

_See {IAdminControl-approveAdmin}._

### revokeAdmin

```solidity
function revokeAdmin(address admin) external
```

_See {IAdminControl-revokeAdmin}._

### isAdmin

```solidity
function isAdmin(address admin) public view returns (bool)
```

_See {IAdminControl-isAdmin}._

## IAdminControl

_Interface for admin control_

### AdminApproved

```solidity
event AdminApproved(address account, address sender)
```

### AdminRevoked

```solidity
event AdminRevoked(address account, address sender)
```

### getAdmins

```solidity
function getAdmins() external view returns (address[])
```

_gets address of all admins_

### approveAdmin

```solidity
function approveAdmin(address admin) external
```

_add an admin.  Can only be called by contract owner._

### revokeAdmin

```solidity
function revokeAdmin(address admin) external
```

_remove an admin.  Can only be called by contract owner._

### isAdmin

```solidity
function isAdmin(address admin) external view returns (bool)
```

_checks whether or not given address is an admin
Returns True if they are_

## OwnableUpgradeable

_Contract module which provides a basic access control mechanism, where
there is an account (an owner) that can be granted exclusive access to
specific functions.

By default, the owner account will be the one that deploys the contract. This
can later be changed with {transferOwnership}.

This module is used through inheritance. It will make available the modifier
&#x60;onlyOwner&#x60;, which can be applied to your functions to restrict their use to
the owner._

### _owner

```solidity
address _owner
```

### OwnershipTransferred

```solidity
event OwnershipTransferred(address previousOwner, address newOwner)
```

### __Ownable_init

```solidity
function __Ownable_init() internal
```

_Initializes the contract setting the deployer as the initial owner._

### __Ownable_init_unchained

```solidity
function __Ownable_init_unchained() internal
```

### owner

```solidity
function owner() public view virtual returns (address)
```

_Returns the address of the current owner._

### onlyOwner

```solidity
modifier onlyOwner()
```

_Throws if called by any account other than the owner._

### renounceOwnership

```solidity
function renounceOwnership() public virtual
```

_Leaves the contract without owner. It will not be possible to call
&#x60;onlyOwner&#x60; functions anymore. Can only be called by the current owner.

NOTE: Renouncing ownership will leave the contract without an owner,
thereby removing any functionality that is only available to the owner._

### transferOwnership

```solidity
function transferOwnership(address newOwner) public virtual
```

_Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;).
Can only be called by the current owner._

### _transferOwnership

```solidity
function _transferOwnership(address newOwner) internal virtual
```

_Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;).
Internal function without access restriction._

### __gap

```solidity
uint256[49] __gap
```

_This empty reserved space is put in place to allow future versions to add new
variables without shifting down storage in the inheritance chain.
See https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps_

## Initializable

_This is a base contract to aid in writing upgradeable contracts, or any kind of contract that will be deployed
behind a proxy. Since proxied contracts do not make use of a constructor, it&#x27;s common to move constructor logic to an
external initializer function, usually called &#x60;initialize&#x60;. It then becomes necessary to protect this initializer
function so it can only be called once. The {initializer} modifier provided by this contract will have this effect.

The initialization functions use a version number. Once a version number is used, it is consumed and cannot be
reused. This mechanism prevents re-execution of each &quot;step&quot; but allows the creation of new initialization steps in
case an upgrade adds a module that needs to be initialized.

For example:

[.hljs-theme-light.nopadding]
&#x60;&#x60;&#x60;
contract MyToken is ERC20Upgradeable {
    function initialize() initializer public {
        __ERC20_init(&quot;MyToken&quot;, &quot;MTK&quot;);
    }
}
contract MyTokenV2 is MyToken, ERC20PermitUpgradeable {
    function initializeV2() reinitializer(2) public {
        __ERC20Permit_init(&quot;MyToken&quot;);
    }
}
&#x60;&#x60;&#x60;

TIP: To avoid leaving the proxy in an uninitialized state, the initializer function should be called as early as
possible by providing the encoded function call as the &#x60;_data&#x60; argument to {ERC1967Proxy-constructor}.

CAUTION: When used with inheritance, manual care must be taken to not invoke a parent initializer twice, or to ensure
that all initializers are idempotent. This is not verified automatically as constructors are by Solidity.

[CAUTION]
&#x3D;&#x3D;&#x3D;&#x3D;
Avoid leaving a contract uninitialized.

An uninitialized contract can be taken over by an attacker. This applies to both a proxy and its implementation
contract, which may impact the proxy. To prevent the implementation contract from being used, you should invoke
the {_disableInitializers} function in the constructor to automatically lock it when it is deployed:

[.hljs-theme-light.nopadding]
&#x60;&#x60;&#x60;
/// @custom:oz-upgrades-unsafe-allow constructor
constructor() {
    _disableInitializers();
}
&#x60;&#x60;&#x60;
&#x3D;&#x3D;&#x3D;&#x3D;_

### _initialized

```solidity
uint8 _initialized
```

_Indicates that the contract has been initialized._

### _initializing

```solidity
bool _initializing
```

_Indicates that the contract is in the process of being initialized._

### Initialized

```solidity
event Initialized(uint8 version)
```

_Triggered when the contract has been initialized or reinitialized._

### initializer

```solidity
modifier initializer()
```

_A modifier that defines a protected initializer function that can be invoked at most once. In its scope,
&#x60;onlyInitializing&#x60; functions can be used to initialize parent contracts. Equivalent to &#x60;reinitializer(1)&#x60;._

### reinitializer

```solidity
modifier reinitializer(uint8 version)
```

_A modifier that defines a protected reinitializer function that can be invoked at most once, and only if the
contract hasn&#x27;t been initialized to a greater version before. In its scope, &#x60;onlyInitializing&#x60; functions can be
used to initialize parent contracts.

&#x60;initializer&#x60; is equivalent to &#x60;reinitializer(1)&#x60;, so a reinitializer may be used after the original
initialization step. This is essential to configure modules that are added through upgrades and that require
initialization.

Note that versions can jump in increments greater than 1; this implies that if multiple reinitializers coexist in
a contract, executing them in the right order is up to the developer or operator._

### onlyInitializing

```solidity
modifier onlyInitializing()
```

_Modifier to protect an initialization function so that it can only be invoked by functions with the
{initializer} and {reinitializer} modifiers, directly or indirectly._

### _disableInitializers

```solidity
function _disableInitializers() internal virtual
```

_Locks the contract, preventing any future reinitialization. This cannot be part of an initializer call.
Calling this in the constructor of a contract will prevent that contract from being initialized or reinitialized
to any version. It is recommended to use this to lock implementation contracts that are designed to be called
through proxies._

### _setInitializedVersion

```solidity
function _setInitializedVersion(uint8 version) private returns (bool)
```

## ERC1155Upgradeable

_Implementation of the basic standard multi-token.
See https://eips.ethereum.org/EIPS/eip-1155
Originally based on code by Enjin: https://github.com/enjin/erc-1155

_Available since v3.1.__

### _balances

```solidity
mapping(uint256 &#x3D;&gt; mapping(address &#x3D;&gt; uint256)) _balances
```

### _operatorApprovals

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; bool)) _operatorApprovals
```

### _uri

```solidity
string _uri
```

### __ERC1155_init

```solidity
function __ERC1155_init(string uri_) internal
```

_See {_setURI}._

### __ERC1155_init_unchained

```solidity
function __ERC1155_init_unchained(string uri_) internal
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### uri

```solidity
function uri(uint256) public view virtual returns (string)
```

_See {IERC1155MetadataURI-uri}.

This implementation returns the same URI for *all* token types. It relies
on the token type ID substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

Clients calling this function must replace the &#x60;\{id\}&#x60; substring with the
actual token type ID._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) public view virtual returns (uint256)
```

_See {IERC1155-balanceOf}.

Requirements:

- &#x60;account&#x60; cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) public view virtual returns (uint256[])
```

_See {IERC1155-balanceOfBatch}.

Requirements:

- &#x60;accounts&#x60; and &#x60;ids&#x60; must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) public virtual
```

_See {IERC1155-setApprovalForAll}._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) public view virtual returns (bool)
```

_See {IERC1155-isApprovedForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) public virtual
```

_See {IERC1155-safeTransferFrom}._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) public virtual
```

_See {IERC1155-safeBatchTransferFrom}._

### _safeTransferFrom

```solidity
function _safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Transfers &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- &#x60;from&#x60; must have a balance of tokens of type &#x60;id&#x60; of at least &#x60;amount&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _safeBatchTransferFrom

```solidity
function _safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _setURI

```solidity
function _setURI(string newuri) internal virtual
```

_Sets a new URI for all token types, by relying on the token type ID
substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

By this mechanism, any occurrence of the &#x60;\{id\}&#x60; substring in either the
URI or any of the amounts in the JSON file at said URI will be replaced by
clients with the token type ID.

For example, the &#x60;https://token-cdn-domain/\{id\}.json&#x60; URI would be
interpreted by clients as
&#x60;https://token-cdn-domain/000000000000000000000000000000000000000000000000000000000004cce0.json&#x60;
for token type ID 0x4cce0.

See {uri}.

Because these URIs cannot be meaningfully represented by the {URI} event,
this function emits no events._

### _mint

```solidity
function _mint(address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Creates &#x60;amount&#x60; tokens of token type &#x60;id&#x60;, and assigns them to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_mint}.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _burn

```solidity
function _burn(address from, uint256 id, uint256 amount) internal virtual
```

_Destroys &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60;

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;from&#x60; must have at least &#x60;amount&#x60; tokens of token type &#x60;id&#x60;._

### _burnBatch

```solidity
function _burnBatch(address from, uint256[] ids, uint256[] amounts) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_burn}.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length._

### _setApprovalForAll

```solidity
function _setApprovalForAll(address owner, address operator, bool approved) internal virtual
```

_Approve &#x60;operator&#x60; to operate on all of &#x60;owner&#x60; tokens

Emits a {ApprovalForAll} event._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning, as well as batched variants.

The same hook is called on both single and batched variants. For single
transfers, the length of the &#x60;id&#x60; and &#x60;amount&#x60; arrays will be 1.

Calling conditions (for each &#x60;id&#x60; and &#x60;amount&#x60; pair):

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens
of token type &#x60;id&#x60; will be  transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;amount&#x60; tokens of token type &#x60;id&#x60; will be minted
for &#x60;to&#x60;.
- when &#x60;to&#x60; is zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens of token type &#x60;id&#x60;
will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.
- &#x60;ids&#x60; and &#x60;amounts&#x60; have the same, non-zero length.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _afterTokenTransfer

```solidity
function _afterTokenTransfer(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_Hook that is called after any token transfer. This includes minting
and burning, as well as batched variants.

The same hook is called on both single and batched variants. For single
transfers, the length of the &#x60;id&#x60; and &#x60;amount&#x60; arrays will be 1.

Calling conditions (for each &#x60;id&#x60; and &#x60;amount&#x60; pair):

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens
of token type &#x60;id&#x60; will be  transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;amount&#x60; tokens of token type &#x60;id&#x60; will be minted
for &#x60;to&#x60;.
- when &#x60;to&#x60; is zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens of token type &#x60;id&#x60;
will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.
- &#x60;ids&#x60; and &#x60;amounts&#x60; have the same, non-zero length.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _doSafeTransferAcceptanceCheck

```solidity
function _doSafeTransferAcceptanceCheck(address operator, address from, address to, uint256 id, uint256 amount, bytes data) private
```

### _doSafeBatchTransferAcceptanceCheck

```solidity
function _doSafeBatchTransferAcceptanceCheck(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) private
```

### _asSingletonArray

```solidity
function _asSingletonArray(uint256 element) private pure returns (uint256[])
```

### __gap

```solidity
uint256[47] __gap
```

_This empty reserved space is put in place to allow future versions to add new
variables without shifting down storage in the inheritance chain.
See https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps_

## IERC1155ReceiverUpgradeable

__Available since v3.1.__

### onERC1155Received

```solidity
function onERC1155Received(address operator, address from, uint256 id, uint256 value, bytes data) external returns (bytes4)
```

_Handles the receipt of a single ERC1155 token type. This function is
called at the end of a &#x60;safeTransferFrom&#x60; after the balance has been updated.

NOTE: To accept the transfer, this must return
&#x60;bytes4(keccak256(&quot;onERC1155Received(address,address,uint256,uint256,bytes)&quot;))&#x60;
(i.e. 0xf23a6e61, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| id | uint256 | The ID of the token being transferred |
| value | uint256 | The amount of tokens being transferred |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | &#x60;bytes4(keccak256(&quot;onERC1155Received(address,address,uint256,uint256,bytes)&quot;))&#x60; if transfer is allowed |

### onERC1155BatchReceived

```solidity
function onERC1155BatchReceived(address operator, address from, uint256[] ids, uint256[] values, bytes data) external returns (bytes4)
```

_Handles the receipt of a multiple ERC1155 token types. This function
is called at the end of a &#x60;safeBatchTransferFrom&#x60; after the balances have
been updated.

NOTE: To accept the transfer(s), this must return
&#x60;bytes4(keccak256(&quot;onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)&quot;))&#x60;
(i.e. 0xbc197c81, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the batch transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| ids | uint256[] | An array containing ids of each token being transferred (order and length must match values array) |
| values | uint256[] | An array containing amounts of each token being transferred (order and length must match ids array) |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | &#x60;bytes4(keccak256(&quot;onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)&quot;))&#x60; if transfer is allowed |

## IERC1155Upgradeable

_Required interface of an ERC1155 compliant contract, as defined in the
https://eips.ethereum.org/EIPS/eip-1155[EIP].

_Available since v3.1.__

### TransferSingle

```solidity
event TransferSingle(address operator, address from, address to, uint256 id, uint256 value)
```

_Emitted when &#x60;value&#x60; tokens of token type &#x60;id&#x60; are transferred from &#x60;from&#x60; to &#x60;to&#x60; by &#x60;operator&#x60;._

### TransferBatch

```solidity
event TransferBatch(address operator, address from, address to, uint256[] ids, uint256[] values)
```

_Equivalent to multiple {TransferSingle} events, where &#x60;operator&#x60;, &#x60;from&#x60; and &#x60;to&#x60; are the same for all
transfers._

### ApprovalForAll

```solidity
event ApprovalForAll(address account, address operator, bool approved)
```

_Emitted when &#x60;account&#x60; grants or revokes permission to &#x60;operator&#x60; to transfer their tokens, according to
&#x60;approved&#x60;._

### URI

```solidity
event URI(string value, uint256 id)
```

_Emitted when the URI for token type &#x60;id&#x60; changes to &#x60;value&#x60;, if it is a non-programmatic URI.

If an {URI} event was emitted for &#x60;id&#x60;, the standard
https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[guarantees] that &#x60;value&#x60; will equal the value
returned by {IERC1155MetadataURI-uri}._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) external view returns (uint256)
```

_Returns the amount of tokens of token type &#x60;id&#x60; owned by &#x60;account&#x60;.

Requirements:

- &#x60;account&#x60; cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) external view returns (uint256[])
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {balanceOf}.

Requirements:

- &#x60;accounts&#x60; and &#x60;ids&#x60; must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) external
```

_Grants or revokes permission to &#x60;operator&#x60; to transfer the caller&#x27;s tokens, according to &#x60;approved&#x60;,

Emits an {ApprovalForAll} event.

Requirements:

- &#x60;operator&#x60; cannot be the caller._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) external view returns (bool)
```

_Returns true if &#x60;operator&#x60; is approved to transfer &#x60;&#x60;account&#x60;&#x60;&#x27;s tokens.

See {setApprovalForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) external
```

_Transfers &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- If the caller is not &#x60;from&#x60;, it must be have been approved to spend &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens via {setApprovalForAll}.
- &#x60;from&#x60; must have a balance of tokens of type &#x60;id&#x60; of at least &#x60;amount&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) external
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

## IERC1155MetadataURIUpgradeable

_Interface of the optional ERC1155MetadataExtension interface, as defined
in the https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[EIP].

_Available since v3.1.__

### uri

```solidity
function uri(uint256 id) external view returns (string)
```

_Returns the URI for token type &#x60;id&#x60;.

If the &#x60;\{id\}&#x60; substring is present in the URI, it must be replaced by
clients with the actual token type ID._

## ERC721Upgradeable

_Implementation of https://eips.ethereum.org/EIPS/eip-721[ERC721] Non-Fungible Token Standard, including
the Metadata extension, but not including the Enumerable extension, which is available separately as
{ERC721Enumerable}._

### _name

```solidity
string _name
```

### _symbol

```solidity
string _symbol
```

### _owners

```solidity
mapping(uint256 &#x3D;&gt; address) _owners
```

### _balances

```solidity
mapping(address &#x3D;&gt; uint256) _balances
```

### _tokenApprovals

```solidity
mapping(uint256 &#x3D;&gt; address) _tokenApprovals
```

### _operatorApprovals

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; bool)) _operatorApprovals
```

### __ERC721_init

```solidity
function __ERC721_init(string name_, string symbol_) internal
```

_Initializes the contract by setting a &#x60;name&#x60; and a &#x60;symbol&#x60; to the token collection._

### __ERC721_init_unchained

```solidity
function __ERC721_init_unchained(string name_, string symbol_) internal
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### balanceOf

```solidity
function balanceOf(address owner) public view virtual returns (uint256)
```

_See {IERC721-balanceOf}._

### ownerOf

```solidity
function ownerOf(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721-ownerOf}._

### name

```solidity
function name() public view virtual returns (string)
```

_See {IERC721Metadata-name}._

### symbol

```solidity
function symbol() public view virtual returns (string)
```

_See {IERC721Metadata-symbol}._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

### _baseURI

```solidity
function _baseURI() internal view virtual returns (string)
```

_Base URI for computing {tokenURI}. If set, the resulting URI for each
token will be the concatenation of the &#x60;baseURI&#x60; and the &#x60;tokenId&#x60;. Empty
by default, can be overridden in child contracts._

### approve

```solidity
function approve(address to, uint256 tokenId) public virtual
```

_See {IERC721-approve}._

### getApproved

```solidity
function getApproved(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721-getApproved}._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) public virtual
```

_See {IERC721-setApprovalForAll}._

### isApprovedForAll

```solidity
function isApprovedForAll(address owner, address operator) public view virtual returns (bool)
```

_See {IERC721-isApprovedForAll}._

### transferFrom

```solidity
function transferFrom(address from, address to, uint256 tokenId) public virtual
```

_See {IERC721-transferFrom}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId) public virtual
```

_See {IERC721-safeTransferFrom}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId, bytes _data) public virtual
```

_See {IERC721-safeTransferFrom}._

### _safeTransfer

```solidity
function _safeTransfer(address from, address to, uint256 tokenId, bytes _data) internal virtual
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;, checking first that contract recipients
are aware of the ERC721 protocol to prevent tokens from being forever locked.

&#x60;_data&#x60; is additional data, it has no specified format and it is sent in call to &#x60;to&#x60;.

This internal function is equivalent to {safeTransferFrom}, and can be used to e.g.
implement alternative mechanisms to perform token transfer, such as signature-based.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### _exists

```solidity
function _exists(uint256 tokenId) internal view virtual returns (bool)
```

_Returns whether &#x60;tokenId&#x60; exists.

Tokens can be managed by their owner or approved accounts via {approve} or {setApprovalForAll}.

Tokens start existing when they are minted (&#x60;_mint&#x60;),
and stop existing when they are burned (&#x60;_burn&#x60;)._

### _isApprovedOrOwner

```solidity
function _isApprovedOrOwner(address spender, uint256 tokenId) internal view virtual returns (bool)
```

_Returns whether &#x60;spender&#x60; is allowed to manage &#x60;tokenId&#x60;.

Requirements:

- &#x60;tokenId&#x60; must exist._

### _safeMint

```solidity
function _safeMint(address to, uint256 tokenId) internal virtual
```

_Safely mints &#x60;tokenId&#x60; and transfers it to &#x60;to&#x60;.

Requirements:

- &#x60;tokenId&#x60; must not exist.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### _safeMint

```solidity
function _safeMint(address to, uint256 tokenId, bytes _data) internal virtual
```

_Same as {xref-ERC721-_safeMint-address-uint256-}[&#x60;_safeMint&#x60;], with an additional &#x60;data&#x60; parameter which is
forwarded in {IERC721Receiver-onERC721Received} to contract recipients._

### _mint

```solidity
function _mint(address to, uint256 tokenId) internal virtual
```

_Mints &#x60;tokenId&#x60; and transfers it to &#x60;to&#x60;.

WARNING: Usage of this method is discouraged, use {_safeMint} whenever possible

Requirements:

- &#x60;tokenId&#x60; must not exist.
- &#x60;to&#x60; cannot be the zero address.

Emits a {Transfer} event._

### _burn

```solidity
function _burn(uint256 tokenId) internal virtual
```

_Destroys &#x60;tokenId&#x60;.
The approval is cleared when the token is burned.

Requirements:

- &#x60;tokenId&#x60; must exist.

Emits a {Transfer} event._

### _transfer

```solidity
function _transfer(address from, address to, uint256 tokenId) internal virtual
```

_Transfers &#x60;tokenId&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.
 As opposed to {transferFrom}, this imposes no restrictions on msg.sender.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must be owned by &#x60;from&#x60;.

Emits a {Transfer} event._

### _approve

```solidity
function _approve(address to, uint256 tokenId) internal virtual
```

_Approve &#x60;to&#x60; to operate on &#x60;tokenId&#x60;

Emits a {Approval} event._

### _setApprovalForAll

```solidity
function _setApprovalForAll(address owner, address operator, bool approved) internal virtual
```

_Approve &#x60;operator&#x60; to operate on all of &#x60;owner&#x60; tokens

Emits a {ApprovalForAll} event._

### _checkOnERC721Received

```solidity
function _checkOnERC721Received(address from, address to, uint256 tokenId, bytes _data) private returns (bool)
```

_Internal function to invoke {IERC721Receiver-onERC721Received} on a target address.
The call is not executed if the target address is not a contract._

| Name | Type | Description |
| ---- | ---- | ----------- |
| from | address | address representing the previous owner of the given token ID |
| to | address | target address that will receive the tokens |
| tokenId | uint256 | uint256 ID of the token to be transferred |
| _data | bytes | bytes optional data to send along with the call |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bool | bool whether the call correctly returned the expected magic value |

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _afterTokenTransfer

```solidity
function _afterTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called after any transfer of tokens. This includes
minting and burning.

Calling conditions:

- when &#x60;from&#x60; and &#x60;to&#x60; are both non-zero.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### __gap

```solidity
uint256[44] __gap
```

_This empty reserved space is put in place to allow future versions to add new
variables without shifting down storage in the inheritance chain.
See https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps_

## IERC721ReceiverUpgradeable

_Interface for any contract that wants to support safeTransfers
from ERC721 asset contracts._

### onERC721Received

```solidity
function onERC721Received(address operator, address from, uint256 tokenId, bytes data) external returns (bytes4)
```

_Whenever an {IERC721} &#x60;tokenId&#x60; token is transferred to this contract via {IERC721-safeTransferFrom}
by &#x60;operator&#x60; from &#x60;from&#x60;, this function is called.

It must return its Solidity selector to confirm the token transfer.
If any other value is returned or the interface is not implemented by the recipient, the transfer will be reverted.

The selector can be obtained in Solidity with &#x60;IERC721Receiver.onERC721Received.selector&#x60;._

## IERC721Upgradeable

_Required interface of an ERC721 compliant contract._

### Transfer

```solidity
event Transfer(address from, address to, uint256 tokenId)
```

_Emitted when &#x60;tokenId&#x60; token is transferred from &#x60;from&#x60; to &#x60;to&#x60;._

### Approval

```solidity
event Approval(address owner, address approved, uint256 tokenId)
```

_Emitted when &#x60;owner&#x60; enables &#x60;approved&#x60; to manage the &#x60;tokenId&#x60; token._

### ApprovalForAll

```solidity
event ApprovalForAll(address owner, address operator, bool approved)
```

_Emitted when &#x60;owner&#x60; enables or disables (&#x60;approved&#x60;) &#x60;operator&#x60; to manage all of its assets._

### balanceOf

```solidity
function balanceOf(address owner) external view returns (uint256 balance)
```

_Returns the number of tokens in &#x60;&#x60;owner&#x60;&#x60;&#x27;s account._

### ownerOf

```solidity
function ownerOf(uint256 tokenId) external view returns (address owner)
```

_Returns the owner of the &#x60;tokenId&#x60; token.

Requirements:

- &#x60;tokenId&#x60; must exist._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId, bytes data) external
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be approved to move this token by either {approve} or {setApprovalForAll}.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId) external
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;, checking first that contract recipients
are aware of the ERC721 protocol to prevent tokens from being forever locked.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be have been allowed to move this token by either {approve} or {setApprovalForAll}.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### transferFrom

```solidity
function transferFrom(address from, address to, uint256 tokenId) external
```

_Transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;.

WARNING: Usage of this method is discouraged, use {safeTransferFrom} whenever possible.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be approved to move this token by either {approve} or {setApprovalForAll}.

Emits a {Transfer} event._

### approve

```solidity
function approve(address to, uint256 tokenId) external
```

_Gives permission to &#x60;to&#x60; to transfer &#x60;tokenId&#x60; token to another account.
The approval is cleared when the token is transferred.

Only a single account can be approved at a time, so approving the zero address clears previous approvals.

Requirements:

- The caller must own the token or be an approved operator.
- &#x60;tokenId&#x60; must exist.

Emits an {Approval} event._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool _approved) external
```

_Approve or remove &#x60;operator&#x60; as an operator for the caller.
Operators can call {transferFrom} or {safeTransferFrom} for any token owned by the caller.

Requirements:

- The &#x60;operator&#x60; cannot be the caller.

Emits an {ApprovalForAll} event._

### getApproved

```solidity
function getApproved(uint256 tokenId) external view returns (address operator)
```

_Returns the account approved for &#x60;tokenId&#x60; token.

Requirements:

- &#x60;tokenId&#x60; must exist._

### isApprovedForAll

```solidity
function isApprovedForAll(address owner, address operator) external view returns (bool)
```

_Returns if the &#x60;operator&#x60; is allowed to manage all of the assets of &#x60;owner&#x60;.

See {setApprovalForAll}_

## IERC721MetadataUpgradeable

_See https://eips.ethereum.org/EIPS/eip-721_

### name

```solidity
function name() external view returns (string)
```

_Returns the token collection name._

### symbol

```solidity
function symbol() external view returns (string)
```

_Returns the token collection symbol._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) external view returns (string)
```

_Returns the Uniform Resource Identifier (URI) for &#x60;tokenId&#x60; token._

## AddressUpgradeable

_Collection of functions related to the address type_

### isContract

```solidity
function isContract(address account) internal view returns (bool)
```

_Returns true if &#x60;account&#x60; is a contract.

[IMPORTANT]
&#x3D;&#x3D;&#x3D;&#x3D;
It is unsafe to assume that an address for which this function returns
false is an externally-owned account (EOA) and not a contract.

Among others, &#x60;isContract&#x60; will return false for the following
types of addresses:

 - an externally-owned account
 - a contract in construction
 - an address where a contract will be created
 - an address where a contract lived, but was destroyed
&#x3D;&#x3D;&#x3D;&#x3D;

[IMPORTANT]
&#x3D;&#x3D;&#x3D;&#x3D;
You shouldn&#x27;t rely on &#x60;isContract&#x60; to protect against flash loan attacks!

Preventing calls from contracts is highly discouraged. It breaks composability, breaks support for smart wallets
like Gnosis Safe, and does not provide security since it can be circumvented by calling from a contract
constructor.
&#x3D;&#x3D;&#x3D;&#x3D;_

### sendValue

```solidity
function sendValue(address payable recipient, uint256 amount) internal
```

_Replacement for Solidity&#x27;s &#x60;transfer&#x60;: sends &#x60;amount&#x60; wei to
&#x60;recipient&#x60;, forwarding all available gas and reverting on errors.

https://eips.ethereum.org/EIPS/eip-1884[EIP1884] increases the gas cost
of certain opcodes, possibly making contracts go over the 2300 gas limit
imposed by &#x60;transfer&#x60;, making them unable to receive funds via
&#x60;transfer&#x60;. {sendValue} removes this limitation.

https://diligence.consensys.net/posts/2019/09/stop-using-soliditys-transfer-now/[Learn more].

IMPORTANT: because control is transferred to &#x60;recipient&#x60;, care must be
taken to not create reentrancy vulnerabilities. Consider using
{ReentrancyGuard} or the
https://solidity.readthedocs.io/en/v0.5.11/security-considerations.html#use-the-checks-effects-interactions-pattern[checks-effects-interactions pattern]._

### functionCall

```solidity
function functionCall(address target, bytes data) internal returns (bytes)
```

_Performs a Solidity function call using a low level &#x60;call&#x60;. A
plain &#x60;call&#x60; is an unsafe replacement for a function call: use this
function instead.

If &#x60;target&#x60; reverts with a revert reason, it is bubbled up by this
function (like regular Solidity function calls).

Returns the raw returned data. To convert to the expected return value,
use https://solidity.readthedocs.io/en/latest/units-and-global-variables.html?highlight&#x3D;abi.decode#abi-encoding-and-decoding-functions[&#x60;abi.decode&#x60;].

Requirements:

- &#x60;target&#x60; must be a contract.
- calling &#x60;target&#x60; with &#x60;data&#x60; must not revert.

_Available since v3.1.__

### functionCall

```solidity
function functionCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;], but with
&#x60;errorMessage&#x60; as a fallback revert reason when &#x60;target&#x60; reverts.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;],
but also transferring &#x60;value&#x60; wei to &#x60;target&#x60;.

Requirements:

- the calling contract must have an ETH balance of at least &#x60;value&#x60;.
- the called Solidity function must be &#x60;payable&#x60;.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCallWithValue-address-bytes-uint256-}[&#x60;functionCallWithValue&#x60;], but
with &#x60;errorMessage&#x60; as a fallback revert reason when &#x60;target&#x60; reverts.

_Available since v3.1.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;],
but performing a static call.

_Available since v3.3.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data, string errorMessage) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-string-}[&#x60;functionCall&#x60;],
but performing a static call.

_Available since v3.3.__

### verifyCallResult

```solidity
function verifyCallResult(bool success, bytes returndata, string errorMessage) internal pure returns (bytes)
```

_Tool to verifies that a low level call was successful, and revert if it wasn&#x27;t, either by bubbling the
revert reason using the provided one.

_Available since v4.3.__

## ContextUpgradeable

_Provides information about the current execution context, including the
sender of the transaction and its data. While these are generally available
via msg.sender and msg.data, they should not be accessed in such a direct
manner, since when dealing with meta-transactions the account sending and
paying for execution may not be the actual sender (as far as an application
is concerned).

This contract is only required for intermediate, library-like contracts._

### __Context_init

```solidity
function __Context_init() internal
```

### __Context_init_unchained

```solidity
function __Context_init_unchained() internal
```

### _msgSender

```solidity
function _msgSender() internal view virtual returns (address)
```

### _msgData

```solidity
function _msgData() internal view virtual returns (bytes)
```

### __gap

```solidity
uint256[50] __gap
```

_This empty reserved space is put in place to allow future versions to add new
variables without shifting down storage in the inheritance chain.
See https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps_

## StringsUpgradeable

_String operations._

### _HEX_SYMBOLS

```solidity
bytes16 _HEX_SYMBOLS
```

### toString

```solidity
function toString(uint256 value) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; decimal representation._

### toHexString

```solidity
function toHexString(uint256 value) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; hexadecimal representation._

### toHexString

```solidity
function toHexString(uint256 value, uint256 length) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; hexadecimal representation with fixed length._

## ERC165Upgradeable

_Implementation of the {IERC165} interface.

Contracts that want to implement ERC165 should inherit from this contract and override {supportsInterface} to check
for the additional interface id that will be supported. For example:

&#x60;&#x60;&#x60;solidity
function supportsInterface(bytes4 interfaceId) public view virtual override returns (bool) {
    return interfaceId &#x3D;&#x3D; type(MyInterface).interfaceId || super.supportsInterface(interfaceId);
}
&#x60;&#x60;&#x60;

Alternatively, {ERC165Storage} provides an easier to use but more expensive implementation._

### __ERC165_init

```solidity
function __ERC165_init() internal
```

### __ERC165_init_unchained

```solidity
function __ERC165_init_unchained() internal
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### __gap

```solidity
uint256[50] __gap
```

_This empty reserved space is put in place to allow future versions to add new
variables without shifting down storage in the inheritance chain.
See https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps_

## IERC165Upgradeable

_Interface of the ERC165 standard, as defined in the
https://eips.ethereum.org/EIPS/eip-165[EIP].

Implementers can declare support of contract interfaces, which can then be
queried by others ({ERC165Checker}).

For an implementation, see {ERC165}._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) external view returns (bool)
```

_Returns true if this contract implements the interface defined by
&#x60;interfaceId&#x60;. See the corresponding
https://eips.ethereum.org/EIPS/eip-165#how-interfaces-are-identified[EIP section]
to learn more about how these ids are created.

This function call must use less than 30 000 gas._

## Ownable

_Contract module which provides a basic access control mechanism, where
there is an account (an owner) that can be granted exclusive access to
specific functions.

By default, the owner account will be the one that deploys the contract. This
can later be changed with {transferOwnership}.

This module is used through inheritance. It will make available the modifier
&#x60;onlyOwner&#x60;, which can be applied to your functions to restrict their use to
the owner._

### _owner

```solidity
address _owner
```

### OwnershipTransferred

```solidity
event OwnershipTransferred(address previousOwner, address newOwner)
```

### constructor

```solidity
constructor() internal
```

_Initializes the contract setting the deployer as the initial owner._

### owner

```solidity
function owner() public view virtual returns (address)
```

_Returns the address of the current owner._

### onlyOwner

```solidity
modifier onlyOwner()
```

_Throws if called by any account other than the owner._

### renounceOwnership

```solidity
function renounceOwnership() public virtual
```

_Leaves the contract without owner. It will not be possible to call
&#x60;onlyOwner&#x60; functions anymore. Can only be called by the current owner.

NOTE: Renouncing ownership will leave the contract without an owner,
thereby removing any functionality that is only available to the owner._

### transferOwnership

```solidity
function transferOwnership(address newOwner) public virtual
```

_Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;).
Can only be called by the current owner._

### _transferOwnership

```solidity
function _transferOwnership(address newOwner) internal virtual
```

_Transfers ownership of the contract to a new account (&#x60;newOwner&#x60;).
Internal function without access restriction._

## ReentrancyGuard

_Contract module that helps prevent reentrant calls to a function.

Inheriting from &#x60;ReentrancyGuard&#x60; will make the {nonReentrant} modifier
available, which can be applied to functions to make sure there are no nested
(reentrant) calls to them.

Note that because there is a single &#x60;nonReentrant&#x60; guard, functions marked as
&#x60;nonReentrant&#x60; may not call one another. This can be worked around by making
those functions &#x60;private&#x60;, and then adding &#x60;external&#x60; &#x60;nonReentrant&#x60; entry
points to them.

TIP: If you would like to learn more about reentrancy and alternative ways
to protect against it, check out our blog post
https://blog.openzeppelin.com/reentrancy-after-istanbul/[Reentrancy After Istanbul]._

### _NOT_ENTERED

```solidity
uint256 _NOT_ENTERED
```

### _ENTERED

```solidity
uint256 _ENTERED
```

### _status

```solidity
uint256 _status
```

### constructor

```solidity
constructor() internal
```

### nonReentrant

```solidity
modifier nonReentrant()
```

_Prevents a contract from calling itself, directly or indirectly.
Calling a &#x60;nonReentrant&#x60; function from another &#x60;nonReentrant&#x60;
function is not supported. It is possible to prevent this from happening
by making the &#x60;nonReentrant&#x60; function external, and making it call a
&#x60;private&#x60; function that does the actual work._

## ERC1155

_Implementation of the basic standard multi-token.
See https://eips.ethereum.org/EIPS/eip-1155
Originally based on code by Enjin: https://github.com/enjin/erc-1155

_Available since v3.1.__

### _balances

```solidity
mapping(uint256 &#x3D;&gt; mapping(address &#x3D;&gt; uint256)) _balances
```

### _operatorApprovals

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; bool)) _operatorApprovals
```

### _uri

```solidity
string _uri
```

### constructor

```solidity
constructor(string uri_) public
```

_See {_setURI}._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### uri

```solidity
function uri(uint256) public view virtual returns (string)
```

_See {IERC1155MetadataURI-uri}.

This implementation returns the same URI for *all* token types. It relies
on the token type ID substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

Clients calling this function must replace the &#x60;\{id\}&#x60; substring with the
actual token type ID._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) public view virtual returns (uint256)
```

_See {IERC1155-balanceOf}.

Requirements:

- &#x60;account&#x60; cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) public view virtual returns (uint256[])
```

_See {IERC1155-balanceOfBatch}.

Requirements:

- &#x60;accounts&#x60; and &#x60;ids&#x60; must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) public virtual
```

_See {IERC1155-setApprovalForAll}._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) public view virtual returns (bool)
```

_See {IERC1155-isApprovedForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) public virtual
```

_See {IERC1155-safeTransferFrom}._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) public virtual
```

_See {IERC1155-safeBatchTransferFrom}._

### _safeTransferFrom

```solidity
function _safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Transfers &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- &#x60;from&#x60; must have a balance of tokens of type &#x60;id&#x60; of at least &#x60;amount&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _safeBatchTransferFrom

```solidity
function _safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _setURI

```solidity
function _setURI(string newuri) internal virtual
```

_Sets a new URI for all token types, by relying on the token type ID
substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

By this mechanism, any occurrence of the &#x60;\{id\}&#x60; substring in either the
URI or any of the amounts in the JSON file at said URI will be replaced by
clients with the token type ID.

For example, the &#x60;https://token-cdn-domain/\{id\}.json&#x60; URI would be
interpreted by clients as
&#x60;https://token-cdn-domain/000000000000000000000000000000000000000000000000000000000004cce0.json&#x60;
for token type ID 0x4cce0.

See {uri}.

Because these URIs cannot be meaningfully represented by the {URI} event,
this function emits no events._

### _mint

```solidity
function _mint(address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Creates &#x60;amount&#x60; tokens of token type &#x60;id&#x60;, and assigns them to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_mint}.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _burn

```solidity
function _burn(address from, uint256 id, uint256 amount) internal virtual
```

_Destroys &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60;

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;from&#x60; must have at least &#x60;amount&#x60; tokens of token type &#x60;id&#x60;._

### _burnBatch

```solidity
function _burnBatch(address from, uint256[] ids, uint256[] amounts) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_burn}.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length._

### _setApprovalForAll

```solidity
function _setApprovalForAll(address owner, address operator, bool approved) internal virtual
```

_Approve &#x60;operator&#x60; to operate on all of &#x60;owner&#x60; tokens

Emits a {ApprovalForAll} event._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning, as well as batched variants.

The same hook is called on both single and batched variants. For single
transfers, the length of the &#x60;id&#x60; and &#x60;amount&#x60; arrays will be 1.

Calling conditions (for each &#x60;id&#x60; and &#x60;amount&#x60; pair):

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens
of token type &#x60;id&#x60; will be  transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;amount&#x60; tokens of token type &#x60;id&#x60; will be minted
for &#x60;to&#x60;.
- when &#x60;to&#x60; is zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens of token type &#x60;id&#x60;
will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.
- &#x60;ids&#x60; and &#x60;amounts&#x60; have the same, non-zero length.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _afterTokenTransfer

```solidity
function _afterTokenTransfer(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_Hook that is called after any token transfer. This includes minting
and burning, as well as batched variants.

The same hook is called on both single and batched variants. For single
transfers, the length of the &#x60;id&#x60; and &#x60;amount&#x60; arrays will be 1.

Calling conditions (for each &#x60;id&#x60; and &#x60;amount&#x60; pair):

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens
of token type &#x60;id&#x60; will be  transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;amount&#x60; tokens of token type &#x60;id&#x60; will be minted
for &#x60;to&#x60;.
- when &#x60;to&#x60; is zero, &#x60;amount&#x60; of &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens of token type &#x60;id&#x60;
will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.
- &#x60;ids&#x60; and &#x60;amounts&#x60; have the same, non-zero length.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _doSafeTransferAcceptanceCheck

```solidity
function _doSafeTransferAcceptanceCheck(address operator, address from, address to, uint256 id, uint256 amount, bytes data) private
```

### _doSafeBatchTransferAcceptanceCheck

```solidity
function _doSafeBatchTransferAcceptanceCheck(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) private
```

### _asSingletonArray

```solidity
function _asSingletonArray(uint256 element) private pure returns (uint256[])
```

## IERC1155

_Required interface of an ERC1155 compliant contract, as defined in the
https://eips.ethereum.org/EIPS/eip-1155[EIP].

_Available since v3.1.__

### TransferSingle

```solidity
event TransferSingle(address operator, address from, address to, uint256 id, uint256 value)
```

_Emitted when &#x60;value&#x60; tokens of token type &#x60;id&#x60; are transferred from &#x60;from&#x60; to &#x60;to&#x60; by &#x60;operator&#x60;._

### TransferBatch

```solidity
event TransferBatch(address operator, address from, address to, uint256[] ids, uint256[] values)
```

_Equivalent to multiple {TransferSingle} events, where &#x60;operator&#x60;, &#x60;from&#x60; and &#x60;to&#x60; are the same for all
transfers._

### ApprovalForAll

```solidity
event ApprovalForAll(address account, address operator, bool approved)
```

_Emitted when &#x60;account&#x60; grants or revokes permission to &#x60;operator&#x60; to transfer their tokens, according to
&#x60;approved&#x60;._

### URI

```solidity
event URI(string value, uint256 id)
```

_Emitted when the URI for token type &#x60;id&#x60; changes to &#x60;value&#x60;, if it is a non-programmatic URI.

If an {URI} event was emitted for &#x60;id&#x60;, the standard
https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[guarantees] that &#x60;value&#x60; will equal the value
returned by {IERC1155MetadataURI-uri}._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) external view returns (uint256)
```

_Returns the amount of tokens of token type &#x60;id&#x60; owned by &#x60;account&#x60;.

Requirements:

- &#x60;account&#x60; cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) external view returns (uint256[])
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {balanceOf}.

Requirements:

- &#x60;accounts&#x60; and &#x60;ids&#x60; must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) external
```

_Grants or revokes permission to &#x60;operator&#x60; to transfer the caller&#x27;s tokens, according to &#x60;approved&#x60;,

Emits an {ApprovalForAll} event.

Requirements:

- &#x60;operator&#x60; cannot be the caller._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) external view returns (bool)
```

_Returns true if &#x60;operator&#x60; is approved to transfer &#x60;&#x60;account&#x60;&#x60;&#x27;s tokens.

See {setApprovalForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) external
```

_Transfers &#x60;amount&#x60; tokens of token type &#x60;id&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.

Emits a {TransferSingle} event.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- If the caller is not &#x60;from&#x60;, it must be have been approved to spend &#x60;&#x60;from&#x60;&#x60;&#x27;s tokens via {setApprovalForAll}.
- &#x60;from&#x60; must have a balance of tokens of type &#x60;id&#x60; of at least &#x60;amount&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) external
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- &#x60;ids&#x60; and &#x60;amounts&#x60; must have the same length.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

## IERC1155Receiver

__Available since v3.1.__

### onERC1155Received

```solidity
function onERC1155Received(address operator, address from, uint256 id, uint256 value, bytes data) external returns (bytes4)
```

_Handles the receipt of a single ERC1155 token type. This function is
called at the end of a &#x60;safeTransferFrom&#x60; after the balance has been updated.

NOTE: To accept the transfer, this must return
&#x60;bytes4(keccak256(&quot;onERC1155Received(address,address,uint256,uint256,bytes)&quot;))&#x60;
(i.e. 0xf23a6e61, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| id | uint256 | The ID of the token being transferred |
| value | uint256 | The amount of tokens being transferred |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | &#x60;bytes4(keccak256(&quot;onERC1155Received(address,address,uint256,uint256,bytes)&quot;))&#x60; if transfer is allowed |

### onERC1155BatchReceived

```solidity
function onERC1155BatchReceived(address operator, address from, uint256[] ids, uint256[] values, bytes data) external returns (bytes4)
```

_Handles the receipt of a multiple ERC1155 token types. This function
is called at the end of a &#x60;safeBatchTransferFrom&#x60; after the balances have
been updated.

NOTE: To accept the transfer(s), this must return
&#x60;bytes4(keccak256(&quot;onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)&quot;))&#x60;
(i.e. 0xbc197c81, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the batch transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| ids | uint256[] | An array containing ids of each token being transferred (order and length must match values array) |
| values | uint256[] | An array containing amounts of each token being transferred (order and length must match ids array) |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | &#x60;bytes4(keccak256(&quot;onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)&quot;))&#x60; if transfer is allowed |

## IERC1155MetadataURI

_Interface of the optional ERC1155MetadataExtension interface, as defined
in the https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[EIP].

_Available since v3.1.__

### uri

```solidity
function uri(uint256 id) external view returns (string)
```

_Returns the URI for token type &#x60;id&#x60;.

If the &#x60;\{id\}&#x60; substring is present in the URI, it must be replaced by
clients with the actual token type ID._

## ERC721

_Implementation of https://eips.ethereum.org/EIPS/eip-721[ERC721] Non-Fungible Token Standard, including
the Metadata extension, but not including the Enumerable extension, which is available separately as
{ERC721Enumerable}._

### _name

```solidity
string _name
```

### _symbol

```solidity
string _symbol
```

### _owners

```solidity
mapping(uint256 &#x3D;&gt; address) _owners
```

### _balances

```solidity
mapping(address &#x3D;&gt; uint256) _balances
```

### _tokenApprovals

```solidity
mapping(uint256 &#x3D;&gt; address) _tokenApprovals
```

### _operatorApprovals

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; bool)) _operatorApprovals
```

### constructor

```solidity
constructor(string name_, string symbol_) public
```

_Initializes the contract by setting a &#x60;name&#x60; and a &#x60;symbol&#x60; to the token collection._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### balanceOf

```solidity
function balanceOf(address owner) public view virtual returns (uint256)
```

_See {IERC721-balanceOf}._

### ownerOf

```solidity
function ownerOf(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721-ownerOf}._

### name

```solidity
function name() public view virtual returns (string)
```

_See {IERC721Metadata-name}._

### symbol

```solidity
function symbol() public view virtual returns (string)
```

_See {IERC721Metadata-symbol}._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

### _baseURI

```solidity
function _baseURI() internal view virtual returns (string)
```

_Base URI for computing {tokenURI}. If set, the resulting URI for each
token will be the concatenation of the &#x60;baseURI&#x60; and the &#x60;tokenId&#x60;. Empty
by default, can be overridden in child contracts._

### approve

```solidity
function approve(address to, uint256 tokenId) public virtual
```

_See {IERC721-approve}._

### getApproved

```solidity
function getApproved(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721-getApproved}._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) public virtual
```

_See {IERC721-setApprovalForAll}._

### isApprovedForAll

```solidity
function isApprovedForAll(address owner, address operator) public view virtual returns (bool)
```

_See {IERC721-isApprovedForAll}._

### transferFrom

```solidity
function transferFrom(address from, address to, uint256 tokenId) public virtual
```

_See {IERC721-transferFrom}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId) public virtual
```

_See {IERC721-safeTransferFrom}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId, bytes _data) public virtual
```

_See {IERC721-safeTransferFrom}._

### _safeTransfer

```solidity
function _safeTransfer(address from, address to, uint256 tokenId, bytes _data) internal virtual
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;, checking first that contract recipients
are aware of the ERC721 protocol to prevent tokens from being forever locked.

&#x60;_data&#x60; is additional data, it has no specified format and it is sent in call to &#x60;to&#x60;.

This internal function is equivalent to {safeTransferFrom}, and can be used to e.g.
implement alternative mechanisms to perform token transfer, such as signature-based.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### _exists

```solidity
function _exists(uint256 tokenId) internal view virtual returns (bool)
```

_Returns whether &#x60;tokenId&#x60; exists.

Tokens can be managed by their owner or approved accounts via {approve} or {setApprovalForAll}.

Tokens start existing when they are minted (&#x60;_mint&#x60;),
and stop existing when they are burned (&#x60;_burn&#x60;)._

### _isApprovedOrOwner

```solidity
function _isApprovedOrOwner(address spender, uint256 tokenId) internal view virtual returns (bool)
```

_Returns whether &#x60;spender&#x60; is allowed to manage &#x60;tokenId&#x60;.

Requirements:

- &#x60;tokenId&#x60; must exist._

### _safeMint

```solidity
function _safeMint(address to, uint256 tokenId) internal virtual
```

_Safely mints &#x60;tokenId&#x60; and transfers it to &#x60;to&#x60;.

Requirements:

- &#x60;tokenId&#x60; must not exist.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### _safeMint

```solidity
function _safeMint(address to, uint256 tokenId, bytes _data) internal virtual
```

_Same as {xref-ERC721-_safeMint-address-uint256-}[&#x60;_safeMint&#x60;], with an additional &#x60;data&#x60; parameter which is
forwarded in {IERC721Receiver-onERC721Received} to contract recipients._

### _mint

```solidity
function _mint(address to, uint256 tokenId) internal virtual
```

_Mints &#x60;tokenId&#x60; and transfers it to &#x60;to&#x60;.

WARNING: Usage of this method is discouraged, use {_safeMint} whenever possible

Requirements:

- &#x60;tokenId&#x60; must not exist.
- &#x60;to&#x60; cannot be the zero address.

Emits a {Transfer} event._

### _burn

```solidity
function _burn(uint256 tokenId) internal virtual
```

_Destroys &#x60;tokenId&#x60;.
The approval is cleared when the token is burned.

Requirements:

- &#x60;tokenId&#x60; must exist.

Emits a {Transfer} event._

### _transfer

```solidity
function _transfer(address from, address to, uint256 tokenId) internal virtual
```

_Transfers &#x60;tokenId&#x60; from &#x60;from&#x60; to &#x60;to&#x60;.
 As opposed to {transferFrom}, this imposes no restrictions on msg.sender.

Requirements:

- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must be owned by &#x60;from&#x60;.

Emits a {Transfer} event._

### _approve

```solidity
function _approve(address to, uint256 tokenId) internal virtual
```

_Approve &#x60;to&#x60; to operate on &#x60;tokenId&#x60;

Emits a {Approval} event._

### _setApprovalForAll

```solidity
function _setApprovalForAll(address owner, address operator, bool approved) internal virtual
```

_Approve &#x60;operator&#x60; to operate on all of &#x60;owner&#x60; tokens

Emits a {ApprovalForAll} event._

### _checkOnERC721Received

```solidity
function _checkOnERC721Received(address from, address to, uint256 tokenId, bytes _data) private returns (bool)
```

_Internal function to invoke {IERC721Receiver-onERC721Received} on a target address.
The call is not executed if the target address is not a contract._

| Name | Type | Description |
| ---- | ---- | ----------- |
| from | address | address representing the previous owner of the given token ID |
| to | address | target address that will receive the tokens |
| tokenId | uint256 | uint256 ID of the token to be transferred |
| _data | bytes | bytes optional data to send along with the call |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bool | bool whether the call correctly returned the expected magic value |

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _afterTokenTransfer

```solidity
function _afterTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called after any transfer of tokens. This includes
minting and burning.

Calling conditions:

- when &#x60;from&#x60; and &#x60;to&#x60; are both non-zero.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

## IERC721

_Required interface of an ERC721 compliant contract._

### Transfer

```solidity
event Transfer(address from, address to, uint256 tokenId)
```

_Emitted when &#x60;tokenId&#x60; token is transferred from &#x60;from&#x60; to &#x60;to&#x60;._

### Approval

```solidity
event Approval(address owner, address approved, uint256 tokenId)
```

_Emitted when &#x60;owner&#x60; enables &#x60;approved&#x60; to manage the &#x60;tokenId&#x60; token._

### ApprovalForAll

```solidity
event ApprovalForAll(address owner, address operator, bool approved)
```

_Emitted when &#x60;owner&#x60; enables or disables (&#x60;approved&#x60;) &#x60;operator&#x60; to manage all of its assets._

### balanceOf

```solidity
function balanceOf(address owner) external view returns (uint256 balance)
```

_Returns the number of tokens in &#x60;&#x60;owner&#x60;&#x60;&#x27;s account._

### ownerOf

```solidity
function ownerOf(uint256 tokenId) external view returns (address owner)
```

_Returns the owner of the &#x60;tokenId&#x60; token.

Requirements:

- &#x60;tokenId&#x60; must exist._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId, bytes data) external
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be approved to move this token by either {approve} or {setApprovalForAll}.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 tokenId) external
```

_Safely transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;, checking first that contract recipients
are aware of the ERC721 protocol to prevent tokens from being forever locked.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must exist and be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be have been allowed to move this token by either {approve} or {setApprovalForAll}.
- If &#x60;to&#x60; refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.

Emits a {Transfer} event._

### transferFrom

```solidity
function transferFrom(address from, address to, uint256 tokenId) external
```

_Transfers &#x60;tokenId&#x60; token from &#x60;from&#x60; to &#x60;to&#x60;.

WARNING: Usage of this method is discouraged, use {safeTransferFrom} whenever possible.

Requirements:

- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.
- &#x60;tokenId&#x60; token must be owned by &#x60;from&#x60;.
- If the caller is not &#x60;from&#x60;, it must be approved to move this token by either {approve} or {setApprovalForAll}.

Emits a {Transfer} event._

### approve

```solidity
function approve(address to, uint256 tokenId) external
```

_Gives permission to &#x60;to&#x60; to transfer &#x60;tokenId&#x60; token to another account.
The approval is cleared when the token is transferred.

Only a single account can be approved at a time, so approving the zero address clears previous approvals.

Requirements:

- The caller must own the token or be an approved operator.
- &#x60;tokenId&#x60; must exist.

Emits an {Approval} event._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool _approved) external
```

_Approve or remove &#x60;operator&#x60; as an operator for the caller.
Operators can call {transferFrom} or {safeTransferFrom} for any token owned by the caller.

Requirements:

- The &#x60;operator&#x60; cannot be the caller.

Emits an {ApprovalForAll} event._

### getApproved

```solidity
function getApproved(uint256 tokenId) external view returns (address operator)
```

_Returns the account approved for &#x60;tokenId&#x60; token.

Requirements:

- &#x60;tokenId&#x60; must exist._

### isApprovedForAll

```solidity
function isApprovedForAll(address owner, address operator) external view returns (bool)
```

_Returns if the &#x60;operator&#x60; is allowed to manage all of the assets of &#x60;owner&#x60;.

See {setApprovalForAll}_

## IERC721Receiver

_Interface for any contract that wants to support safeTransfers
from ERC721 asset contracts._

### onERC721Received

```solidity
function onERC721Received(address operator, address from, uint256 tokenId, bytes data) external returns (bytes4)
```

_Whenever an {IERC721} &#x60;tokenId&#x60; token is transferred to this contract via {IERC721-safeTransferFrom}
by &#x60;operator&#x60; from &#x60;from&#x60;, this function is called.

It must return its Solidity selector to confirm the token transfer.
If any other value is returned or the interface is not implemented by the recipient, the transfer will be reverted.

The selector can be obtained in Solidity with &#x60;IERC721Receiver.onERC721Received.selector&#x60;._

## ERC721Enumerable

_This implements an optional extension of {ERC721} defined in the EIP that adds
enumerability of all the token ids in the contract as well as all token ids owned by each
account._

### _ownedTokens

```solidity
mapping(address &#x3D;&gt; mapping(uint256 &#x3D;&gt; uint256)) _ownedTokens
```

### _ownedTokensIndex

```solidity
mapping(uint256 &#x3D;&gt; uint256) _ownedTokensIndex
```

### _allTokens

```solidity
uint256[] _allTokens
```

### _allTokensIndex

```solidity
mapping(uint256 &#x3D;&gt; uint256) _allTokensIndex
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### tokenOfOwnerByIndex

```solidity
function tokenOfOwnerByIndex(address owner, uint256 index) public view virtual returns (uint256)
```

_See {IERC721Enumerable-tokenOfOwnerByIndex}._

### totalSupply

```solidity
function totalSupply() public view virtual returns (uint256)
```

_See {IERC721Enumerable-totalSupply}._

### tokenByIndex

```solidity
function tokenByIndex(uint256 index) public view virtual returns (uint256)
```

_See {IERC721Enumerable-tokenByIndex}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; cannot be the zero address.
- &#x60;to&#x60; cannot be the zero address.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _addTokenToOwnerEnumeration

```solidity
function _addTokenToOwnerEnumeration(address to, uint256 tokenId) private
```

_Private function to add a token to this extension&#x27;s ownership-tracking data structures._

| Name | Type | Description |
| ---- | ---- | ----------- |
| to | address | address representing the new owner of the given token ID |
| tokenId | uint256 | uint256 ID of the token to be added to the tokens list of the given address |

### _addTokenToAllTokensEnumeration

```solidity
function _addTokenToAllTokensEnumeration(uint256 tokenId) private
```

_Private function to add a token to this extension&#x27;s token tracking data structures._

| Name | Type | Description |
| ---- | ---- | ----------- |
| tokenId | uint256 | uint256 ID of the token to be added to the tokens list |

### _removeTokenFromOwnerEnumeration

```solidity
function _removeTokenFromOwnerEnumeration(address from, uint256 tokenId) private
```

_Private function to remove a token from this extension&#x27;s ownership-tracking data structures. Note that
while the token is not assigned a new owner, the &#x60;_ownedTokensIndex&#x60; mapping is _not_ updated: this allows for
gas optimizations e.g. when performing a transfer operation (avoiding double writes).
This has O(1) time complexity, but alters the order of the _ownedTokens array._

| Name | Type | Description |
| ---- | ---- | ----------- |
| from | address | address representing the previous owner of the given token ID |
| tokenId | uint256 | uint256 ID of the token to be removed from the tokens list of the given address |

### _removeTokenFromAllTokensEnumeration

```solidity
function _removeTokenFromAllTokensEnumeration(uint256 tokenId) private
```

_Private function to remove a token from this extension&#x27;s token tracking data structures.
This has O(1) time complexity, but alters the order of the _allTokens array._

| Name | Type | Description |
| ---- | ---- | ----------- |
| tokenId | uint256 | uint256 ID of the token to be removed from the tokens list |

## IERC721Enumerable

_See https://eips.ethereum.org/EIPS/eip-721_

### totalSupply

```solidity
function totalSupply() external view returns (uint256)
```

_Returns the total amount of tokens stored by the contract._

### tokenOfOwnerByIndex

```solidity
function tokenOfOwnerByIndex(address owner, uint256 index) external view returns (uint256)
```

_Returns a token ID owned by &#x60;owner&#x60; at a given &#x60;index&#x60; of its token list.
Use along with {balanceOf} to enumerate all of &#x60;&#x60;owner&#x60;&#x60;&#x27;s tokens._

### tokenByIndex

```solidity
function tokenByIndex(uint256 index) external view returns (uint256)
```

_Returns a token ID at a given &#x60;index&#x60; of all the tokens stored by the contract.
Use along with {totalSupply} to enumerate all tokens._

## IERC721Metadata

_See https://eips.ethereum.org/EIPS/eip-721_

### name

```solidity
function name() external view returns (string)
```

_Returns the token collection name._

### symbol

```solidity
function symbol() external view returns (string)
```

_Returns the token collection symbol._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) external view returns (string)
```

_Returns the Uniform Resource Identifier (URI) for &#x60;tokenId&#x60; token._

## Address

_Collection of functions related to the address type_

### isContract

```solidity
function isContract(address account) internal view returns (bool)
```

_Returns true if &#x60;account&#x60; is a contract.

[IMPORTANT]
&#x3D;&#x3D;&#x3D;&#x3D;
It is unsafe to assume that an address for which this function returns
false is an externally-owned account (EOA) and not a contract.

Among others, &#x60;isContract&#x60; will return false for the following
types of addresses:

 - an externally-owned account
 - a contract in construction
 - an address where a contract will be created
 - an address where a contract lived, but was destroyed
&#x3D;&#x3D;&#x3D;&#x3D;

[IMPORTANT]
&#x3D;&#x3D;&#x3D;&#x3D;
You shouldn&#x27;t rely on &#x60;isContract&#x60; to protect against flash loan attacks!

Preventing calls from contracts is highly discouraged. It breaks composability, breaks support for smart wallets
like Gnosis Safe, and does not provide security since it can be circumvented by calling from a contract
constructor.
&#x3D;&#x3D;&#x3D;&#x3D;_

### sendValue

```solidity
function sendValue(address payable recipient, uint256 amount) internal
```

_Replacement for Solidity&#x27;s &#x60;transfer&#x60;: sends &#x60;amount&#x60; wei to
&#x60;recipient&#x60;, forwarding all available gas and reverting on errors.

https://eips.ethereum.org/EIPS/eip-1884[EIP1884] increases the gas cost
of certain opcodes, possibly making contracts go over the 2300 gas limit
imposed by &#x60;transfer&#x60;, making them unable to receive funds via
&#x60;transfer&#x60;. {sendValue} removes this limitation.

https://diligence.consensys.net/posts/2019/09/stop-using-soliditys-transfer-now/[Learn more].

IMPORTANT: because control is transferred to &#x60;recipient&#x60;, care must be
taken to not create reentrancy vulnerabilities. Consider using
{ReentrancyGuard} or the
https://solidity.readthedocs.io/en/v0.5.11/security-considerations.html#use-the-checks-effects-interactions-pattern[checks-effects-interactions pattern]._

### functionCall

```solidity
function functionCall(address target, bytes data) internal returns (bytes)
```

_Performs a Solidity function call using a low level &#x60;call&#x60;. A
plain &#x60;call&#x60; is an unsafe replacement for a function call: use this
function instead.

If &#x60;target&#x60; reverts with a revert reason, it is bubbled up by this
function (like regular Solidity function calls).

Returns the raw returned data. To convert to the expected return value,
use https://solidity.readthedocs.io/en/latest/units-and-global-variables.html?highlight&#x3D;abi.decode#abi-encoding-and-decoding-functions[&#x60;abi.decode&#x60;].

Requirements:

- &#x60;target&#x60; must be a contract.
- calling &#x60;target&#x60; with &#x60;data&#x60; must not revert.

_Available since v3.1.__

### functionCall

```solidity
function functionCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;], but with
&#x60;errorMessage&#x60; as a fallback revert reason when &#x60;target&#x60; reverts.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;],
but also transferring &#x60;value&#x60; wei to &#x60;target&#x60;.

Requirements:

- the calling contract must have an ETH balance of at least &#x60;value&#x60;.
- the called Solidity function must be &#x60;payable&#x60;.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCallWithValue-address-bytes-uint256-}[&#x60;functionCallWithValue&#x60;], but
with &#x60;errorMessage&#x60; as a fallback revert reason when &#x60;target&#x60; reverts.

_Available since v3.1.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;],
but performing a static call.

_Available since v3.3.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data, string errorMessage) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-string-}[&#x60;functionCall&#x60;],
but performing a static call.

_Available since v3.3.__

### functionDelegateCall

```solidity
function functionDelegateCall(address target, bytes data) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[&#x60;functionCall&#x60;],
but performing a delegate call.

_Available since v3.4.__

### functionDelegateCall

```solidity
function functionDelegateCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-string-}[&#x60;functionCall&#x60;],
but performing a delegate call.

_Available since v3.4.__

### verifyCallResult

```solidity
function verifyCallResult(bool success, bytes returndata, string errorMessage) internal pure returns (bytes)
```

_Tool to verifies that a low level call was successful, and revert if it wasn&#x27;t, either by bubbling the
revert reason using the provided one.

_Available since v4.3.__

## Context

_Provides information about the current execution context, including the
sender of the transaction and its data. While these are generally available
via msg.sender and msg.data, they should not be accessed in such a direct
manner, since when dealing with meta-transactions the account sending and
paying for execution may not be the actual sender (as far as an application
is concerned).

This contract is only required for intermediate, library-like contracts._

### _msgSender

```solidity
function _msgSender() internal view virtual returns (address)
```

### _msgData

```solidity
function _msgData() internal view virtual returns (bytes)
```

## Strings

_String operations._

### _HEX_SYMBOLS

```solidity
bytes16 _HEX_SYMBOLS
```

### toString

```solidity
function toString(uint256 value) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; decimal representation._

### toHexString

```solidity
function toHexString(uint256 value) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; hexadecimal representation._

### toHexString

```solidity
function toHexString(uint256 value, uint256 length) internal pure returns (string)
```

_Converts a &#x60;uint256&#x60; to its ASCII &#x60;string&#x60; hexadecimal representation with fixed length._

## ERC165

_Implementation of the {IERC165} interface.

Contracts that want to implement ERC165 should inherit from this contract and override {supportsInterface} to check
for the additional interface id that will be supported. For example:

&#x60;&#x60;&#x60;solidity
function supportsInterface(bytes4 interfaceId) public view virtual override returns (bool) {
    return interfaceId &#x3D;&#x3D; type(MyInterface).interfaceId || super.supportsInterface(interfaceId);
}
&#x60;&#x60;&#x60;

Alternatively, {ERC165Storage} provides an easier to use but more expensive implementation._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

## ERC165Checker

_Library used to query support of an interface declared via {IERC165}.

Note that these functions return the actual result of the query: they do not
&#x60;revert&#x60; if an interface is not supported. It is up to the caller to decide
what to do in these cases._

### _INTERFACE_ID_INVALID

```solidity
bytes4 _INTERFACE_ID_INVALID
```

### supportsERC165

```solidity
function supportsERC165(address account) internal view returns (bool)
```

_Returns true if &#x60;account&#x60; supports the {IERC165} interface,_

### supportsInterface

```solidity
function supportsInterface(address account, bytes4 interfaceId) internal view returns (bool)
```

_Returns true if &#x60;account&#x60; supports the interface defined by
&#x60;interfaceId&#x60;. Support for {IERC165} itself is queried automatically.

See {IERC165-supportsInterface}._

### getSupportedInterfaces

```solidity
function getSupportedInterfaces(address account, bytes4[] interfaceIds) internal view returns (bool[])
```

_Returns a boolean array where each value corresponds to the
interfaces passed in and whether they&#x27;re supported or not. This allows
you to batch check interfaces for a contract where your expectation
is that some interfaces may not be supported.

See {IERC165-supportsInterface}.

_Available since v3.4.__

### supportsAllInterfaces

```solidity
function supportsAllInterfaces(address account, bytes4[] interfaceIds) internal view returns (bool)
```

_Returns true if &#x60;account&#x60; supports all the interfaces defined in
&#x60;interfaceIds&#x60;. Support for {IERC165} itself is queried automatically.

Batch-querying can lead to gas savings by skipping repeated checks for
{IERC165} support.

See {IERC165-supportsInterface}._

### _supportsERC165Interface

```solidity
function _supportsERC165Interface(address account, bytes4 interfaceId) private view returns (bool)
```

Query if a contract implements an interface, does not check ERC165 support

_Assumes that account contains a contract that supports ERC165, otherwise
the behavior of this method is undefined. This precondition can be checked
with {supportsERC165}.
Interface identification is specified in ERC-165._

| Name | Type | Description |
| ---- | ---- | ----------- |
| account | address | The address of the contract to query for support of an interface |
| interfaceId | bytes4 | The interface identifier, as specified in ERC-165 |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bool | true if the contract at account indicates support of the interface with identifier interfaceId, false otherwise |

## IERC165

_Interface of the ERC165 standard, as defined in the
https://eips.ethereum.org/EIPS/eip-165[EIP].

Implementers can declare support of contract interfaces, which can then be
queried by others ({ERC165Checker}).

For an implementation, see {ERC165}._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) external view returns (bool)
```

_Returns true if this contract implements the interface defined by
&#x60;interfaceId&#x60;. See the corresponding
https://eips.ethereum.org/EIPS/eip-165#how-interfaces-are-identified[EIP section]
to learn more about how these ids are created.

This function call must use less than 30 000 gas._

## EnumerableSet

_Library for managing
https://en.wikipedia.org/wiki/Set_(abstract_data_type)[sets] of primitive
types.

Sets have the following properties:

- Elements are added, removed, and checked for existence in constant time
(O(1)).
- Elements are enumerated in O(n). No guarantees are made on the ordering.

&#x60;&#x60;&#x60;
contract Example {
    // Add the library methods
    using EnumerableSet for EnumerableSet.AddressSet;

    // Declare a set state variable
    EnumerableSet.AddressSet private mySet;
}
&#x60;&#x60;&#x60;

As of v3.3.0, sets of type &#x60;bytes32&#x60; (&#x60;Bytes32Set&#x60;), &#x60;address&#x60; (&#x60;AddressSet&#x60;)
and &#x60;uint256&#x60; (&#x60;UintSet&#x60;) are supported._

### Set

```solidity
struct Set {
  bytes32[] _values;
  mapping(bytes32 &#x3D;&gt; uint256) _indexes;
}
```

### _add

```solidity
function _add(struct EnumerableSet.Set set, bytes32 value) private returns (bool)
```

_Add a value to a set. O(1).

Returns true if the value was added to the set, that is if it was not
already present._

### _remove

```solidity
function _remove(struct EnumerableSet.Set set, bytes32 value) private returns (bool)
```

_Removes a value from a set. O(1).

Returns true if the value was removed from the set, that is if it was
present._

### _contains

```solidity
function _contains(struct EnumerableSet.Set set, bytes32 value) private view returns (bool)
```

_Returns true if the value is in the set. O(1)._

### _length

```solidity
function _length(struct EnumerableSet.Set set) private view returns (uint256)
```

_Returns the number of values on the set. O(1)._

### _at

```solidity
function _at(struct EnumerableSet.Set set, uint256 index) private view returns (bytes32)
```

_Returns the value stored at position &#x60;index&#x60; in the set. O(1).

Note that there are no guarantees on the ordering of values inside the
array, and it may change when more values are added or removed.

Requirements:

- &#x60;index&#x60; must be strictly less than {length}._

### _values

```solidity
function _values(struct EnumerableSet.Set set) private view returns (bytes32[])
```

_Return the entire set in an array

WARNING: This operation will copy the entire storage to memory, which can be quite expensive. This is designed
to mostly be used by view accessors that are queried without any gas fees. Developers should keep in mind that
this function has an unbounded cost, and using it as part of a state-changing function may render the function
uncallable if the set grows to a point where copying to memory consumes too much gas to fit in a block._

### Bytes32Set

```solidity
struct Bytes32Set {
  struct EnumerableSet.Set _inner;
}
```

### add

```solidity
function add(struct EnumerableSet.Bytes32Set set, bytes32 value) internal returns (bool)
```

_Add a value to a set. O(1).

Returns true if the value was added to the set, that is if it was not
already present._

### remove

```solidity
function remove(struct EnumerableSet.Bytes32Set set, bytes32 value) internal returns (bool)
```

_Removes a value from a set. O(1).

Returns true if the value was removed from the set, that is if it was
present._

### contains

```solidity
function contains(struct EnumerableSet.Bytes32Set set, bytes32 value) internal view returns (bool)
```

_Returns true if the value is in the set. O(1)._

### length

```solidity
function length(struct EnumerableSet.Bytes32Set set) internal view returns (uint256)
```

_Returns the number of values in the set. O(1)._

### at

```solidity
function at(struct EnumerableSet.Bytes32Set set, uint256 index) internal view returns (bytes32)
```

_Returns the value stored at position &#x60;index&#x60; in the set. O(1).

Note that there are no guarantees on the ordering of values inside the
array, and it may change when more values are added or removed.

Requirements:

- &#x60;index&#x60; must be strictly less than {length}._

### values

```solidity
function values(struct EnumerableSet.Bytes32Set set) internal view returns (bytes32[])
```

_Return the entire set in an array

WARNING: This operation will copy the entire storage to memory, which can be quite expensive. This is designed
to mostly be used by view accessors that are queried without any gas fees. Developers should keep in mind that
this function has an unbounded cost, and using it as part of a state-changing function may render the function
uncallable if the set grows to a point where copying to memory consumes too much gas to fit in a block._

### AddressSet

```solidity
struct AddressSet {
  struct EnumerableSet.Set _inner;
}
```

### add

```solidity
function add(struct EnumerableSet.AddressSet set, address value) internal returns (bool)
```

_Add a value to a set. O(1).

Returns true if the value was added to the set, that is if it was not
already present._

### remove

```solidity
function remove(struct EnumerableSet.AddressSet set, address value) internal returns (bool)
```

_Removes a value from a set. O(1).

Returns true if the value was removed from the set, that is if it was
present._

### contains

```solidity
function contains(struct EnumerableSet.AddressSet set, address value) internal view returns (bool)
```

_Returns true if the value is in the set. O(1)._

### length

```solidity
function length(struct EnumerableSet.AddressSet set) internal view returns (uint256)
```

_Returns the number of values in the set. O(1)._

### at

```solidity
function at(struct EnumerableSet.AddressSet set, uint256 index) internal view returns (address)
```

_Returns the value stored at position &#x60;index&#x60; in the set. O(1).

Note that there are no guarantees on the ordering of values inside the
array, and it may change when more values are added or removed.

Requirements:

- &#x60;index&#x60; must be strictly less than {length}._

### values

```solidity
function values(struct EnumerableSet.AddressSet set) internal view returns (address[])
```

_Return the entire set in an array

WARNING: This operation will copy the entire storage to memory, which can be quite expensive. This is designed
to mostly be used by view accessors that are queried without any gas fees. Developers should keep in mind that
this function has an unbounded cost, and using it as part of a state-changing function may render the function
uncallable if the set grows to a point where copying to memory consumes too much gas to fit in a block._

### UintSet

```solidity
struct UintSet {
  struct EnumerableSet.Set _inner;
}
```

### add

```solidity
function add(struct EnumerableSet.UintSet set, uint256 value) internal returns (bool)
```

_Add a value to a set. O(1).

Returns true if the value was added to the set, that is if it was not
already present._

### remove

```solidity
function remove(struct EnumerableSet.UintSet set, uint256 value) internal returns (bool)
```

_Removes a value from a set. O(1).

Returns true if the value was removed from the set, that is if it was
present._

### contains

```solidity
function contains(struct EnumerableSet.UintSet set, uint256 value) internal view returns (bool)
```

_Returns true if the value is in the set. O(1)._

### length

```solidity
function length(struct EnumerableSet.UintSet set) internal view returns (uint256)
```

_Returns the number of values on the set. O(1)._

### at

```solidity
function at(struct EnumerableSet.UintSet set, uint256 index) internal view returns (uint256)
```

_Returns the value stored at position &#x60;index&#x60; in the set. O(1).

Note that there are no guarantees on the ordering of values inside the
array, and it may change when more values are added or removed.

Requirements:

- &#x60;index&#x60; must be strictly less than {length}._

### values

```solidity
function values(struct EnumerableSet.UintSet set) internal view returns (uint256[])
```

_Return the entire set in an array

WARNING: This operation will copy the entire storage to memory, which can be quite expensive. This is designed
to mostly be used by view accessors that are queried without any gas fees. Developers should keep in mind that
this function has an unbounded cost, and using it as part of a state-changing function may render the function
uncallable if the set grows to a point where copying to memory consumes too much gas to fit in a block._

## ERC1155Creator

_ERC1155Creator implementation_

### _totalSupply

```solidity
mapping(uint256 &#x3D;&gt; uint256) _totalSupply
```

### constructor

```solidity
constructor() public
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address, address from, address to, uint256[] ids, uint256[] amounts, bytes) internal virtual
```

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri_) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBaseNew

```solidity
function mintBaseNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[])
```

_See {IERC1155CreatorCore-mintBaseNew}._

### mintBaseExisting

```solidity
function mintBaseExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintBaseExisting}._

### mintExtensionNew

```solidity
function mintExtensionNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC1155CreatorCore-mintExtensionNew}._

### mintExtensionExisting

```solidity
function mintExtensionExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintExtensionExisting}._

### _mintNew

```solidity
function _mintNew(address extension, address[] to, uint256[] amounts, string[] uris) internal returns (uint256[] tokenIds)
```

_Mint new tokens_

### _mintExisting

```solidity
function _mintExisting(address extension, address[] to, uint256[] tokenIds, uint256[] amounts) internal
```

_Mint existing tokens_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC1155CreatorCore-tokenExtension}._

### burn

```solidity
function burn(address account, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### uri

```solidity
function uri(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

### totalSupply

```solidity
function totalSupply(uint256 tokenId) external view virtual returns (uint256)
```

_Total amount of tokens in with a given id._

### _mint

```solidity
function _mint(address account, uint256 id, uint256 amount, bytes data) internal virtual
```

_See {ERC1155-_mint}._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_See {ERC1155-_mintBatch}._

### _burn

```solidity
function _burn(address account, uint256 id, uint256 amount) internal virtual
```

_See {ERC1155-_burn}._

### _burnBatch

```solidity
function _burnBatch(address account, uint256[] ids, uint256[] amounts) internal virtual
```

_See {ERC1155-_burnBatch}._

## ERC1155CreatorImplementation

_ERC1155Creator implementation_

### _totalSupply

```solidity
mapping(uint256 &#x3D;&gt; uint256) _totalSupply
```

### initialize

```solidity
function initialize() public
```

Initializer

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address, address from, address to, uint256[] ids, uint256[] amounts, bytes) internal virtual
```

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri_) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBaseNew

```solidity
function mintBaseNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[])
```

_See {IERC1155CreatorCore-mintBaseNew}._

### mintBaseExisting

```solidity
function mintBaseExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintBaseExisting}._

### mintExtensionNew

```solidity
function mintExtensionNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC1155CreatorCore-mintExtensionNew}._

### mintExtensionExisting

```solidity
function mintExtensionExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintExtensionExisting}._

### _mintNew

```solidity
function _mintNew(address extension, address[] to, uint256[] amounts, string[] uris) internal returns (uint256[] tokenIds)
```

_Mint new tokens_

### _mintExisting

```solidity
function _mintExisting(address extension, address[] to, uint256[] tokenIds, uint256[] amounts) internal
```

_Mint existing tokens_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC1155CreatorCore-tokenExtension}._

### burn

```solidity
function burn(address account, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### uri

```solidity
function uri(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

### totalSupply

```solidity
function totalSupply(uint256 tokenId) external view virtual returns (uint256)
```

_Total amount of tokens in with a given id._

### _mint

```solidity
function _mint(address account, uint256 id, uint256 amount, bytes data) internal virtual
```

_See {ERC1155-_mint}._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_See {ERC1155-_mintBatch}._

### _burn

```solidity
function _burn(address account, uint256 id, uint256 amount) internal virtual
```

_See {ERC1155-_burn}._

### _burnBatch

```solidity
function _burnBatch(address account, uint256[] ids, uint256[] amounts) internal virtual
```

_See {ERC1155-_burnBatch}._

## ERC1155CreatorUpgradeable

_ERC1155Creator implementation (using transparent upgradeable proxy)_

### _totalSupply

```solidity
mapping(uint256 &#x3D;&gt; uint256) _totalSupply
```

### initialize

```solidity
function initialize() public
```

Initializer

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address, address from, address to, uint256[] ids, uint256[] amounts, bytes) internal virtual
```

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri_, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri_) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri_) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBaseNew

```solidity
function mintBaseNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[])
```

_See {IERC1155CreatorCore-mintBaseNew}._

### mintBaseExisting

```solidity
function mintBaseExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintBaseExisting}._

### mintExtensionNew

```solidity
function mintExtensionNew(address[] to, uint256[] amounts, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC1155CreatorCore-mintExtensionNew}._

### mintExtensionExisting

```solidity
function mintExtensionExisting(address[] to, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-mintExtensionExisting}._

### _mintNew

```solidity
function _mintNew(address extension, address[] to, uint256[] amounts, string[] uris) internal returns (uint256[] tokenIds)
```

_Mint new tokens_

### _mintExisting

```solidity
function _mintExisting(address extension, address[] to, uint256[] tokenIds, uint256[] amounts) internal
```

_Mint existing tokens_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC1155CreatorCore-tokenExtension}._

### burn

```solidity
function burn(address account, uint256[] tokenIds, uint256[] amounts) public virtual
```

_See {IERC1155CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### uri

```solidity
function uri(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

### totalSupply

```solidity
function totalSupply(uint256 tokenId) external view virtual returns (uint256)
```

_Total amount of tokens in with a given id._

### _mint

```solidity
function _mint(address account, uint256 id, uint256 amount, bytes data) internal virtual
```

_See {ERC1155-_mint}._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_See {ERC1155-_mintBatch}._

### _burn

```solidity
function _burn(address account, uint256 id, uint256 amount) internal virtual
```

_See {ERC1155-_burn}._

### _burnBatch

```solidity
function _burnBatch(address account, uint256[] ids, uint256[] amounts) internal virtual
```

_See {ERC1155-_burnBatch}._

## ERC721Creator

_ERC721Creator implementation_

### constructor

```solidity
constructor(string _name, string _symbol) public
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBase

```solidity
function mintBase(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBase

```solidity
function mintBase(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### _mintBase

```solidity
function _mintBase(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token with no extension_

### mintExtension

```solidity
function mintExtension(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtension

```solidity
function mintExtension(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### _mintExtension

```solidity
function _mintExtension(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token via extension_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721CreatorCore-tokenExtension}._

### burn

```solidity
function burn(uint256 tokenId) public virtual
```

_See {IERC721CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

## ERC721CreatorEnumerable

_ERC721Creator implementation (with enumerable api&#x27;s)_

### constructor

```solidity
constructor(string _name, string _symbol) public
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

### _postMintBase

```solidity
function _postMintBase(address to, uint256 tokenId) internal virtual
```

### _postMintExtension

```solidity
function _postMintExtension(address to, uint256 tokenId) internal virtual
```

### _postBurn

```solidity
function _postBurn(address owner, uint256 tokenId) internal virtual
```

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

## ERC721CreatorImplementation

_ERC721Creator implementation_

### initialize

```solidity
function initialize(string _name, string _symbol) public
```

Initializer

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBase

```solidity
function mintBase(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBase

```solidity
function mintBase(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### _mintBase

```solidity
function _mintBase(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token with no extension_

### mintExtension

```solidity
function mintExtension(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtension

```solidity
function mintExtension(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### _mintExtension

```solidity
function _mintExtension(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token via extension_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721CreatorCore-tokenExtension}._

### burn

```solidity
function burn(uint256 tokenId) public virtual
```

_See {IERC721CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

## ERC721CreatorUpgradeable

_ERC721Creator implementation (using transparent upgradeable proxy)_

### initialize

```solidity
function initialize(string _name, string _symbol) public
```

Initializer

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning.

Calling conditions:

- When &#x60;from&#x60; and &#x60;to&#x60; are both non-zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be
transferred to &#x60;to&#x60;.
- When &#x60;from&#x60; is zero, &#x60;tokenId&#x60; will be minted for &#x60;to&#x60;.
- When &#x60;to&#x60; is zero, &#x60;&#x60;from&#x60;&#x60;&#x27;s &#x60;tokenId&#x60; will be burned.
- &#x60;from&#x60; and &#x60;to&#x60; are never both zero.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_See {ICreatorCore-registerExtension}._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_See {ICreatorCore-registerExtension}._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_See {ICreatorCore-unregisterExtension}._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_See {ICreatorCore-blacklistExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri, bool identical) external
```

_See {ICreatorCore-setBaseTokenURIExtension}._

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefixExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURIExtension}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri) external
```

_See {ICreatorCore-setBaseTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_See {ICreatorCore-setTokenURIPrefix}._

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri) external
```

_See {ICreatorCore-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_See {ICreatorCore-setTokenURI}._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_See {ICreatorCore-setMintPermissions}._

### mintBase

```solidity
function mintBase(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBase

```solidity
function mintBase(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintBase}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### mintBaseBatch

```solidity
function mintBaseBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintBaseBatch}._

### _mintBase

```solidity
function _mintBase(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token with no extension_

### mintExtension

```solidity
function mintExtension(address to) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtension

```solidity
function mintExtension(address to, string uri) public virtual returns (uint256)
```

_See {IERC721CreatorCore-mintExtension}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, uint16 count) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, string[] uris) public virtual returns (uint256[] tokenIds)
```

_See {IERC721CreatorCore-mintExtensionBatch}._

### _mintExtension

```solidity
function _mintExtension(address to, string uri) internal virtual returns (uint256 tokenId)
```

_Mint token via extension_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) public view virtual returns (address)
```

_See {IERC721CreatorCore-tokenExtension}._

### burn

```solidity
function burn(uint256 tokenId) public virtual
```

_See {IERC721CreatorCore-burn}._

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyalties}._

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_See {ICreatorCore-setRoyaltiesExtension}._

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getRoyalties}._

### getFees

```solidity
function getFees(uint256 tokenId) external view virtual returns (address payable[], uint256[])
```

_{See ICreatorCore-getFees}._

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view virtual returns (address payable[])
```

_{See ICreatorCore-getFeeRecipients}._

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view virtual returns (uint256[])
```

_{See ICreatorCore-getFeeBps}._

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view virtual returns (address, uint256)
```

_{See ICreatorCore-royaltyInfo}._

### tokenURI

```solidity
function tokenURI(uint256 tokenId) public view virtual returns (string)
```

_See {IERC721Metadata-tokenURI}._

## Migrations

### owner

```solidity
address owner
```

### last_completed_migration

```solidity
uint256 last_completed_migration
```

### restricted

```solidity
modifier restricted()
```

### setCompleted

```solidity
function setCompleted(uint256 completed) public
```

## CreatorCore

_Core creator implementation_

### _tokenCount

```solidity
uint256 _tokenCount
```

### _extensions

```solidity
struct EnumerableSet.AddressSet _extensions
```

### _blacklistedExtensions

```solidity
struct EnumerableSet.AddressSet _blacklistedExtensions
```

### _extensionPermissions

```solidity
mapping(address &#x3D;&gt; address) _extensionPermissions
```

### _extensionApproveTransfers

```solidity
mapping(address &#x3D;&gt; bool) _extensionApproveTransfers
```

### _tokensExtension

```solidity
mapping(uint256 &#x3D;&gt; address) _tokensExtension
```

### _extensionBaseURI

```solidity
mapping(address &#x3D;&gt; string) _extensionBaseURI
```

### _extensionBaseURIIdentical

```solidity
mapping(address &#x3D;&gt; bool) _extensionBaseURIIdentical
```

### _extensionURIPrefix

```solidity
mapping(address &#x3D;&gt; string) _extensionURIPrefix
```

### _tokenURIs

```solidity
mapping(uint256 &#x3D;&gt; string) _tokenURIs
```

### _extensionRoyaltyReceivers

```solidity
mapping(address &#x3D;&gt; address payable[]) _extensionRoyaltyReceivers
```

### _extensionRoyaltyBPS

```solidity
mapping(address &#x3D;&gt; uint256[]) _extensionRoyaltyBPS
```

### _tokenRoyaltyReceivers

```solidity
mapping(uint256 &#x3D;&gt; address payable[]) _tokenRoyaltyReceivers
```

### _tokenRoyaltyBPS

```solidity
mapping(uint256 &#x3D;&gt; uint256[]) _tokenRoyaltyBPS
```

### _INTERFACE_ID_ROYALTIES_CREATORCORE

```solidity
bytes4 _INTERFACE_ID_ROYALTIES_CREATORCORE
```

@dev CreatorCore

 bytes4(keccak256(&#x27;getRoyalties(uint256)&#x27;)) &#x3D;&#x3D; 0xbb3bafd6

 &#x3D;&gt; 0xbb3bafd6 &#x3D; 0xbb3bafd6

### _INTERFACE_ID_ROYALTIES_RARIBLE

```solidity
bytes4 _INTERFACE_ID_ROYALTIES_RARIBLE
```

@dev Rarible: RoyaltiesV1

 bytes4(keccak256(&#x27;getFeeRecipients(uint256)&#x27;)) &#x3D;&#x3D; 0xb9c4d9fb
 bytes4(keccak256(&#x27;getFeeBps(uint256)&#x27;)) &#x3D;&#x3D; 0x0ebd4c7f

 &#x3D;&gt; 0xb9c4d9fb ^ 0x0ebd4c7f &#x3D; 0xb7799584

### _INTERFACE_ID_ROYALTIES_FOUNDATION

```solidity
bytes4 _INTERFACE_ID_ROYALTIES_FOUNDATION
```

@dev Foundation

 bytes4(keccak256(&#x27;getFees(uint256)&#x27;)) &#x3D;&#x3D; 0xd5a06d4c

 &#x3D;&gt; 0xd5a06d4c &#x3D; 0xd5a06d4c

### _INTERFACE_ID_ROYALTIES_EIP2981

```solidity
bytes4 _INTERFACE_ID_ROYALTIES_EIP2981
```

@dev EIP-2981

bytes4(keccak256(&quot;royaltyInfo(uint256,uint256)&quot;)) &#x3D;&#x3D; 0x2a55205a

&#x3D;&gt; 0x2a55205a &#x3D; 0x2a55205a

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### extensionRequired

```solidity
modifier extensionRequired()
```

_Only allows registered extensions to call the specified function_

### nonBlacklistRequired

```solidity
modifier nonBlacklistRequired(address extension)
```

_Only allows non-blacklisted extensions_

### getExtensions

```solidity
function getExtensions() external view returns (address[] extensions)
```

_See {ICreatorCore-getExtensions}._

### _registerExtension

```solidity
function _registerExtension(address extension, string baseURI, bool baseURIIdentical) internal
```

_Register an extension_

### _unregisterExtension

```solidity
function _unregisterExtension(address extension) internal
```

_Unregister an extension_

### _blacklistExtension

```solidity
function _blacklistExtension(address extension) internal
```

_Blacklist an extension_

### _setBaseTokenURIExtension

```solidity
function _setBaseTokenURIExtension(string uri, bool identical) internal
```

_Set base token uri for an extension_

### _setTokenURIPrefixExtension

```solidity
function _setTokenURIPrefixExtension(string prefix) internal
```

_Set token uri prefix for an extension_

### _setTokenURIExtension

```solidity
function _setTokenURIExtension(uint256 tokenId, string uri) internal
```

_Set token uri for a token of an extension_

### _setBaseTokenURI

```solidity
function _setBaseTokenURI(string uri) internal
```

_Set base token uri for tokens with no extension_

### _setTokenURIPrefix

```solidity
function _setTokenURIPrefix(string prefix) internal
```

_Set token uri prefix for tokens with no extension_

### _setTokenURI

```solidity
function _setTokenURI(uint256 tokenId, string uri) internal
```

_Set token uri for a token with no extension_

### _tokenURI

```solidity
function _tokenURI(uint256 tokenId) internal view returns (string)
```

_Retrieve a token&#x27;s URI_

### _tokenExtension

```solidity
function _tokenExtension(uint256 tokenId) internal view returns (address extension)
```

Get token extension

### _getRoyalties

```solidity
function _getRoyalties(uint256 tokenId) internal view returns (address payable[], uint256[])
```

Helper to get royalties for a token

### _getRoyaltyReceivers

```solidity
function _getRoyaltyReceivers(uint256 tokenId) internal view returns (address payable[])
```

Helper to get royalty receivers for a token

### _getRoyaltyBPS

```solidity
function _getRoyaltyBPS(uint256 tokenId) internal view returns (uint256[])
```

Helper to get royalty basis points for a token

### _getRoyaltyInfo

```solidity
function _getRoyaltyInfo(uint256 tokenId, uint256 value) internal view returns (address receiver, uint256 amount)
```

### _setRoyalties

```solidity
function _setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) internal
```

Set royalties for a token

### _setRoyaltiesExtension

```solidity
function _setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) internal
```

Set royalties for all tokens of an extension

## ERC1155CreatorCore

_Core ERC1155 creator implementation_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### setApproveTransferExtension

```solidity
function setApproveTransferExtension(bool enabled) external
```

_See {ICreatorCore-setApproveTransferExtension}._

### _setMintPermissions

```solidity
function _setMintPermissions(address extension, address permissions) internal
```

_Set mint permissions for an extension_

### _checkMintPermissions

```solidity
function _checkMintPermissions(address[] to, uint256[] tokenIds, uint256[] amounts) internal
```

Check if an extension can mint

### _postBurn

```solidity
function _postBurn(address owner, uint256[] tokenIds, uint256[] amounts) internal virtual
```

Post burn actions

### _approveTransfer

```solidity
function _approveTransfer(address from, address to, uint256[] tokenIds, uint256[] amounts) internal
```

Approve a transfer

## ERC721CreatorCore

_Core ERC721 creator implementation_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### setApproveTransferExtension

```solidity
function setApproveTransferExtension(bool enabled) external
```

_See {ICreatorCore-setApproveTransferExtension}._

### _setMintPermissions

```solidity
function _setMintPermissions(address extension, address permissions) internal
```

_Set mint permissions for an extension_

### _checkMintPermissions

```solidity
function _checkMintPermissions(address to, uint256 tokenId) internal
```

Check if an extension can mint

### _postMintBase

```solidity
function _postMintBase(address, uint256) internal virtual
```

Override for post mint actions

### _postMintExtension

```solidity
function _postMintExtension(address, uint256) internal virtual
```

Override for post mint actions

### _postBurn

```solidity
function _postBurn(address owner, uint256 tokenId) internal virtual
```

Post-burning callback and metadata cleanup

### _approveTransfer

```solidity
function _approveTransfer(address from, address to, uint256 tokenId) internal
```

Approve a transfer

## ERC721CreatorCoreEnumerable

_Core ERC721 creator implementation (with enumerable api&#x27;s)_

### _extensionBalances

```solidity
mapping(address &#x3D;&gt; uint256) _extensionBalances
```

### _extensionTokens

```solidity
mapping(address &#x3D;&gt; mapping(uint256 &#x3D;&gt; uint256)) _extensionTokens
```

### _extensionTokensIndex

```solidity
mapping(uint256 &#x3D;&gt; uint256) _extensionTokensIndex
```

### _extensionBalancesByOwner

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; uint256)) _extensionBalancesByOwner
```

### _extensionTokensByOwner

```solidity
mapping(address &#x3D;&gt; mapping(address &#x3D;&gt; mapping(uint256 &#x3D;&gt; uint256))) _extensionTokensByOwner
```

### _extensionTokensIndexByOwner

```solidity
mapping(uint256 &#x3D;&gt; uint256) _extensionTokensIndexByOwner
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### totalSupplyExtension

```solidity
function totalSupplyExtension(address extension) public view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-totalSupplyExtension}._

### tokenByIndexExtension

```solidity
function tokenByIndexExtension(address extension, uint256 index) external view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-tokenByIndexExtension}._

### balanceOfExtension

```solidity
function balanceOfExtension(address extension, address owner) public view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-balanceOfExtension}._

### tokenOfOwnerByIndexExtension

```solidity
function tokenOfOwnerByIndexExtension(address extension, address owner, uint256 index) external view virtual returns (uint256)
```

### totalSupplyBase

```solidity
function totalSupplyBase() public view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-totalSupplyBase}._

### tokenByIndexBase

```solidity
function tokenByIndexBase(uint256 index) external view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-tokenByIndexBase}._

### balanceOfBase

```solidity
function balanceOfBase(address owner) public view virtual returns (uint256)
```

_See {IERC721CreatorCoreEnumerable-balanceOfBase}._

### tokenOfOwnerByIndexBase

```solidity
function tokenOfOwnerByIndexBase(address owner, uint256 index) external view virtual returns (uint256)
```

### _addTokenToOwnerEnumeration

```solidity
function _addTokenToOwnerEnumeration(address to, uint256 tokenId, address tokenExtension_) private
```

### _removeTokenFromOwnerEnumeration

```solidity
function _removeTokenFromOwnerEnumeration(address from, uint256 tokenId, address tokenExtension_) private
```

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address from, address to, uint256 tokenId) internal virtual
```

### _postMintBase

```solidity
function _postMintBase(address to, uint256 tokenId) internal virtual
```

### _postMintExtension

```solidity
function _postMintExtension(address to, uint256 tokenId) internal virtual
```

### _postBurn

```solidity
function _postBurn(address owner, uint256 tokenId) internal virtual
```

Post-burning callback and metadata cleanup

## ICreatorCore

_Core creator interface_

### ExtensionRegistered

```solidity
event ExtensionRegistered(address extension, address sender)
```

### ExtensionUnregistered

```solidity
event ExtensionUnregistered(address extension, address sender)
```

### ExtensionBlacklisted

```solidity
event ExtensionBlacklisted(address extension, address sender)
```

### MintPermissionsUpdated

```solidity
event MintPermissionsUpdated(address extension, address permissions, address sender)
```

### RoyaltiesUpdated

```solidity
event RoyaltiesUpdated(uint256 tokenId, address payable[] receivers, uint256[] basisPoints)
```

### DefaultRoyaltiesUpdated

```solidity
event DefaultRoyaltiesUpdated(address payable[] receivers, uint256[] basisPoints)
```

### ExtensionRoyaltiesUpdated

```solidity
event ExtensionRoyaltiesUpdated(address extension, address payable[] receivers, uint256[] basisPoints)
```

### ExtensionApproveTransferUpdated

```solidity
event ExtensionApproveTransferUpdated(address extension, bool enabled)
```

### getExtensions

```solidity
function getExtensions() external view returns (address[])
```

_gets address of all extensions_

### registerExtension

```solidity
function registerExtension(address extension, string baseURI) external
```

_add an extension.  Can only be called by contract owner or admin.
extension address must point to a contract implementing ICreatorExtension.
Returns True if newly added, False if already added._

### registerExtension

```solidity
function registerExtension(address extension, string baseURI, bool baseURIIdentical) external
```

_add an extension.  Can only be called by contract owner or admin.
extension address must point to a contract implementing ICreatorExtension.
Returns True if newly added, False if already added._

### unregisterExtension

```solidity
function unregisterExtension(address extension) external
```

_add an extension.  Can only be called by contract owner or admin.
Returns True if removed, False if already removed._

### blacklistExtension

```solidity
function blacklistExtension(address extension) external
```

_blacklist an extension.  Can only be called by contract owner or admin.
This function will destroy all ability to reference the metadata of any tokens created
by the specified extension. It will also unregister the extension if needed.
Returns True if removed, False if already removed._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri) external
```

_set the baseTokenURI of an extension.  Can only be called by extension._

### setBaseTokenURIExtension

```solidity
function setBaseTokenURIExtension(string uri, bool identical) external
```

_set the baseTokenURI of an extension.  Can only be called by extension.
For tokens with no uri configured, tokenURI will return &quot;uri+tokenId&quot;_

### setTokenURIPrefixExtension

```solidity
function setTokenURIPrefixExtension(string prefix) external
```

_set the common prefix of an extension.  Can only be called by extension.
If configured, and a token has a uri set, tokenURI will return &quot;prefixURI+tokenURI&quot;
Useful if you want to use ipfs/arweave_

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256 tokenId, string uri) external
```

_set the tokenURI of a token extension.  Can only be called by extension that minted token._

### setTokenURIExtension

```solidity
function setTokenURIExtension(uint256[] tokenId, string[] uri) external
```

_set the tokenURI of a token extension for multiple tokens.  Can only be called by extension that minted token._

### setBaseTokenURI

```solidity
function setBaseTokenURI(string uri) external
```

_set the baseTokenURI for tokens with no extension.  Can only be called by owner/admin.
For tokens with no uri configured, tokenURI will return &quot;uri+tokenId&quot;_

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(string prefix) external
```

_set the common prefix for tokens with no extension.  Can only be called by owner/admin.
If configured, and a token has a uri set, tokenURI will return &quot;prefixURI+tokenURI&quot;
Useful if you want to use ipfs/arweave_

### setTokenURI

```solidity
function setTokenURI(uint256 tokenId, string uri) external
```

_set the tokenURI of a token with no extension.  Can only be called by owner/admin._

### setTokenURI

```solidity
function setTokenURI(uint256[] tokenIds, string[] uris) external
```

_set the tokenURI of multiple tokens with no extension.  Can only be called by owner/admin._

### setMintPermissions

```solidity
function setMintPermissions(address extension, address permissions) external
```

_set a permissions contract for an extension.  Used to control minting._

### setApproveTransferExtension

```solidity
function setApproveTransferExtension(bool enabled) external
```

_Configure so transfers of tokens created by the caller (must be extension) gets approval
from the extension before transferring_

### tokenExtension

```solidity
function tokenExtension(uint256 tokenId) external view returns (address)
```

_get the extension of a given token_

### setRoyalties

```solidity
function setRoyalties(address payable[] receivers, uint256[] basisPoints) external
```

_Set default royalties_

### setRoyalties

```solidity
function setRoyalties(uint256 tokenId, address payable[] receivers, uint256[] basisPoints) external
```

_Set royalties of a token_

### setRoyaltiesExtension

```solidity
function setRoyaltiesExtension(address extension, address payable[] receivers, uint256[] basisPoints) external
```

_Set royalties of an extension_

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view returns (address payable[], uint256[])
```

_Get royalites of a token.  Returns list of receivers and basisPoints_

### getFeeRecipients

```solidity
function getFeeRecipients(uint256 tokenId) external view returns (address payable[])
```

### getFeeBps

```solidity
function getFeeBps(uint256 tokenId) external view returns (uint256[])
```

### getFees

```solidity
function getFees(uint256 tokenId) external view returns (address payable[], uint256[])
```

### royaltyInfo

```solidity
function royaltyInfo(uint256 tokenId, uint256 value) external view returns (address, uint256)
```

## IERC1155CreatorCore

_Core ERC1155 creator interface_

### mintBaseNew

```solidity
function mintBaseNew(address[] to, uint256[] amounts, string[] uris) external returns (uint256[])
```

_mint a token with no extension. Can only be called by an admin._

| Name | Type | Description |
| ---- | ---- | ----------- |
| to | address[] | - Can be a single element array (all tokens go to same address) or multi-element array (single token to many recipients) |
| amounts | uint256[] | - Can be a single element array (all recipients get the same amount) or a multi-element array |
| uris | string[] | - If no elements, all tokens use the default uri.                   If any element is an empty string, the corresponding token uses the default uri. Requirements: If to is a multi-element array, then uris must be empty or single element array               If to is a multi-element array, then amounts must be a single element array or a multi-element array of the same size               If to is a single element array, uris must be empty or the same length as amounts Examples:    mintBaseNew([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [])        Mints a single new token, and gives 1 each to &#x27;0x....1&#x27; and &#x27;0x....2&#x27;.  Token uses default uri.        mintBaseNew([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1, 2], [])        Mints a single new token, and gives 1 to &#x27;0x....1&#x27; and 2 to &#x27;0x....2&#x27;.  Token uses default uri.        mintBaseNew([&#x27;0x....1&#x27;], [1, 2], [&quot;&quot;, &quot;http://token2.com&quot;])        Mints two new tokens to &#x27;0x....1&#x27;. 1 of the first token, 2 of the second.  1st token uses default uri, second uses &quot;http://token2.com&quot;. |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | uint256[] | Returns list of tokenIds minted |

### mintBaseExisting

```solidity
function mintBaseExisting(address[] to, uint256[] tokenIds, uint256[] amounts) external
```

_batch mint existing token with no extension. Can only be called by an admin._

| Name | Type | Description |
| ---- | ---- | ----------- |
| to | address[] | - Can be a single element array (all tokens go to same address) or multi-element array (single token to many recipients) |
| tokenIds | uint256[] | - Can be a single element array (all recipients get the same token) or a multi-element array |
| amounts | uint256[] | - Can be a single element array (all recipients get the same amount) or a multi-element array Requirements: If any of the parameters are multi-element arrays, they need to be the same length as other multi-element arrays Examples:    mintBaseExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [10])        Mints 10 of tokenId 1 to each of &#x27;0x....1&#x27; and &#x27;0x....2&#x27;.        mintBaseExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1, 2], [10, 20])        Mints 10 of tokenId 1 to &#x27;0x....1&#x27; and 20 of tokenId 2 to &#x27;0x....2&#x27;.        mintBaseExisting([&#x27;0x....1&#x27;], [1, 2], [10, 20])        Mints 10 of tokenId 1 and 20 of tokenId 2 to &#x27;0x....1&#x27;.        mintBaseExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [10, 20])        Mints 10 of tokenId 1 to &#x27;0x....1&#x27; and 20 of tokenId 1 to &#x27;0x....2&#x27;. |

### mintExtensionNew

```solidity
function mintExtensionNew(address[] to, uint256[] amounts, string[] uris) external returns (uint256[])
```

_mint a token from an extension. Can only be called by a registered extension._

| Name | Type | Description |
| ---- | ---- | ----------- |
| to | address[] | - Can be a single element array (all tokens go to same address) or multi-element array (single token to many recipients) |
| amounts | uint256[] | - Can be a single element array (all recipients get the same amount) or a multi-element array |
| uris | string[] | - If no elements, all tokens use the default uri.                   If any element is an empty string, the corresponding token uses the default uri. Requirements: If to is a multi-element array, then uris must be empty or single element array               If to is a multi-element array, then amounts must be a single element array or a multi-element array of the same size               If to is a single element array, uris must be empty or the same length as amounts Examples:    mintExtensionNew([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [])        Mints a single new token, and gives 1 each to &#x27;0x....1&#x27; and &#x27;0x....2&#x27;.  Token uses default uri.        mintExtensionNew([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1, 2], [])        Mints a single new token, and gives 1 to &#x27;0x....1&#x27; and 2 to &#x27;0x....2&#x27;.  Token uses default uri.        mintExtensionNew([&#x27;0x....1&#x27;], [1, 2], [&quot;&quot;, &quot;http://token2.com&quot;])        Mints two new tokens to &#x27;0x....1&#x27;. 1 of the first token, 2 of the second.  1st token uses default uri, second uses &quot;http://token2.com&quot;. |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | uint256[] | Returns list of tokenIds minted |

### mintExtensionExisting

```solidity
function mintExtensionExisting(address[] to, uint256[] tokenIds, uint256[] amounts) external
```

_batch mint existing token from extension. Can only be called by a registered extension._

| Name | Type | Description |
| ---- | ---- | ----------- |
| to | address[] | - Can be a single element array (all tokens go to same address) or multi-element array (single token to many recipients) |
| tokenIds | uint256[] | - Can be a single element array (all recipients get the same token) or a multi-element array |
| amounts | uint256[] | - Can be a single element array (all recipients get the same amount) or a multi-element array Requirements: If any of the parameters are multi-element arrays, they need to be the same length as other multi-element arrays Examples:    mintExtensionExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [10])        Mints 10 of tokenId 1 to each of &#x27;0x....1&#x27; and &#x27;0x....2&#x27;.        mintExtensionExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1, 2], [10, 20])        Mints 10 of tokenId 1 to &#x27;0x....1&#x27; and 20 of tokenId 2 to &#x27;0x....2&#x27;.        mintExtensionExisting([&#x27;0x....1&#x27;], [1, 2], [10, 20])        Mints 10 of tokenId 1 and 20 of tokenId 2 to &#x27;0x....1&#x27;.        mintExtensionExisting([&#x27;0x....1&#x27;, &#x27;0x....2&#x27;], [1], [10, 20])        Mints 10 of tokenId 1 to &#x27;0x....1&#x27; and 20 of tokenId 1 to &#x27;0x....2&#x27;. |

### burn

```solidity
function burn(address account, uint256[] tokenIds, uint256[] amounts) external
```

_burn tokens. Can only be called by token owner or approved address.
On burn, calls back to the registered extension&#x27;s onBurn method_

### totalSupply

```solidity
function totalSupply(uint256 tokenId) external view returns (uint256)
```

_Total amount of tokens in with a given tokenId._

## IERC721CreatorCore

_Core ERC721 creator interface_

### mintBase

```solidity
function mintBase(address to) external returns (uint256)
```

_mint a token with no extension. Can only be called by an admin.
Returns tokenId minted_

### mintBase

```solidity
function mintBase(address to, string uri) external returns (uint256)
```

_mint a token with no extension. Can only be called by an admin.
Returns tokenId minted_

### mintBaseBatch

```solidity
function mintBaseBatch(address to, uint16 count) external returns (uint256[])
```

_batch mint a token with no extension. Can only be called by an admin.
Returns tokenId minted_

### mintBaseBatch

```solidity
function mintBaseBatch(address to, string[] uris) external returns (uint256[])
```

_batch mint a token with no extension. Can only be called by an admin.
Returns tokenId minted_

### mintExtension

```solidity
function mintExtension(address to) external returns (uint256)
```

_mint a token. Can only be called by a registered extension.
Returns tokenId minted_

### mintExtension

```solidity
function mintExtension(address to, string uri) external returns (uint256)
```

_mint a token. Can only be called by a registered extension.
Returns tokenId minted_

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, uint16 count) external returns (uint256[])
```

_batch mint a token. Can only be called by a registered extension.
Returns tokenIds minted_

### mintExtensionBatch

```solidity
function mintExtensionBatch(address to, string[] uris) external returns (uint256[])
```

_batch mint a token. Can only be called by a registered extension.
Returns tokenId minted_

### burn

```solidity
function burn(uint256 tokenId) external
```

_burn a token. Can only be called by token owner or approved address.
On burn, calls back to the registered extension&#x27;s onBurn method_

## IERC721CreatorCoreEnumerable

_Core ERC721 creator interface (with enumerable api&#x27;s)_

### totalSupplyExtension

```solidity
function totalSupplyExtension(address extension) external view returns (uint256)
```

### tokenByIndexExtension

```solidity
function tokenByIndexExtension(address extension, uint256 index) external view returns (uint256)
```

### balanceOfExtension

```solidity
function balanceOfExtension(address extension, address owner) external view returns (uint256 balance)
```

### tokenOfOwnerByIndexExtension

```solidity
function tokenOfOwnerByIndexExtension(address extension, address owner, uint256 index) external view returns (uint256 tokenId)
```

### totalSupplyBase

```solidity
function totalSupplyBase() external view returns (uint256)
```

### tokenByIndexBase

```solidity
function tokenByIndexBase(uint256 index) external view returns (uint256)
```

### balanceOfBase

```solidity
function balanceOfBase(address owner) external view returns (uint256 balance)
```

### tokenOfOwnerByIndexBase

```solidity
function tokenOfOwnerByIndexBase(address owner, uint256 index) external view returns (uint256 tokenId)
```

## IRoyalties

_Royalty interface for creator core classes_

### getRoyalties

```solidity
function getRoyalties(uint256 tokenId) external view returns (address payable[], uint256[])
```

_Get royalites of a token.  Returns list of receivers and basisPoints_

## CreatorExtension

_Base creator extension variables_

### LEGACY_EXTENSION_INTERFACE

```solidity
bytes4 LEGACY_EXTENSION_INTERFACE
```

_Legacy extension interface identifiers

{IERC165-supportsInterface} needs to return &#x27;true&#x27; for this interface
in order backwards compatible with older creator contracts_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

## CreatorExtensionBasic

_Provides functions to set token uri&#x27;s_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(address creator, string uri) external
```

_See {ICreatorExtensionBasic-setBaseTokenURI}._

### setBaseTokenURI

```solidity
function setBaseTokenURI(address creator, string uri, bool identical) external
```

_See {ICreatorExtensionBasic-setBaseTokenURI}._

### setTokenURI

```solidity
function setTokenURI(address creator, uint256 tokenId, string uri) external
```

_See {ICreatorExtensionBasic-setTokenURI}._

### setTokenURI

```solidity
function setTokenURI(address creator, uint256[] tokenIds, string[] uris) external
```

_See {ICreatorExtensionBasic-setTokenURI}._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(address creator, string prefix) external
```

_See {ICreatorExtensionBasic-setTokenURIPrefix}._

## ERC1155CreatorExtensionApproveTransfer

_Suggested implementation for extensions that require the creator to
check with it before a transfer occurs_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### setApproveTransfer

```solidity
function setApproveTransfer(address creator, bool enabled) external
```

_See {IERC1155CreatorExtensionApproveTransfer-setApproveTransfer}_

## ERC1155CreatorExtensionBurnable

_Suggested implementation for extensions that want to receive onBurn callbacks
Mint tracks the creators/tokens created, and onBurn only accepts callbacks from
the creator of a token created._

### _tokenCreators

```solidity
mapping(uint256 &#x3D;&gt; address) _tokenCreators
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### mintNew

```solidity
function mintNew(address creator, address[] to, uint256[] amounts, string[] uris) external returns (uint256[])
```

_batch mint a token_

### _mintNew

```solidity
function _mintNew(address creator, address[] to, uint256[] amounts, string[] uris) internal returns (uint256[] tokenIds)
```

### onBurn

```solidity
function onBurn(address, uint256[] tokenIds, uint256[]) public virtual
```

_See {IERC1155CreatorExtension-onBurn}._

## IERC1155CreatorExtensionApproveTransfer

Implement this if you want your extension to approve a transfer

### setApproveTransfer

```solidity
function setApproveTransfer(address creator, bool enabled) external
```

_Set whether or not the creator contract will check the extension for approval of token transfer_

### approveTransfer

```solidity
function approveTransfer(address from, address to, uint256[] tokenIds, uint256[] amounts) external returns (bool)
```

_Called by creator contract to approve a transfer_

## IERC1155CreatorExtensionBurnable

_Your extension is required to implement this interface if it wishes
to receive the onBurn callback whenever a token the extension created is
burned_

### onBurn

```solidity
function onBurn(address owner, uint256[] tokenIds, uint256[] amounts) external
```

_callback handler for burn events_

## ERC721CreatorExtension

_Base ERC721 creator extension variables_

### LEGACY_ERC721_EXTENSION_BURNABLE_INTERFACE

```solidity
bytes4 LEGACY_ERC721_EXTENSION_BURNABLE_INTERFACE
```

_Legacy extension interface identifiers (see CreatorExtension for more)

{IERC165-supportsInterface} needs to return &#x27;true&#x27; for this interface
in order backwards compatible with older creator contracts_

## ERC721CreatorExtensionApproveTransfer

_Suggested implementation for extensions that require the creator to
check with it before a transfer occurs_

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### setApproveTransfer

```solidity
function setApproveTransfer(address creator, bool enabled) external
```

_See {IERC721CreatorExtensionApproveTransfer-setApproveTransfer}_

## ERC721CreatorExtensionBurnable

_Suggested implementation for extensions that want to receive onBurn callbacks
Mint tracks the creators/tokens created, and onBurn only accepts callbacks from
the creator of a token created._

### _tokenCreators

```solidity
mapping(uint256 &#x3D;&gt; address) _tokenCreators
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### mint

```solidity
function mint(address creator, address to) external returns (uint256)
```

_mint a token_

### mintBatch

```solidity
function mintBatch(address creator, address to, uint16 count) external returns (uint256[])
```

_batch mint a token_

### _mint

```solidity
function _mint(address creator, address to) internal returns (uint256)
```

### _mint

```solidity
function _mint(address creator, address to, string uri) internal returns (uint256)
```

### _mintBatch

```solidity
function _mintBatch(address creator, address to, uint16 count) internal returns (uint256[] tokenIds)
```

### _mintBatch

```solidity
function _mintBatch(address creator, address to, string[] uris) internal returns (uint256[] tokenIds)
```

### onBurn

```solidity
function onBurn(address, uint256 tokenId) public virtual
```

_See {IERC721CreatorExtension-onBurn}._

## IERC721CreatorExtensionApproveTransfer

Implement this if you want your extension to approve a transfer

### setApproveTransfer

```solidity
function setApproveTransfer(address creator, bool enabled) external
```

_Set whether or not the creator will check the extension for approval of token transfer_

### approveTransfer

```solidity
function approveTransfer(address from, address to, uint256 tokenId) external returns (bool)
```

_Called by creator contract to approve a transfer_

## IERC721CreatorExtensionBurnable

_Your extension is required to implement this interface if it wishes
to receive the onBurn callback whenever a token the extension created is
burned_

### onBurn

```solidity
function onBurn(address owner, uint256 tokenId) external
```

_callback handler for burn events_

## ICreatorExtensionBasic

_Provides functions to set token uri&#x27;s_

### setBaseTokenURI

```solidity
function setBaseTokenURI(address creator, string uri) external
```

_set the baseTokenURI of tokens generated by this extension.  Can only be called by admins._

### setBaseTokenURI

```solidity
function setBaseTokenURI(address creator, string uri, bool identical) external
```

_set the baseTokenURI of tokens generated by this extension.  Can only be called by admins._

### setTokenURI

```solidity
function setTokenURI(address creator, uint256 tokenId, string uri) external
```

_set the tokenURI of a token generated by this extension.  Can only be called by admins._

### setTokenURI

```solidity
function setTokenURI(address creator, uint256[] tokenId, string[] uri) external
```

_set the tokenURI of multiple tokens generated by this extension.  Can only be called by admins._

### setTokenURIPrefix

```solidity
function setTokenURIPrefix(address creator, string prefix) external
```

_set the extension&#x27;s token uri prefix_

## ICreatorExtensionTokenURI

_Implement this if you want your extension to have overloadable URI&#x27;s_

### tokenURI

```solidity
function tokenURI(address creator, uint256 tokenId) external view returns (string)
```

Get the uri for a given creator/tokenId

## MockContract

## MockERC1155

### constructor

```solidity
constructor(string uri_) public
```

### testMint

```solidity
function testMint(address account, uint256 id, uint256 amount, bytes data) external
```

## MockERC1155CreatorExtensionBurnable

### _mintedTokens

```solidity
uint256[] _mintedTokens
```

### _burntTokens

```solidity
mapping(uint256 &#x3D;&gt; uint256) _burntTokens
```

### _creator

```solidity
address _creator
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### constructor

```solidity
constructor(address creator) public
```

### testMintNew

```solidity
function testMintNew(address[] to, uint256[] amounts, string[] uris) external
```

### testMintExisting

```solidity
function testMintExisting(address[] to, uint256[] tokenIds, uint256[] amounts) external
```

### mintedTokens

```solidity
function mintedTokens() external view returns (uint256[])
```

### burntTokens

```solidity
function burntTokens(uint256 tokenId) external view returns (uint256)
```

### onBurn

```solidity
function onBurn(address to, uint256[] tokenIds, uint256[] amounts) public
```

## MockERC1155CreatorExtensionOverride

### _approveEnabled

```solidity
bool _approveEnabled
```

### _tokenURI

```solidity
string _tokenURI
```

### _creator

```solidity
address _creator
```

### constructor

```solidity
constructor(address creator) public
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### testMintNew

```solidity
function testMintNew(address[] to, uint256[] amounts, string[] uris) external
```

### setApproveEnabled

```solidity
function setApproveEnabled(bool enabled) public
```

### setTokenURI

```solidity
function setTokenURI(string uri) public
```

### approveTransfer

```solidity
function approveTransfer(address, address, uint256[], uint256[]) external view virtual returns (bool)
```

### tokenURI

```solidity
function tokenURI(address creator, uint256) external view virtual returns (string)
```

## MockERC1155CreatorMintPermissions

### _approveEnabled

```solidity
bool _approveEnabled
```

### constructor

```solidity
constructor(address creator_) public
```

### setApproveEnabled

```solidity
function setApproveEnabled(bool enabled) external
```

### approveMint

```solidity
function approveMint(address extension, address[] to, uint256[] tokenIds, uint256[] amounts) public
```

## MockERC721

### constructor

```solidity
constructor(string _name, string _symbol) public
```

### testMint

```solidity
function testMint(address to, uint256 tokenId) external
```

## MockERC721CreatorExtensionBurnable

### _mintedTokens

```solidity
uint256[] _mintedTokens
```

### _burntTokens

```solidity
uint256[] _burntTokens
```

### _creator

```solidity
address _creator
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### constructor

```solidity
constructor(address creator) public
```

### testMint

```solidity
function testMint(address to) external
```

### testMint

```solidity
function testMint(address to, string uri) external
```

### testMintBatch

```solidity
function testMintBatch(address to, uint16 count) external
```

### testMintBatch

```solidity
function testMintBatch(address to, string[] uris) external
```

### mintedTokens

```solidity
function mintedTokens() external view returns (uint256[])
```

### burntTokens

```solidity
function burntTokens() external view returns (uint256[])
```

### onBurn

```solidity
function onBurn(address to, uint256 tokenId) public
```

## MockERC721CreatorExtensionOverride

### _approveEnabled

```solidity
bool _approveEnabled
```

### _tokenURI

```solidity
string _tokenURI
```

### _creator

```solidity
address _creator
```

### constructor

```solidity
constructor(address creator) public
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### testMint

```solidity
function testMint(address to) external
```

### setApproveEnabled

```solidity
function setApproveEnabled(bool enabled) public
```

### setTokenURI

```solidity
function setTokenURI(string uri) public
```

### approveTransfer

```solidity
function approveTransfer(address, address, uint256) external view virtual returns (bool)
```

### tokenURI

```solidity
function tokenURI(address creator, uint256) external view virtual returns (string)
```

## MockERC721CreatorMintPermissions

### _approveEnabled

```solidity
bool _approveEnabled
```

### constructor

```solidity
constructor(address creator_) public
```

### setApproveEnabled

```solidity
function setApproveEnabled(bool enabled) external
```

### approveMint

```solidity
function approveMint(address extension, address to, uint256 tokenId) public
```

## ERC1155CreatorMintPermissions

_Basic implementation of a permission contract that works with a singular creator contract.
approveMint requires the sender to be the configured creator._

### _creator

```solidity
address _creator
```

### constructor

```solidity
constructor(address creator_) internal
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### approveMint

```solidity
function approveMint(address, address[], uint256[], uint256[]) public virtual
```

_See {IERC1155CreatorMintPermissions-approve}._

## IERC1155CreatorMintPermissions

_Required interface of an ERC1155Creator compliant extension contracts._

### approveMint

```solidity
function approveMint(address extension, address[] to, uint256[] tokenIds, uint256[] amounts) external
```

_get approval to mint_

## ERC721CreatorMintPermissions

_Basic implementation of a permission contract that works with a singular creator contract.
approveMint requires the sender to be the configured creator._

### _creator

```solidity
address _creator
```

### constructor

```solidity
constructor(address creator_) internal
```

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### approveMint

```solidity
function approveMint(address, address, uint256) public virtual
```

_See {IERC721CreatorMintPermissions-approve}._

## IERC721CreatorMintPermissions

_Required interface of an ERC721Creator compliant extension contracts._

### approveMint

```solidity
function approveMint(address extension, address to, uint256 tokenId) external
```

_get approval to mint_


# Browser API documentation

## Class: Mesh

The main class for this package. Has methods for receiving order events and sending orders through the 0x Mesh network.

#### Hierarchy

* **Mesh**

#### Constructors

### constructer

+ **new Mesh**\(`config`: [Config](reference.md#interface-config)\): [_Mesh_](reference.md#class-mesh)

_Defined in_ [_index.ts:573_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L573)

Instantiates a new Mesh instance.

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| `config` | [Config](reference.md#interface-config) | Configuration options for Mesh |

**Returns:** [_Mesh_](reference.md#class-mesh)

An instance of Mesh

#### Methods

### addOrdersAsync

▸ **addOrdersAsync**\(`orders`: SignedOrder\[\], `pinned`: boolean\): _Promise‹_[_ValidationResults_](reference.md#interface-validationresults)_›_

_Defined in_ [_index.ts:647_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L647)

Validates and adds the given orders to Mesh. If an order is successfully added, Mesh will share it with any peers in the network and start watching it for changes \(e.g. filled, canceled, expired\). The returned promise will only be rejected if there was an error validating or adding the order; it will not be rejected for any invalid orders \(check results.rejected instead\).

**Parameters:**

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `orders` | SignedOrder\[\] | - | An array of orders to add. |
| `pinned` | boolean | true | Whether or not the orders should be pinned. Pinned orders will not be affected by any DDoS prevention or incentive mechanisms and will always stay in storage until they are no longer fillable. |

**Returns:** _Promise‹_[_ValidationResults_](reference.md#interface-validationresults)_›_

Validation results for the given orders, indicating which orders were accepted and which were rejected.

### onError

▸ **onError**\(`handler`: function\): _void_

_Defined in_ [_index.ts:593_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L593)

Registers a handler which will be called in the event of a critical error. Note that the handler will not be called for non-critical errors. In order to ensure no errors are missed, this should be called before startAsync.

**Parameters:**

▪ **handler**: _function_

The handler to be called.

▸ \(`err`: Error\): _void_

**Parameters:**

| Name | Type |
| :--- | :--- |
| `err` | Error |

**Returns:** _void_

### onOrderEvents

▸ **onOrderEvents**\(`handler`: function\): _void_

_Defined in_ [_index.ts:608_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L608)

Registers a handler which will be called for any incoming order events. Order events are fired whenver an order is added, canceled, expired, or filled. In order to ensure no events are missed, this should be called before startAsync.

**Parameters:**

▪ **handler**: _function_

The handler to be called.

▸ \(`events`: [OrderEvent](reference.md#interface-orderevent)\[\]\): _void_

**Parameters:**

| Name | Type |
| :--- | :--- |
| `events` | [OrderEvent](reference.md#interface-orderevent)\[\] |

**Returns:** _void_

### startAsync

▸ **startAsync**\(\): _Promise‹void›_

_Defined in_ [_index.ts:619_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L619)

Starts the Mesh node in the background. Mesh will automatically find peers in the network and begin receiving orders from them.

**Returns:** _Promise‹void›_

## Enumeration: OrderEventEndState

#### Enumeration members

### Added

• **Added**: = "ADDED"

_Defined in_ [_index.ts:436_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L436)

### Cancelled

• **Cancelled**: = "CANCELLED"

_Defined in_ [_index.ts:439_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L439)

### Expired

• **Expired**: = "EXPIRED"

_Defined in_ [_index.ts:440_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L440)

### FillabilityIncreased

• **FillabilityIncreased**: = "FILLABILITY\_INCREASED"

_Defined in_ [_index.ts:443_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L443)

### Filled

• **Filled**: = "FILLED"

_Defined in_ [_index.ts:437_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L437)

### FullyFilled

• **FullyFilled**: = "FULLY\_FILLED"

_Defined in_ [_index.ts:438_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L438)

### Invalid

• **Invalid**: = "INVALID"

_Defined in_ [_index.ts:435_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L435)

### StoppedWatching

• **StoppedWatching**: = "STOPPED\_WATCHING"

_Defined in_ [_index.ts:444_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L444)

### Unexpired

• **Unexpired**: = "UNEXPIRED"

_Defined in_ [_index.ts:441_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L441)

### Unfunded

• **Unfunded**: = "UNFUNDED"

_Defined in_ [_index.ts:442_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L442)

## Enumeration: RejectedOrderKind

A set of categories for rejected orders.

#### Enumeration members

### CoordinatorError

• **CoordinatorError**: = "COORDINATOR\_ERROR"

_Defined in_ [_index.ts:527_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L527)

### MeshError

• **MeshError**: = "MESH\_ERROR"

_Defined in_ [_index.ts:525_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L525)

### MeshValidation

• **MeshValidation**: = "MESH\_VALIDATION"

_Defined in_ [_index.ts:526_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L526)

### ZeroExValidation

• **ZeroExValidation**: = "ZEROEX\_VALIDATION"

_Defined in_ [_index.ts:524_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L524)

## Enumeration: Verbosity

#### Enumeration members

### Debug

• **Debug**: = 5

_Defined in_ [_index.ts:149_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L149)

### Error

• **Error**: = 2

_Defined in_ [_index.ts:146_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L146)

### Fatal

• **Fatal**: = 1

_Defined in_ [_index.ts:145_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L145)

### Info

• **Info**: = 4

_Defined in_ [_index.ts:148_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L148)

### Panic

• **Panic**: = 0

_Defined in_ [_index.ts:144_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L144)

### Trace

• **Trace**: = 6

_Defined in_ [_index.ts:150_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L150)

### Warn

• **Warn**: = 3

_Defined in_ [_index.ts:147_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L147)

## Interface: AcceptedOrderInfo

Info for any orders that were accepted.

#### Hierarchy

* **AcceptedOrderInfo**

#### Properties

### fillableTakerAssetAmount

• **fillableTakerAssetAmount**: _BigNumber_

_Defined in_ [_index.ts:505_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L505)

### isNew

• **isNew**: _boolean_

_Defined in_ [_index.ts:506_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L506)

### orderHash

• **orderHash**: _string_

_Defined in_ [_index.ts:503_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L503)

### signedOrder

• **signedOrder**: _SignedOrder_

_Defined in_ [_index.ts:504_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L504)

## Interface: Config

A set of configuration options for Mesh.

#### Hierarchy

* **Config**

#### Properties

### `Optional` blockPollingIntervalSeconds

• **blockPollingIntervalSeconds**? : _undefined \| number_

_Defined in_ [_index.ts:79_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L79)

### `Optional` bootstrapList

• **bootstrapList**? : _string\[\]_

_Defined in_ [_index.ts:72_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L72)

### `Optional` customContractAddresses

• **customContractAddresses**? : [_ContractAddresses_](reference.md#class-contractaddresses)

_Defined in_ [_index.ts:123_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L123)

### `Optional` enableEthereumRPCRateLimiting

• **enableEthereumRPCRateLimiting**? : _undefined \| false \| true_

_Defined in_ [_index.ts:96_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L96)

### ethereumChainID

• **ethereumChainID**: _number_

_Defined in_ [_index.ts:64_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L64)

### `Optional` ethereumRPCMaxContentLength

• **ethereumRPCMaxContentLength**? : _undefined \| number_

_Defined in_ [_index.ts:88_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L88)

### `Optional` ethereumRPCMaxRequestsPer24HrUTC

• **ethereumRPCMaxRequestsPer24HrUTC**? : _undefined \| number_

_Defined in_ [_index.ts:101_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L101)

### `Optional` ethereumRPCMaxRequestsPerSecond

• **ethereumRPCMaxRequestsPerSecond**? : _undefined \| number_

_Defined in_ [_index.ts:107_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L107)

### ethereumRPCURL

• **ethereumRPCURL**: _string_

_Defined in_ [_index.ts:61_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L61)

### `Optional` maxOrdersInStorage

• **maxOrdersInStorage**? : _undefined \| number_

_Defined in_ [_index.ts:128_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L128)

### `Optional` useBootstrapList

• **useBootstrapList**? : _undefined \| false \| true_

_Defined in_ [_index.ts:67_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L67)

### `Optional` verbosity

• **verbosity**? : [_Verbosity_](reference.md#enumeration-verbosity)

_Defined in_ [_index.ts:58_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L58)

## Interface: ContractAddresses

#### Hierarchy

* **ContractAddresses**

#### Properties

### `Optional` coordinator

• **coordinator**? : _undefined \| string_

_Defined in_ [_index.ts:137_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L137)

### `Optional` coordinatorRegistry

• **coordinatorRegistry**? : _undefined \| string_

_Defined in_ [_index.ts:138_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L138)

### devUtils

• **devUtils**: _string_

_Defined in_ [_index.ts:133_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L133)

### erc1155Proxy

• **erc1155Proxy**: _string_

_Defined in_ [_index.ts:136_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L136)

### erc20Proxy

• **erc20Proxy**: _string_

_Defined in_ [_index.ts:134_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L134)

### erc721Proxy

• **erc721Proxy**: _string_

_Defined in_ [_index.ts:135_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L135)

### exchange

• **exchange**: _string_

_Defined in_ [_index.ts:132_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L132)

### `Optional` weth9

• **weth9**? : _undefined \| string_

_Defined in_ [_index.ts:139_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L139)

### `Optional` zrxToken

• **zrxToken**? : _undefined \| string_

_Defined in_ [_index.ts:140_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L140)

## Interface: ContractEvent

#### Hierarchy

* **ContractEvent**

#### Properties

### address

• **address**: _string_

_Defined in_ [_index.ts:417_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L417)

### blockHash

• **blockHash**: _string_

_Defined in_ [_index.ts:412_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L412)

### isRemoved

• **isRemoved**: _string_

_Defined in_ [_index.ts:416_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L416)

### kind

• **kind**: _ContractEventKind_

_Defined in_ [_index.ts:418_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L418)

### logIndex

• **logIndex**: _number_

_Defined in_ [_index.ts:415_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L415)

### parameters

• **parameters**: _ContractEventParameters_

_Defined in_ [_index.ts:419_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L419)

### txHash

• **txHash**: _string_

_Defined in_ [_index.ts:413_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L413)

### txIndex

• **txIndex**: _number_

_Defined in_ [_index.ts:414_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L414)

## Interface: ERC1155ApprovalForAllEvent

#### Hierarchy

* **ERC1155ApprovalForAllEvent**

#### Properties

### approved

• **approved**: _boolean_

_Defined in_ [_index.ts:293_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L293)

### operator

• **operator**: _string_

_Defined in_ [_index.ts:292_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L292)

### owner

• **owner**: _string_

_Defined in_ [_index.ts:291_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L291)

## Interface: ERC1155TransferBatchEvent

#### Hierarchy

* **ERC1155TransferBatchEvent**

#### Properties

### from

• **from**: _string_

_Defined in_ [_index.ts:276_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L276)

### ids

• **ids**: _BigNumber\[\]_

_Defined in_ [_index.ts:278_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L278)

### operator

• **operator**: _string_

_Defined in_ [_index.ts:275_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L275)

### to

• **to**: _string_

_Defined in_ [_index.ts:277_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L277)

### values

• **values**: _BigNumber\[\]_

_Defined in_ [_index.ts:279_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L279)

## Interface: ERC1155TransferSingleEvent

#### Hierarchy

* **ERC1155TransferSingleEvent**

#### Properties

### from

• **from**: _string_

_Defined in_ [_index.ts:260_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L260)

### id

• **id**: _BigNumber_

_Defined in_ [_index.ts:262_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L262)

### operator

• **operator**: _string_

_Defined in_ [_index.ts:259_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L259)

### to

• **to**: _string_

_Defined in_ [_index.ts:261_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L261)

### value

• **value**: _BigNumber_

_Defined in_ [_index.ts:263_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L263)

## Interface: ERC20ApprovalEvent

#### Hierarchy

* **ERC20ApprovalEvent**

#### Properties

### owner

• **owner**: _string_

_Defined in_ [_index.ts:217_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L217)

### spender

• **spender**: _string_

_Defined in_ [_index.ts:218_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L218)

### value

• **value**: _BigNumber_

_Defined in_ [_index.ts:219_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L219)

## Interface: ERC20TransferEvent

#### Hierarchy

* **ERC20TransferEvent**

#### Properties

### from

• **from**: _string_

_Defined in_ [_index.ts:205_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L205)

### to

• **to**: _string_

_Defined in_ [_index.ts:206_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L206)

### value

• **value**: _BigNumber_

_Defined in_ [_index.ts:207_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L207)

## Interface: ERC721ApprovalEvent

#### Hierarchy

* **ERC721ApprovalEvent**

#### Properties

### approved

• **approved**: _string_

_Defined in_ [_index.ts:242_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L242)

### owner

• **owner**: _string_

_Defined in_ [_index.ts:241_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L241)

### tokenId

• **tokenId**: _BigNumber_

_Defined in_ [_index.ts:243_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L243)

## Interface: ERC721ApprovalForAllEvent

#### Hierarchy

* **ERC721ApprovalForAllEvent**

#### Properties

### approved

• **approved**: _boolean_

_Defined in_ [_index.ts:255_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L255)

### operator

• **operator**: _string_

_Defined in_ [_index.ts:254_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L254)

### owner

• **owner**: _string_

_Defined in_ [_index.ts:253_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L253)

## Interface: ERC721TransferEvent

#### Hierarchy

* **ERC721TransferEvent**

#### Properties

### from

• **from**: _string_

_Defined in_ [_index.ts:229_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L229)

### to

• **to**: _string_

_Defined in_ [_index.ts:230_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L230)

### tokenId

• **tokenId**: _BigNumber_

_Defined in_ [_index.ts:231_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L231)

## Interface: ExchangeCancelEvent

#### Hierarchy

* **ExchangeCancelEvent**

#### Properties

### feeRecipientAddress

• **feeRecipientAddress**: _string_

_Defined in_ [_index.ts:327_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L327)

### makerAddress

• **makerAddress**: _string_

_Defined in_ [_index.ts:325_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L325)

### makerAssetData

• **makerAssetData**: _string_

_Defined in_ [_index.ts:329_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L329)

### orderHash

• **orderHash**: _string_

_Defined in_ [_index.ts:328_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L328)

### senderAddress

• **senderAddress**: _string_

_Defined in_ [_index.ts:326_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L326)

### takerAssetData

• **takerAssetData**: _string_

_Defined in_ [_index.ts:330_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L330)

## Interface: ExchangeCancelUpToEvent

#### Hierarchy

* **ExchangeCancelUpToEvent**

#### Properties

### makerAddress

• **makerAddress**: _string_

_Defined in_ [_index.ts:334_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L334)

### orderEpoch

• **orderEpoch**: _BigNumber_

_Defined in_ [_index.ts:336_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L336)

### senderAddress

• **senderAddress**: _string_

_Defined in_ [_index.ts:335_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L335)

## Interface: ExchangeFillEvent

#### Hierarchy

* **ExchangeFillEvent**

#### Properties

### feeRecipientAddress

• **feeRecipientAddress**: _string_

_Defined in_ [_index.ts:300_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L300)

### makerAddress

• **makerAddress**: _string_

_Defined in_ [_index.ts:297_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L297)

### makerAssetData

• **makerAssetData**: _string_

_Defined in_ [_index.ts:306_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L306)

### makerAssetFilledAmount

• **makerAssetFilledAmount**: _BigNumber_

_Defined in_ [_index.ts:301_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L301)

### makerFeePaid

• **makerFeePaid**: _BigNumber_

_Defined in_ [_index.ts:303_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L303)

### orderHash

• **orderHash**: _string_

_Defined in_ [_index.ts:305_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L305)

### senderAddress

• **senderAddress**: _string_

_Defined in_ [_index.ts:299_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L299)

### takerAddress

• **takerAddress**: _string_

_Defined in_ [_index.ts:298_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L298)

### takerAssetData

• **takerAssetData**: _string_

_Defined in_ [_index.ts:307_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L307)

### takerAssetFilledAmount

• **takerAssetFilledAmount**: _BigNumber_

_Defined in_ [_index.ts:302_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L302)

### takerFeePaid

• **takerFeePaid**: _BigNumber_

_Defined in_ [_index.ts:304_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L304)

## Interface: OrderEvent

Order events are fired by Mesh whenever an order is added, canceled, expired, or filled.

#### Hierarchy

* **OrderEvent**

#### Properties

### contractEvents

• **contractEvents**: [_ContractEvent_](reference.md#class-contractevent)_\[\]_

_Defined in_ [_index.ts:466_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L466)

### endState

• **endState**: [_OrderEventEndState_](reference.md#enumeration-ordereventendstate)

_Defined in_ [_index.ts:464_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L464)

### fillableTakerAssetAmount

• **fillableTakerAssetAmount**: _BigNumber_

_Defined in_ [_index.ts:465_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L465)

### orderHash

• **orderHash**: _string_

_Defined in_ [_index.ts:462_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L462)

### signedOrder

• **signedOrder**: _SignedOrder_

_Defined in_ [_index.ts:463_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L463)

### timestampMs

• **timestampMs**: _number_

_Defined in_ [_index.ts:461_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L461)

## Interface: RejectedOrderInfo

Info for any orders that were rejected, including the reason they were rejected.

#### Hierarchy

* **RejectedOrderInfo**

#### Properties

### kind

• **kind**: [_RejectedOrderKind_](reference.md#enumeration-rejectedorderkind)

_Defined in_ [_index.ts:516_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L516)

### orderHash

• **orderHash**: _string_

_Defined in_ [_index.ts:514_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L514)

### signedOrder

• **signedOrder**: _SignedOrder_

_Defined in_ [_index.ts:515_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L515)

### status

• **status**: [_RejectedOrderStatus_](reference.md#class-rejectedorderstatus)

_Defined in_ [_index.ts:517_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L517)

## Interface: RejectedOrderStatus

Provides more information about why an order was rejected.

#### Hierarchy

* **RejectedOrderStatus**

#### Properties

### code

• **code**: _string_

_Defined in_ [_index.ts:534_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L534)

### message

• **message**: _string_

_Defined in_ [_index.ts:535_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L535)

## Interface: ValidationResults

Indicates which orders where accepted, which were rejected, and why.

#### Hierarchy

* **ValidationResults**

#### Properties

### accepted

• **accepted**: [_AcceptedOrderInfo_](reference.md#class-acceptedorderinfo)_\[\]_

_Defined in_ [_index.ts:495_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L495)

### rejected

• **rejected**: [_RejectedOrderInfo_](reference.md#class-rejectedorderinfo)_\[\]_

_Defined in_ [_index.ts:496_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L496)

## Interface: WethDepositEvent

#### Hierarchy

* **WethDepositEvent**

#### Properties

### owner

• **owner**: _string_

_Defined in_ [_index.ts:356_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L356)

### value

• **value**: _BigNumber_

_Defined in_ [_index.ts:357_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L357)

## Interface: WethWithdrawalEvent

#### Hierarchy

* **WethWithdrawalEvent**

#### Properties

### owner

• **owner**: _string_

_Defined in_ [_index.ts:346_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L346)

### value

• **value**: _BigNumber_

_Defined in_ [_index.ts:347_](https://github.com/0xProject/0x-mesh/blob/8813eae2/browser/ts/index.ts#L347)


# inAppPurchase

> In-app purchases on Mac App Store.

Process: [Main](../glossary.md#main-process)

## Events

The `inAppPurchase` module emits the following events:

### Event: 'transactions-updated'

Emitted when one or more transactions have been updated.

Returns:

* `event` Event
* `transactions` Transaction[] - Array of [`Transaction`](structures/transaction) objects.

## Methods

The `inAppPurchase` module has the following methods:

### `inAppPurchase.purchaseProduct(productID, quantity, callback)`

* `productID` String - The id of the product to purchase. (the id of `com.example.app.product1` is `product1`).
* `quantity` Integer (optional) - The number of items the user wants to purchase.
* `callback` Function (optional) - The callback called when the payment is added to the PaymentQueue.
* `isProductValid` Boolean - Determine if the product is valid and added to the payment queue.

You should listen for the `transactions-updated` event as soon as possible and certainly before you call `purchaseProduct`.

### `inAppPurchase.canMakePayments()`

Returns `true` if the user can make a payment and `false` otherwise.

### `inAppPurchase.getReceiptURL()`

Returns `String`, the path to the receipt.

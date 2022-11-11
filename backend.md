# Backend



### Creating Orders

These are some tweaks needed on the current POST requests, `/listing` and `/offer`

* Replace `nonce` with `counter`
  * Include counter when storing the entire order (parameter + signature)

### Retrieving Orders

There are a few things needed in these GET requests, `/listing` and `/offer`

* Remove "0x" wherever "0x" was NOT used when creating the order
  * Basically anywhere it was originally a uint or string
* If there are no query params such as offerer, contract or tokenId, then retrieve all listings or offers (within pageNumber and limitPerPage)
* By default, sort orders by most recent timestamp for all requests
  * Include a sortBy param that allows oldest to newest and newest to oldest
* Include query params pageNumber and limitPerPage
  * This should be an extension or replacement of the current `limit` param
* Include sorting under the following filters:
  * By offerer
    * timestamp - newest to oldest / oldest to newest
    * pricing (consideration/offer) - highest to lowest / lowest to highest
  * By contract address
    * timestamp - newest to oldest / oldest to newest
    * pricing (consideration/offer) - highest to lowest / lowest to highest
  * By contract address && tokenIds
    * timestamp - newest to oldest / oldest to newest
    * pricing (consideration/offer) - highest to lowest / lowest to highest
  * By recipient (within consideration item)
    * timestamp - newest to oldest / oldest to newest
    * pricing (consideration/offer) - highest to lowest / lowest to highest
* By default, exclude cancelled, fulfilled and expired orders unless specifically request as a query param
  * e.i. `/listings?fulfilled=true&cancelled=true&expired=true&pending=false`
    * Boolean values in which include fulfilled, cancelled and expired orders and excludes current orders awaiting fulfillment (pending)

_**The OpenSea documentation includes similar query params for additional guidance:**_

* Retrieve listings - https://docs.opensea.io/v2.0/reference/retrieve-listings
* Retrieve offers - https://docs.opensea.io/v2.0/reference/retrieve-offers

### Fulfilling Orders

**\[not needed as implemented on the blockchain level]** This would be 2 new POST request (1 for listing and 1 for offer) that would take any existing order created and mark it as fulfilled. Likely log the tx, signature or return value from seaport.

### Cancel Orders

**\[not needed as implemented on the blockchain level]** This would be 2 new POST request (1 for listing and 1 for offer) that would take any existing order created and mark it as cancelled. Likely log the tx, signature or return value from seaport.

### Retrieve Collection Stats (???)

There are 2 possible statistics needed that requires aggregating all the orders and grouping by collection (contract address). These are:

* Trading volume within a particular time period
  * Query params are most likely:
    * startTime (required)
    * endTime (required)
    * contract address (optional - if empty, then get all collections sorted in descending order of value traded)
* Floor price
  * Query params are most likely:
    * startTime (required)
    * endTime (required)
    * contract addresses (optional - if empty, then get all collections sorted by highest to lowest floor prices)

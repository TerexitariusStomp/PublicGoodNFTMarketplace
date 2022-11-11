# Pages

Pages

* Landing
* Explore NFTs
* NFT Detail
* Collection Detail
* Wallet Detail
* Search



### Landing <a href="#landing" id="landing"></a>

_An entry point into the PGNFTMKT dapp, with a basic explanation of the market’s unique mechanics._

#### Navigation <a href="#navigation" id="navigation"></a>

* Home
* Explore NFTs
* Search
* Connect Wallet
  * Rewards NFT
  * Wallet Detail
  * My Collections
  * Disconnect

#### Explainer Element <a href="#explainer-element" id="explainer-element"></a>

A combination of copy and infographics which tells visitors, especially new visitors, what PGNFTMKT is.

#### Footer <a href="#footer" id="footer"></a>

* Social links (link to charged particles? Giveth?)
* Partial nav links (Home, explore)
* Blog, whitepaper, or terms of service links if applicable.
* Built on Seaport and Opensea

### Explore NFTs <a href="#explore-nfts" id="explore-nfts"></a>

_Users can browse through NFTs and collections on PGNFTMKT. This screen has two tabs, to explore collections, and to explore NFTs._

* NFT Tab - an infinitely-scrolling list of NFTs, sorted by most recent listing
  * NFT Name
  * Image
  * Collection Name
  * Collection Avatar
  * Last Price/Date Minted
* Collections Tab - an infinitely scrolling list of collections, sorted by 7-day trading volume.
  * Collection Name
  * Collection Avatar

### NFT Detail <a href="#nft-detail" id="nft-detail"></a>

_A detailed view of an individual NFT._

#### NFT Information <a href="#nft-information" id="nft-information"></a>

* NFT Name
* NFT Image
* NFT Properties
  * Property category
  * Property name
  * Property rarity
* Public Goods Recipient
  * If the public goods recipient is undefined or invalid, this displays to non-owners as Giveth. To owners, a badge is displayed which indicates the recipient address needs to be updated.
* NFT Contract Address
* NFT Token ID
* NFT Token Standard
* NFT Current Price/Most Recent Price
* Collection Name
* Collection Avatar
* Collection Description
* Deployer Address
* (If owner) List/De-list button
* For ERC1155 token standard NFTs, all current listings of the NFT will display, regardless of owner.
  * Cancel listing (if owner)
  * Buy (if not owner)
* Unsolicited offers made on this NFT
  * If any of these offers belong to the user, there is a button on those to cancel the offer.
  * If the user owns this NFT, there is a button to accept each offer.

#### Offer Interface <a href="#offer-interface" id="offer-interface"></a>

If the user is not the NFT’s owner, they may one of two types of offer on the NFT: solicited or unsolicited. A solicited offer is made on a listed NFT, at the seller’s asking price. Solicited offers are first come, first served, and do not need to be manually approved by the seller.\
Unsolicited offers are made on any NFT, listed, or unlisted, and the buyer determines the price. The NFT’s owner must review and accept an unsolicited offer for a transaction to be made.

* Asking price (When listed. Price is in ETH)
* Buy Now Button
* Make Offer button (for unsolicited offers)
  * Pressing this button brings up a small modal to allow the user to set the price of their offer.
  * There will be an external link to uniswap to get more WETH.
  * PGNFTMKT requires WETH for transactions. If the user has insufficient WETH they’ll be pointed to Uniswap or they can reduce their offer.

#### Activity History <a href="#activity-history" id="activity-history"></a>

_A history of all this NFT’s trades in table format_

* Event (Minted, Sent)
* Price
* From (address)
* To (address)
* Date

### Collection Detail <a href="#collection-detail" id="collection-detail"></a>

_A detailed view of a given collection of NFTs._

#### Collection Information <a href="#collection-information" id="collection-information"></a>

* Collection name
* Collection avatar/banner image
* Number of items
* Collection description
* Collection deployer address
* Floor price
* Public Goods Recipient
  * If the public goods recipient is undefined or invalid, this displays to non-owners as Giveth. To owners, a badge is displayed which indicates the recipient address needs to be updated.
* Edit form for the following if owner:
  * Modify royalty %
  * Modify royalty recipient
  * Modify charity/public goods recipient

#### NFT Gallery <a href="#nft-gallery" id="nft-gallery"></a>

_A grid gallery of all NFTs in the collection._

### Wallet Detail <a href="#wallet-detail" id="wallet-detail"></a>

_An inventory of the user’s currently connected wallet._

* Wallet address (not editable. If the user has an ENS address, that is displayed as well. Whenever only one can be displayed, default to the ENS address.)
* Promote to/demote from admin button (If admin)

#### Rewards NFT <a href="#rewards-nft" id="rewards-nft"></a>

_New wallets are given a Rewards NFT upon verifying their connection to the platform for the first time. This NFT receives platform and GIV tokens whenever the user makes an applicable purchase. The amount of tokens is set by the platform._

* NFT Preview
* Available tokens to claim
* Claim button
* Textual explanation of the Rewards NFT’s purpose and functions.

#### My Collections <a href="#my-collections" id="my-collections"></a>

_If this address is the deployer of any collections, links to those collections are visible here. Uses the Opensea API to fetch registered collections and associated data._

* Collection name (Functions as a link to the collection detail page when clicked on.)
* Collection avatar
* Number of items
* Public Goods funding recipient (owners can set or change this here)
* Set Royalties button
  * 1% platform fee
  * 1% public good funding
  * one additional royalty % and payout address, owner’s choice. (Autopopulated from opensea, but owners can overide royalty percentages and payout addresses)
* Import collection button (Enter your collection’s contract address here to check if the connected wallet address is an owner of the collection on Opensea)

#### NFT Gallery <a href="#nft-gallery1" id="nft-gallery1"></a>

_A grid of NFTs the user owns. Functionally identical to a Search Result screen pre-filtered with the user’s wallet address as owner. Filterable and sortable as a basic Search Result screen._

#### Offers Made <a href="#offers-made" id="offers-made"></a>

\*A list of NFTs the connected user has made unsolicited offers on.

* Filter active offers vs all offers. By default, only active offers are displayed.
* Link to NFT
* Status (won, pending, expired)
* Offer date/time
* Offer amount
* Cancel button (If the offer is active)

#### Offers Received <a href="#offers-received" id="offers-received"></a>

\*A list of offers the connected user has received for NFTs they own. These are only unsolicited offers, which require their review.

* Filter pending offers vs all offers
* Link to NFT
* Offer date/time
* Offer amount
* Offering address
* Accept button (for pending offers)

### Import New Collection <a href="#import-new-collection" id="import-new-collection"></a>

_Users can set up a profile page and import collections of NFTs they have already deployed elsewhere. This option will be accessible from the My Collections Page_

* Explanation text on how to edit the collection data (name, pictures, description, royalty percentages) by registering it on opensea
* A form field for the contract address of the collection.
* Public funding recipient (drop-down plus search field if the projects list is long)

### Search <a href="#search" id="search"></a>

_Users will be able to search NFTs, Addresses, and Collections via a combined search field, available in the global navigation. Suggested search results will autofill dynamically as the user types. These will be sorted by relevance (similarity to the keywords inputted) and then sorted alphabetically._

#### Search Results <a href="#search-results" id="search-results"></a>

* Breadcrumbs will allow users to navigate back to initial search results

**Collections**

* Collection Name
* Collection Avatar
* 7-day trading volume OR Floor price
* A link to see more matching collections

**Users**

* Address or ENS Name
* A link to see more matching users

**NFTs**

* Name
* Collection Name
* Picture
* Price
* NFTs will scroll infinitely

### Admin <a href="#admin" id="admin"></a>

_There will be a single screen through which admins can allowlist Giveth project verified wallet addresses as potential recipients for platform fees._

* Most likely a form field to add new addresses.
  * Project name
  * Wallet address
  * Giveth url
* A display of the current allowlist.
  * A button on each active row to deactivate the project
  * A button on each inactive project to reactivate it\
    _This is to avoid projects being added and removed repeatedly from the list without a record as to what happened._

General Community

When community members come to the platform (central website) they are, first asked their language of choice then asked to connect their cryptocurrency wallet. If they do not have a cryptocurrency wallet, they are notified as to the disadvantages of interacting with the platform (no NFTs from funding, not able to receive fiat funding back). Once they accept the disadvantages of interacting with the platform without a cryptocurrency wallet or have connected their cryptocurrency wallet, they are directed to a landing page. Every page of the platform is kept super simple so to maximize accessibility.&#x20;

Artist Page

Each NFT artist will have their own page that anyone is able to view and make NFT purchases from. This page will show the floor price for the artist NFTs and how much on average their NFTs are going for. Along with this it will show links to the artists other social channels.&#x20;

Organizational Page

Each organization will have an organizational page that will have their current NFT's that involve their actions, even if the organization is not the holder of that NFT (no matter if the NFT is lazy minted or minted).This page will show the floor price for the NFTs and how much on average their NFTs are going for. Along with this it will show links to other social channels and entity information. All organizations are sourced from Giveth.

Secondary Market

Once the NFTs are bought and sent to the buyer (secondary holder), they are displayed in the secondary marketplace. This marketplace will be curated by the type of art, have sorting filters, and top art will be displayed automatically to the community member based upon the data we know about them.&#x20;

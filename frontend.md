# Frontend



### Tech Stack <a href="#tech-stack" id="tech-stack"></a>

* Framework
  * [NextJS](https://nextjs.org/)
* Styling
  * [Chakra UI](https://chakra-ui.com/)
* Web3 Interaction
  * [Wagmi](https://wagmi.sh/)
* Marketplace
  * [OpenSea API](https://docs.opensea.io/reference/api-overview)
  * [SeaportJS](https://github.com/ProjectOpenSea/seaport-js)
  * [Quay](https://github.com/Alcibiades-Capital/quay) (Backend)
* NFT
  * [Alchemy NFT API](https://www.alchemy.com/nft-api)
  * [Royalty Lookup API](https://royaltyregistry.xyz/lookup)
  * [Charged Particle SDK](https://docs.charged.fi/sdk/charged-particles-sdk-overview)

### Database Management <a href="#database-management" id="database-management"></a>

A database will be needed to store a few dedicated collections:

#### NFT Collection <a href="#nft-collection" id="nft-collection"></a>

* Contract Address
* Public Goods recipient
* Royalty Fee
* Royalty recipient address

#### Public Goods Charity <a href="#public-goods-charity" id="public-goods-charity"></a>

* Name
* Description
* URL
* Recipient address

### Main Functions <a href="#main-functions" id="main-functions"></a>

#### Charged Particle <a href="#charged-particle" id="charged-particle"></a>

* Create rewards NFT as Charged Particle
* View charge value (check token balance inside NFT)
* Check if NFT is a Charged Particle
* Claim rewards from NFT

#### Quay + Seaport <a href="#quay-seaport" id="quay-seaport"></a>

* Authenticate w/ SIWE
* Verify session
* Create Order
  * Create Offer
    * Include mktplace fee, donation fee and royalty fee
    * Check donation project for pause/unpause
      * If paused, reroute donation fee to another recipient
    * Include conduit address
    * Log order creation to Quay
  * Create Listing
    * Include mktplace fee, donation fee and royalty fee
    * Check donation project for pause/unpause
      * If paused, reroute donation fee to another recipient
    * Include conduit address
    * Log order creation to Quay
* Retrieve Orders
  * Retrieve Offers
    * Check if includes proper fee
    * Sorted by most recent
    * By Offerer
    * By contract address and tokenIds
    * By contract address
    * Exclude cancelled/fulfilled
  * Retrieve Listings
    * Check if includes proper fee
    * Sorted by most recent
    * By Offerer
    * By contract address and tokenIds
    * By contract address
    * Exclude cancelled/fulfilled
* Collection Metrics
  * Retrieve Trading Volume(s)
  * Retrieve Floor Price(s)
* Fulfill Order (Seaport only)
  * Fulfill Offer
  * Fulfill Listing
* Cancel Order (Seaport only)
  * Log order cancellation to Quay

### Components <a href="#components" id="components"></a>

* Navigation
* Footer
* Modals
* Toasts
* NFT Gallery

#### Navigation <a href="#navigation" id="navigation"></a>

* Links
  * Home
  * Explore NFTs
* Search bar
  * Autofill dropdown list
  * Fetch past search terms
  * Fetch collections, users and tokens with matched keywords
    * Fetch and sort by trading volume (?)
* Connect Wallet button (if NOT connected)
* Connected Wallet icon button (if connected)
  * Rewards NFT link
  * Wallet Detail link
  * My Collections link
  * Disconnect

#### Footer <a href="#footer" id="footer"></a>

* Social links
* Partial nav links (Home, explore)
* Blog, whitepaper, or terms of service links if applicable.

#### Modal <a href="#modal" id="modal"></a>

* Make Listing
  * Include form to set ask price
* Make Offer
  * Include form to set the offer price
* Register New Collection
  * Include the following form fields:
    * Collection Name
    * Collection Avatar
    * Contract Address
    * Royalty percentage
    * Royalty recipient
    * Public Goods funding recipient

#### NFT Gallery <a href="#nft-gallery" id="nft-gallery"></a>

* Fetch and render NFTs by either of the following:
  * Wallet address (aka owner)
  * Collection (aka contract address)
* Fetch listings of NFTs
* Sortable by price, date listed (?)
* Filter by listed and unlisted
* Pagination

### Pages <a href="#pages" id="pages"></a>

#### Overview <a href="#overview" id="overview"></a>

* Landing
* Explore NFTs
* NFT Detail
* Collection Detail
* Wallet Detail
* Search

#### Landing <a href="#landing" id="landing"></a>

* Navigation
* Footer
* Explainer Element
  * A combination of copy and infographics which tells visitors, especially new visitors, what PGNFTMKT is.

#### Explore NFTs <a href="#explore-nfts" id="explore-nfts"></a>

_Users can browse through NFTs on PGNFTMKT._

* NFT Component
  * NFT Name
  * Image
  * Collection Name
  * Last Price
* Infinitely scrolling single-column showcase of NFTs
  * Query most recent listings
    * Pagination and page limits
* Infinite scrolling column of trending/top collections
  * Query collections by either trading volume or floor price
    * Pagination and page limits

#### NFT Detail <a href="#nft-detail" id="nft-detail"></a>

_A detailed view of an individual NFT._

* Fetch and render metadata
* Fetch and render metadata trait/property rarities
* Fetch and render collection info
  * Name
  * Description
  * Owner/Deployer/Creator
* Fetch listings
  * Render list (if ERC-1155)
  * Cancel listing button + function (if owner)
* Fetch offers
  * Render list
  * Render cancel button (if offerer)
    * cancel offer
  * Render accept button (if owner of NFT)
    * fulfill order
* Buy Widget
  * Render ask price (if listed)
    * Render last sold price otherwise
  * “Buy Now” Button (if listed)
    * Fulfill listing
  * “Make Offer” button
    * Displays [Make Offer](https://hackmd.io/@georgeh/rkrMDKhVi#Modal) modal
* Activity History Component
  * Event (Minted, Sent)
  * Price
  * From (address)
  * To (address)
  * Date

#### Collection Detail <a href="#collection-detail" id="collection-detail"></a>

_A detailed view of a given collection of NFTs._

* Fetch and render Collection info (from Opensea API)
  * Collection name
  * Collection avatar/banner image
  * Number of items
  * Collection description
  * Deployer/owner/creator address
  * Floor price (from Quay)
* [NFT Gallery](https://hackmd.io/@georgeh/rkrMDKhVi#NFT-Gallery)
* Edit form for the following:
  * Modify royalty %
  * Modify royalty recipient
  * Modify charity/public goods recipient

#### Wallet Detail <a href="#wallet-detail" id="wallet-detail"></a>

* Display ENS or wallet address of user
* Rewards NFT
  * Render NFT preview
  * View available tokens to claim
  * Claim button
  * [Charged Particle functions](https://hackmd.io/@georgeh/rkrMDKhVi#Charged-Particle)
* My Collections
  * Fetch collection/contract metadata
    * Collection name (Functions as a link to the collection detail page when clicked on.)
    * Collection avatar
    * Number of items
  * Register new collection button
    * Displays [Register New Collection](https://hackmd.io/@georgeh/rkrMDKhVi#Modal) modal
* NFT Gallery
* Offers Made
  * Retrieve offers by offerer
  * Render list with the following:
    * Filter active offers vs all offers. By default, only active offers are displayed.
    * Link to NFT
    * Status (won, pending, expired)
    * Offer date/time
    * Offer amount
    * Cancel button (If the offer is active)
      * Cancel order
* Offers Received
  * Retrieve offers by recipient
  * Render list with the following:
    * Filter active offers vs all offers
    * Link to NFT
    * Offer date/time
    * Offer amount
    * Offering address

#### Import New Collection <a href="#import-new-collection" id="import-new-collection"></a>

* Form fields:
  * A form field for charity recipient
    * Dropdown menu with search autofill
    * Filter out paused projects
  * A form field for royalty recipient
  * A form field for royalty %
  * Autofill info from Opensea API
* Functions
  * Save new collection to database
  * Check if user is owner or deployer of contract before submission

#### Search <a href="#search" id="search"></a>

* Render keyword
* Render breadcrumb links for result navigation
* Collections results section
  * A link to see more matching collections
  * Render matched collections each with the following:
    * Collection Name
    * Collection Avatar
    * 7-day trading volume (from Quay)
  * Fetch collections that include search keyword(s) in at least one of the following:
    * Name
    * Address
    * Owner/Deployer address
* Users results section
  * A link to see more matching users
  * Render matched users each with the following:
    * Address or ENS Name
    * PFP
  * Fetch users that include search keyword in at least one of the following:
    * ENS
    * Wallet address
* NFTs results section
  * [NFT Gallery](https://hackmd.io/@georgeh/rkrMDKhVi#NFT-Gallery)
    * Renders all that match search query
    * Pagination and infinite scrolling
  * Retrieve listings of matched NFTs

#### Admin <a href="#admin" id="admin"></a>

* Render list of donation projects
  * Queried from database
* Add and edit donation projects
  * Name
  * Description
  * URL
  * Ethereum Address
* Toggle pause/unpause for projects
  * Paused projects do not receive commission from trades

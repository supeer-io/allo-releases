# Change Log

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added

### Changed

### Optimized

### Deprecated

### Removed

### Fixed

### Security



## v1.2.0

This version implements the new navigatin that includes the links to Allo Account and Allo Alerts. 

### Added

- Allo Ecosystem: Users can switch to the different Allo apps (Accounts, Alerts) from the nav
- Search: Added autofocus on the main search bar

### Changed

- Bookmarks: The bookmark page has been moved out of the _Profile_ and has its own page now.

### Optimized

- Cache: Optimized saving the preload entries in browser's IndexedDB

### Fixes

- Cache: Fixed brrowser cache busting for popular assets
- Theme: Fixed theme colors for asset charts
- Transaction Groups: Fixed the _per page_ limits for transaction groups (and all other static txn rows)








## v1.1.4

### Fixes

- Date and Number formats: fixed default locale being undefined on the server side
- Timestamps: Fixed datetime to timestamp conversion when they already include 'Z' (UTC marker)
- Blocks: prevent 404 errors when an error occur while fetching extra block data from GraphQL API
- Transaction Filters: Fixed an issue where address filters were overwriting the actual address the user is viewing the transactions for
- Accounts: Fixed account thumbnails not loading on mount
- Accounts: Fixed account types not updating after fetching data
- URLs: Fixed an issue where removing multiple slashes (`/account//<AccountId>/txns`) was sometimes removing double slashes from protocol.
- Nav Links: Fixed active state for strict Navlinks with trailing slashes




## v1.1.3

### Added

- Accounts: Added tooltip for the _Funded by_ info

### Fixed

- Fixed block timestamps




## v1.1.2

### Fixed

- Date formats: better formating for uncommon languages
- Accounts: fixed re-rendering of the Rekeyed To component after getting the API response 


## v1.1.1

### Added

- Preload: individually set cache durations for each preloaded content type

### Fixed

- API: fixed `searchAssetMeta` route
- Number formats: remove rounding for most amounts
- Defi portfolio: fixed component update when receiving the response from the API.
- Styling: fixed dividers when they are rendered on multiple lines 


## v1.1.0

### Added

- New `TxnGroup` entity
- New route for transaction groups (`allo.info/txn/group/<Group ID>`)
- Search for GroupId in the main search bar
- External links: added _Raw indexer data_ links
- Dates and Amounts formats using the browser's locale 

### Changed

- Group transactions rendered using the standard transaction tables components
- _Group Summary_ transfers are now collapsible (collapsed by default)
- Bookmarks sorted in alphabetical order


### Removed

- Removed "Sign Out" button from the profile until profiles implement AlloAccounts
- Removed transaction type `Unknown` from the filters


### Fixed

- Fixed a typo in `Key Registration` transaction type
- Trigger NFD search only on alphanumerical strings


## v1.0.0

This is the first public release of [Allo.info](https://allo.info).

### Key Features

- Search for: 
  - Assets
  - Accounts
  - Apps
  - Blocks
  - Txns 
  - NFDs ([@NFDomains](https://twitter.com/NFDomains))
  - Projects ([@awesome_algo](https://twitter.com/awesome_algo))
  - and our own Articles
- Accounts: 
  - NFD Profile
  - Defi value ([@TeamAlgogator](https://twitter.com/TeamAlgogator))
  - NFTs value ([@asalytic](https://twitter.com/asalytic))
- Assets
  - Pera Verification labels ([@PeraAlgoWallet](https://twitter.com/PeraAlgoWallet))
  - NFT Rarity ([@asalytic](https://twitter.com/asalytic))
  - Token price ([@vestigefi](https://twitter.com/vestigefi))
- Applications: 
  - TEAL inspector
- Transactions:
  - Group summary
  - Transactions filters
- Bookmarks!!!

### Migration Guidelines
```diff
- https://algoexplorer.io/tx/<txId>
+ https://allo.info/tx/<txId>

- https://algoexplorer.io/asset/<assetId>
+ https://allo.info/asset/<assetId>

- https://algoexplorer.io/address/<address>
+ https://allo.info/account/<address>

- https://algoexplorer.io/application/<appId>
+ https://allo.info/application/<appId>

- https://algoexplorer.io/block/<round>
+ https://allo.info/block/<round>
```   

##
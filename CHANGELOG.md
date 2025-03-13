# Change Log

All notable changes to this project will be documented in this file.

## v1.6.4

### Changed

- Modified OverviewLayout.svelte
- Updated history-related files
- Refactored Filterable.ts
- Updated BaseEntity.ts with minor adjustments

## v1.6.3

### Added

- Added scamWarning functionality back

### Changed

- Updated layout configuration for account pages

## v1.6.2

### Added

- Added warnings for accounts
- Added labels for scams
- Added marketplace listings
- Added organizations
- Added ThisDID links on Transactions
- Added tracking API endpoint

### Changed

- Changed ThisDID URL scheme
- Updated LoadMore component
- Bound fake input trigger to mouseup/touchend events
- Modified label localization

### Fixed

- Fixed token holders display
- Updated SupplyDistribution component

### Optimized

- Temporarily disabled scam tracker

## v1.6.1

### Added

- Added XComp vaults support

### Changed

- Improved asset address display
- Enhanced token holders distribution visualizations
- Modified token holders overview component

## v1.6.0

### Added

- Secondary addresses in the related addresses card
- Vestige burn vaults support
- Secondary reserves in the supply distribution chart
- App <--> account links in the Metadata card
- Labels strings for various entities
- Metadata component for all main entities
- Loading state on the supply chart
- Vestige labels strings

### Changed

- Migrated from SASS to newer version
- Switched tags to labels, now fetching metadata from Allo Commons
- Moved NFD card inside metadata component
- Moved asset info into the Metadata component
- Changed DID resolver URLs
- Synced supply and holders color palettes
- Improved holders component with legend
- Enhanced metadata block responsiveness
- Updated entity handling for improved placeholder selection

### Fixed

- Fixed decimals component
- Fixed distribution render update
- Fixed vault labels
- Fixed metadata component responsiveness
- Fixed wall shadows
- Fixed styles for scam check component

### Removed

- Removed deepStore
- Removed unused holder labels conditions
- Removed redundant Profile.svelte component

### Optimized

- Restructured token-related components
- Improved organization of entity classes with init method standardization
- Refined GraphQL queries for asset data

### Dependencies

- Updated @supeer/orm from ^0.3.4 to ^0.4.0
- Updated @supeer/ui from ^1.6.12 to ^1.7.1
- Updated @sveltejs/kit from ^2.5.18 to ^2.7.3
- Updated svelte-preprocess from ^5.1.0 to ^6.0.3
- Added @sveltejs/vite-plugin-svelte at ^3.1.2

## v1.5.2

### Added

- ACCOUNTS, APPS, ASSETS | Added charts for transaction counts and volume

### Changed

- ACCOUNT | Updated top interactions with in/out + progress
- UI | New layouts for account/token/nft/app pages
- CACHE | Implemented autoclean cache on the client side on reload

### Fixed

- ACCOUNTS, APPS, ASSETS | Fixed transaction sums calculations
- UI | Fixed search history overflowing the grid

### Removed

- API | Removed unused analytics route
- HOMEPAGE | Removed unused stats stores

### Optimized

- ACCOUNTS, APPS, ASSETS | Separated calls for chart and total transactions

## v1.5.1

### Added

- ACCOUNTS, APPS, ASSETS | Added txn counters

### Changed

- ACCOUNT | Switched the top interactions to use the new Analytics API endpoints
- DEPENDENCIES | Updated ORM version

### Fixed

- UI | Fixed animated counters where small numbers might not reach final value in some cases

## v1.5.0

### Added

- SEARCH | New search modal
- TABLES | Controls component for filters
- CHARTS | Zoom reset button on charts
- ASSET | NFT descriptions

### Changed

- SEARCH | Updated scoring methods
- SEARCH | Added Pera projects metadata scores
- DEPENDENCIES | Updated Svelte & TypeScript packages

### Fixed

- SEARCH | Fixed fetching opengraph project images
- CHARTS | Fixed scroll trap in mobile charts
- DATASETS |Fixed Datasets for server-side timestamps loading
- APPS | Fixed style issues in app programs
- ASSET | Fixed deleted assets page when asset was created by an app
- ACCOUNT | Fixed NFD twitter links
- UI | Fixed style issues with tooltip encoding options

## v1.4.6-alpha.0

### Added

- DATASETS | Added Metadata dataset
- SEARCH | Added frequent/recent searches
- SEARCH | Added History module
- SEARCH | Added clear and search all buttons
- TXN |Added AssetFreezeTxn component in Tx page

## v1.4.5

### Fixed

- TXN | Transaction 404 quick fix

## v1.4.4

### Fixed

- SERVER | Try/catch in server hooks

## v1.4.3

### Changed

- UI | Fine-tuned popup overlay

### Fixed

- TABLES | Fixed TableRow type
- NAV | Fixed active state in NavLink
- BUILD | Fixed circular dependency
- HELPERS |Fixed search paths helpers

## v1.4.2

### Added

- UI | Popups and tooltips are now using portals

### Changed

- UI | Updated footer version display

### Fixed

- SERVER | Fixed GraphQL server caching
- SERVER | Fixed feedback API route

## v1.4.1

### Added

- EXTERNAL LINKS | Added Minthol logo (still waiting for their fallback route when no collection for final implementation)
- PAGES | Added privacy policy and terms of use pages

### Changed

- CACHE | Lowered cache pruning interval

### Fixed

- CACHE | Fixed cache pruning
- UI | Fixed some text-link styles
- UI | Fixed external links decoration

## v1.4.0

### Added

- EXTERNAL LINKS | Added Goplausible DID resolver links

### Changed

- UI | Homepage styles
- UI | Updated FontAwesome

### Fixed

- ASSET | Fixed assets supply tooltip slugs
- CHARTS | Fixed NumberCounter text wrapping
- UI | Fixed menu height issues on mobile

## v1.3.1

### Added

- TXNS | Implemented scam detection API from ChainTrail.io and added warning messages
- SEARCH | Go directly to a result page if a single result has been found at the moment of hiting submit
- CACHE | Added self-pruning on the browser cache. Expired entries are now deleted automatically on page refresh, at an 1h interval.

### Fixed

- SEARCH | Fixed filters and addons params being appended to API query strings
- ACCOUNTS | Fixed "funded by" value not getting refreshed sometimes when changing accounts
- ASSETS | Open urls links starting with `ipfs://` on our IPFS gateway.
- HOMEPAGE | Fixed the sections height on very large and portrait screens

## v1.3.0

This is a production release.
Below are all changes between v1.2.0 -> v1.3.0

### Added

- Homepage: Added a stats section about the current state of Algorand mainnet
- External Links: Added links to Pera Explorer on transactions, groups, applications and blocks
- Inner Transactions: Added indentation in transaction tables to help visualize inner transactions depth.
- Transactions: Added a tab in the transaction view to see all inner transactions for a single outer txn. Same view available for inner transactions too.
- Asset Overview: Added a holders distribution card in the token overview
- Asset Holders: Added a page with the holders distribution bar chart, along with holders list (with filters and sortings)
- Txn Notes: Added a toggle to switch the note encoding
- Txn Logs: Added toggles to switch transaction logs encoding
- Search: Added search from the labeled assets list

### Changed

- Accounts: Switched Algogator to the new Compx API endpoints
- Profile: Moved profile settings (portfolio providers) from LocalStorage to IndexedDb in preparation of the full profiles
- Grid Layouts: Revamped grid layouts in preparation of customizable layouts
- Account Rekey Transactions: Switched the query from the standrard indexer to our GraphQL API that has better indexing.
- Search Scores: More weight for `Trusted` and `Verified` labels
- Search Scores: Drop the score for `Suspicious` labels

### Fixed

- Accounts: fixed the AppId not always being displayed because of async component rendering
- Txns Filters: Fix txn filters not being applied in /tx/group route
- Styling: fixed alignment in data tables
- Formatting: fixed amount formating not using locales in some places
- Tooltips: Refactored tooltips to have them all displayed on a completely seperate layer. That fixes all the z-index and context scope issues.
- Accounts: fixed the AppId not always being displayed because of async component rendering
- Txns Filters: Fix txn filters not being applied in /tx/group route
- Styling: fixed alignment in data tables
- Formatting: fixed amount formating not using locales in some places
- Search: Fixed suggestions dropdown not being displayed on autofocus
- Search: Fixed searching from the Popular Assets list
- Search: Fixed the search scopes (tokens, nfts) for cached data

## v1.2.3-beta

This is a pre-release. You can test it on the preview environment.

### Added

- Homepage: Added a stats section about the current state of Algorand mainnet
- External Links: Added links to Pera Explorer on transactions, groups, applications and blocks
- Inner Transactions: Added indentation in transaction tables to help visualize inner transactions depth.
- Transactions: Added a tab in the transaction view to see all inner transactions for a single outer txn. Same view available for inner transactions too.

### Changed

- Accounts: Switched Algogator to the new Compx API endpoints
- Profile: Moved profile settings (portfolio providers) from LocalStorage to IndexedDb in preparation of the full profiles

### Optimized

- Account Rekey Transactions: Switched the query from the standrard indexer to our GraphQL API that has better indexing. (no more timeouts!)

### Fixed

- Accounts: fixed the AppId not always being displayed because of async component rendering
- Txns Filters: Fix txn filters not being applied in /tx/group route
- Styling: fixed alignment in data tables
- Formatting: fixed amount formating not using locales in some places
- Tooltips: Refactored tooltips to have them all displayed on a completely seperate layer. That fixes all the z-index and context scope issues.

## v1.2.2-beta

This is a pre-release. You can test it on the preview environment.

### Added

- Asset Overview: Added a holders distribution card in the token overview
- Asset Holders: Added a page with the holders distribution bar chart, along with holders list (with filters and sortings)

### Changed

- Grid Layouts: Revamped grid layouts in preparation of customizable layouts

### Fixed

- Accounts: fixed the AppId not always being displayed because of async component rendering
- Txns Filters: Fix txn filters not being applied in /tx/group route
- Styling: fixed alignment in data tables
- Formatting: fixed amount formating not using locales in some places

## v1.2.1-beta

This is a pre-release. You can test it on the preview environment.

### Added

- Txn Notes: Added a toggle to switch the note encoding
- Txn Logs: Added toggles to switch transaction logs encoding
- Search: Added search from the labeled assets list

### Changed

- Search Scores: More weight for `Trusted` and `Verified` labels
- Search Scores: Drop the score for `Suspicious` labels

### Fixed

- Search: Fixed suggestions dropdown not being displayed on autofocus
- Search: Fixed searching from the Popular Assets list
- Search: Fixed the search scopes (tokens, nfts) for cached data

## v1.2.0

This version implements the new navigation that includes the links to Allo Account and Allo Alerts.

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

# In.Goibibo

This is a Go-MMT's B2B portal for hoteliers to list and sell their property on Goibibo & MakeMyTrip. There have been multiple things that I have worked upon in my tenure here. Here I will list down all the technical changes that we have done!

> * Below items are mentioned in Chronological order & dates mentioned are go live dates
> * Product stories are intentionally not mentioned in Detail

## Technical changes

* Initial migration out of Django - 14th Nov 2018 - https://tech.goibibo.com/django-unchained-literally-fa90697dc37e
  - New Development Setup - [Create React App](https://create-react-app.dev/)
    - Webpack setup for Bundling
    - ESLint for linting
    - Jest for writing testcases
    - SCSS/Module SCSS support out of the box
    - Typescript support
    - Optimizing assets
    - Code splitting support
    - Automatic configurations for all of the above and easy updates in the future (just by updating `react-scripts` version)
    - Setup Prettier to auto format code on commit
    - Added Jira check in commit messages using husky
    - Output filepaths for Akamai purging
  - Wrote custom bash scripts to do the bundling + versioning for the legacy code
  - Also figured out a way to have legacy underscore templates (multiple HTMLs) get bundled in the new SPA setup
  - Setup a new dockerized service in AWS for standalone deployment and also setup a proxy from Inventory repo
  - Achieved ~200KB reduction in gzipped size just because of better dev setup.
* Lint warning fixes & deps upgrade - 14th Feb 2019
  - Upgraded all packages in the repo (and made all breaking changes needed to be done)
  - Fixed all lint warnings throughout the codebase
  - **Fail production build on Lint warning**
* Code cleanup - 25th Feb 2019 - https://goibibo.atlassian.net/wiki/spaces/WIKI/pages/1704913/Code+Cleanup+-+22+02+2019
  - Almost 17k LOC unused code deleted
  - One entire CSS lib variant removed
  - Reduced ~65k in gzipped size
  - Load time down from ~5.5s to ~4s in office network speed
* Webengage service worker setup - 26th Feb
* React router introduction - 25th Apr 2019 - https://github.com/goibibo/ingoibibo_extranet/wiki/React-Router-Release
  - Moved all legacy HTML present by default for all tabs into script templates
  - Create a lean webapp shell with Header, Navigation & Content area
  - Migrate all Tabs which were already in react to React router routes
  - Create a thin React shell component for all legacy routes which does
    - Restore the legacy HTML for that tab into the "Content Area"
    - Run the legacy init function for that tab
    - Setup a subtab click handler and all other handlers
    - And a cleanup to clear the HTML
  - Added a Global Loader in React
  - Top level Error Boundary - To capture failures in React code
  - Top level state (via Context API) and migrated all top level info to this
  - Deep linking for Property & Analytics tabs
  - **10k LOC more cleanup**
  - We have achieved ~35KB reduction in gzip sizes of legacy codes due to cleanup.
  - Our script parsing time has halved (From 3221ms to 1530ms)
  - **Overall load time has halved (From 4.08s to 1.95s)**
  - Our rendering time (time it creates elements on UI) has reduced from 617ms to 99ms a mammoth ~80% reduction. Similar is the case with CSS application time (Painting)
* Added custom proxy with which devs can choose their backend setup via `.env.development.local` - 10th May 2019
* Circle CI integration to run build on all PRs - 7th June 2019
* Photos optimization - lazyload with intersection observer API - 27th June 2019
* Code performance optimizations - 9th Aug 2019 - https://github.com/goibibo/ingoibibo_extranet/pull/227
  - 6k LOC code deleted
  - Made initial data call async.
  - Removed unused legacy vendor libs
  - Removed unused font files and duplicate font files
  - Made top level `getAllGeneralDetails` (which fetches static data for property screen) API call independant
  - Deferred top level async calls until after the hotel change API calls are done!
  - Prevent multiple top level re renders!!
  - Removed jquery-ui-custom css and all related assets
  - **Implemented code splitting for React code with React.lazy & React.Suspense**
  - Deferred loading of a certain legacy vendor libraries until the tab it is used is opened!
  - **The loading time of Extranet in office network now under ~1s**
* S3 setup for Extranet **Zero Downtime deployment** - 28th Aug 2019
* Docker size optimization by switching base to node alpine - 29th Aug 2019
* Setup Jest + Puppeteer with running the puppeteer tests inside Docker - 16th Sep 2019
* Setup Jest integration tests report publishing - 5th Dec 2019
* Browser version restriction - 31st Jan 2020
* Module bundle analyze - 31st Jan 2020
* Multilingual dev setup + Production deployment setup with checks in place - 7th Feb 2020

### Proposed tech enhancements

* Migrate legacy tabs - Property, PLB/Margin offers, Bookings, Ratings & Review, Reports, Invoicing (with Clear Tax)
* Update/rewrite React code to the latest standards (Hooks, APIClient, Utils etc) - Rates & Inventory, Promotions
* Create a core set of reusable components
  - This also means that we throw away all CSS libraries/legacy CSS
  - Preferable use a library which gives a lot of functionality and interactions built-in like Material UI
  - Update the rest of the code slowly to use the core set of components
* Common utils - Validation framework, EventBus, API Client, Logging, GTM
* Custom hooks
* Setup i8ln & l8ln at the top level
* Setup a top level structure to hold info about Tab access & functionality access
* Perf - Image Sprites, Code Splitting, Lazy loading, Prefetching, Replace libraries which are huge by smaller equivalent
* PWA - Offline caching & Push notifications.
* Figure out a way in which we can share contracts and it can automatically generate types for writing FE code.
* Automated release notification mails
* Setup performance metric collection system and historical data collection for alerting & reporting
* Modules/No modules build output
* Typescript

## Product Stories

* House Rules (inside Property -> Policies section) - 13th Dec 2018
  - DB Template driven UI powered by Formik
  - Legacy placeholder and an event dispatched from legacy for react to render onto the placeholder
* Direct connect bookings - 22nd Jan 2019
* Amenities Rewrite - 8th Feb 2019
  - DB Template driven UI powered by Formik
  - Entire tab html + legacy JS code replaced by a placeholder element
  - Event dispatch from legacy for react to render in the placeholder element
* Onboarding flow - 25th Apr 2019
  - New flow for onboarding hotels
  - 8 screens collecting different information for taking a hotel live
  - Worked with one other developer on this
* Maintain Hotel selection & Route selection on refresh - 30th Apr 2019
* MO API Phase 2 changes; Payment info for DCB hotels - 9th July 2019
* Hotel level settings (Bulk uploaders for Inventory) - 15th July 2019
* FCL in Onboarding - 5th Aug 2019
* Inventory Optimization tabs (Sold out & Filling Fast) - 28th Aug 2019
* GST Tax slab changes - 1st Oct 2019
* Whatsapp Optin - 14th Oct 2019
* Guest chat enhancements - Multiple release dates
* Quality Score - 27th Jan 2020

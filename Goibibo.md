# In.Goibibo

> This is a Go-MMT's B2B portal for hoteliers to list and sell their property on Goibibo & MakeMyTrip. There have been multiple things that I have worked upon in my tenure here. Here I will list down all the technical changes that we have done!

## Technical changes (in chronological order)

* Initial migration out of Django - https://tech.goibibo.com/django-unchained-literally-fa90697dc37e
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
* Lint warning fixes & deps upgrade
  - Upgraded all packages in the repo (and made all breaking changes needed to be done)
  - Fixed all lint warnings throughout the codebase
  - **Fail production build on Lint warning**

## Product Stories (in Chronological order)

* House Rules (inside Property -> Policies section) 
  - DB Template driven UI powered by Formik
  - Legacy placeholder and an event dispatched from legacy for react to render onto the placeholder
* Direct connect bookings
* Amenities Rewrite
  - DB Template driven UI powered by Formik
  - Entire tab html + legacy JS code replaced by a placeholder element
  - Event dispatch from legacy for react to render in the placeholder element

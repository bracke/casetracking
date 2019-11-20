# Architecture 
The system is a Website implemented as a single-page JavaScript app. The app communicates with an API to POST and GET data using the REST protocol.

## Single-page app
THe singe-page app is implemented using the EmberJS JavaScript framework.

## Testing
Testing is done using the tools build into Ember CLI, including QUnit.
Ember-cli-mirage is used for faking the data API during test.
Ember-cli-fastboot-testing is used to test the fastboot rendered HTML (created using prember and ember-cli-fastboot).
Accessibility testing is done using ember-a11y-testing.

## Code documentation
All components are documented in ember-freestyle.

## User documentation
All user facing documentation is created as Jekyll generated static pages. The source material is written in markdown format.

## In-app text
There are no text strings inside the code, they are all read from external files to facilitate translation. 
Fetching the relevant text is done using ember-intl and @ember-intl/decorators. Deciding which language to use is done by ember-best-language.


## Data API and Hosting
THe app uses the Firebase data API and the app itself is hosted as static assets on Firebase.
THe integraton with Firebase is implemented using the ember-fire addon.

## Authentication
Authentication is implemented using ember-fire combined with ember-simple-auth.
All pages that require authentication are subroutes of the route 'authenticated'.

## Styling
All style for components are done using CSS modules using the ember-css-modules addon.

## Deployment
Deployment to Firebase is done using ember-cli-deploy with ember-cli-deploy-firebase.

## Speed and Size Optimizations

- Static pages like help and about/impressum are external pages and not part of the app.
- jQuery is not included.
- All data is loaded async with progress animations and dummy data.
- Data lists use paging and fetch only the current page.
- The report section is a separate engine which gets loaded on demand. 
- Superuser and admin pages are in a separate engine which only gets loaded on demand.
- In ember-bootstrap, whitelisting of components is used to reduce bootstrap size.
- Version 4 of ember-font-awesome is used which only includes the used elements.
- Fastboot is used to make startup (login page) quick.
- Only SVG images are used.
- No fonts are loaded.
- No tracking is done and no tracking libraries are used.

## Structure of list view
All list views contain the following compoents:

- Paging component (reused)(addon pagination-pager).
- Data loader component (reused).
- Sorting component (reused).
- Search component (reused).
- ListItem component (specific for item type).
- CSV export component.

## Structure for create item dialogs
All create item dialogs are implemented using bootstrap forms and ember-validated-form.



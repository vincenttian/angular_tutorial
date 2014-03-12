# Angular Tutorial

## Overview
This is the tutorial of the angular javascript library, and I will document my progress in this repo.

start node server: node scripts/web-server.js 

tutorial source: http://docs.angularjs.org/tutorial

## Prerequisites

### step-0

- Initial [angular-seed] project layout


### step-1

- We have converted the seed application by removing all of the boiler-plate code.
- We have added single static HTML file which shows a static list of phones. (we will convert this
  static page into dynamic one with the help of angular)


### step-2

- Converted static page into dynamic one by:
  - create a root controller for the application
  - extracting the data from HTML into a the controller as a mock dataset
  - convert the static document into a template with the use of `ng:` [directive] (iterate over
    mock data using [ng:repeat] and render it into a view)
- Added unit test, which mostly shows how one goes about writing a unit test, rather then test
  something of value on our mock dataset.


### step-3

- added a search box to demonstrate how:
  - the data-binding works on input fields
  - to use [$filter] function
  - [ng:repeat] automatically shrinks and grows the number of phones in the view
- added an end-to-end test to:
  - show how end-to-end tests are written and used
  - to prove that the search box and the repeater are correctly wired together


### step-4

- replaced the mock data with data loaded from the server (in our case the JSON return is just a
  static file)
  - The JSON is loaded using the [$xhr] service
- Demonstrate the use of [services][service] and [dependency injection][DI]
  - The [$xhr] is injected into the controller through [dependency injection][DI]


### step-5

- adding phone image and links to phone pages
- css to style the page just a notch


### step-6

- making the order predicate for catalog dynamic
  - adding 'predicates' section to the view with links that control the order
  - ordering defaults to 'age' property
- css sugar


### step-7

- Introduce the [$route] service which allows binding URLs for deep-linking with views
  - Replace content of root controller PhonesCtrl with [$route] configuration
  - Map `/phones' to PhoneListCtrl and partails/phones-list.html
  - Map `/phones/phone-id' to PhoneDetailCtrl and partails/phones-detail.html
  - Copy deep linking parameters to root controller `params` property for access in sub controllers
  - Replace content of index.html with [ng:view]
- Create PhoneListCtrl view
  - Move code which fetches phones data into PhoneListCtrl
  - Move existing HTML from index.html to partials/phone-list.html
- Create PhoneDetailsCtrl view
  - Wire [$route] service to map `/phanes/phone-id` to map to this controller.
  - Empty PhoneDetailsCtrl
  - Place holder partials/phane-details.html

### step-8

- Fetch data for and render phone detail view
  - [$xhr] to fetch details for a specific phone
  - template for the phone detailed view
- CSS to make it look pretty
- Detail data for phones in JSON format

### step-9

- replace [$xhr] with [$resource]
  - demonstrate how a resource can be created using a [service]

# cs32 --> Term Project
## Contributors
Developed by Zeeshan Bhalwani (zbhalwan) & Kyle Sohn (ksohn3) & Safae Merigh (smerigh) & Omer Chaudhry (mchaud11)

Total time this week: 10 hours 

Github Repo: https://github.com/cs0320-s2023/commerce-project.git


## Project Description

## Contributions

Kyle:
Filtering styling with bootstrap
Styled products as Cards with bootstrap
Dom & unit testing

Zeeshan: 
Google authentification with firebase
Wishlist functionality (panel, adding/removing products)
Wishlist and Sign In/Out frontend
Connecting wishlist and user accounts to database
Accessibility + shortcuts
Setting up and creating initial handler for backend mock api server 
Defensive Programming 

Omer:
Front end:
Dom & unit testing
Assistance with google authentification with firebase

Backend: 
Setting up and creating initial handler for backend mock api server 

Safae: 
Frontend : 
Creation & styling of components:
Search Bar
Platforms filtering
Search Results
Product price Statistics
Error Message
Implementation of functionalities (in data folder):
Interfaces to manage different data types
Retrieving of platforms (from mock data & from API)
Retrieving products from user search (from mock data & from API)
Retrieving prices for each product (from mock data & from API)

Backend:
Creating and implementation of final handlers for back end 
SneakerPlatformHandler, SneakerPriceStatsHandler, SneakerProductList 
  —> with mocking & making API calls
Created and implemented caching (all the HTTP and Proxy files)

## Backend
In the `src` package is `main` and `test`:
* `java` 

  * _SneakerSKUHandler.java_ : handles the request for the SKU and Image URL of a sneaker from its name (not used)
  * _SneakerPriceHandler.java_ : handles the request for the price of a sneaker from its SKU (not used)

  * _SneakerPlatformsHandler.java_ : handles the request for platforms
  * _SneakerPriceStatsHandler.java_ : handles the request for prices
  * _SneakerProductListsHandler.java_ : handles the request for product shoes after search

    * HTTP
      * PlatformsHTTP & PriceStatsHTTP & ProductListHTTP : calling API 
      * PlatformsProxy & PriceStatsProxy & ProductListProxy : Caching

* `test` and its subdirectories contains unit testing, fuzz testing, integration testing, and testing with mocks.


### API Endpoints
* Paid API will use: https://rapidapi.com/letscrape-6bRBa3QguO5/api/real-time-product-search/
MOCK API:
  * GET /sneaker/sku?name={name} : returns the SKU and Image URL of a sneaker from its name
  * GET /sneaker/price?sku={sku} : returns the price of a sneaker from its SKU

## Frontend
* `frontend` contains code for rendering the website

* `src` directory contains `data`, `components`, `tests` directories and `App.tsx`

  * _App.tsx_ : entry point of the webpage, where all the necessary components are rendered.

  * `mockdata` directory contains mock data 
    * _platforms.ts_ : provides a list of the different sneakers
    * _search.ts_ : provides a list of the different sneakers´ information (platforms, sku, image, color...) when looking up "Adidas"
    * _priceStats.ts_ : provides a list of the different sneakers´ prices on different platforms when looking up "Adidas"

  * `components` directory contains all the components that appear on the webpage: SearchBar, ProductDescription, SearchResults, Filter, Wishlist, & Google SignIn button

    * _SearchBar.tsx_: where the user can type the product he is looking for. 
    * _GoogleSignIn.tsx_ : let's the user sign in via their email address
    * _Filter.tsx_ : let's the user restrain the search to its selected platforms
    * _SearchResults.tsx_ : shows all the vendors selling the selected product 
      * _ProdcutPriceStats.tsx_ : shows the product description. Includes: picture + name + prices (accross all selected platforms + sidebar to visualze price range)
      * _Wishlist.tsx_ : shows the products the user has liked
  
  * `data`: where the functionnality is implemented
    * _dataTypes.ts_ : lists all the interfaces that represent data types used througout the project
    * _getPlatforms.ts_ : retrieves the platforms of a given shoe 
    * _getPriceStats.ts_  : retrieves the prices on all platforms of a given shoe 
    * _getProductList.ts_  : retrieves the products corresponding to a search by the user 
    * _getWishlist.ts_ :  retrieves the products the user has liked
    * _mockingMde.ts_ : whether we are mocking or making calls to the API
    * _reducer.ts_: handles the global state of the different components
    * _typePredicate.ts_ : has type guard functions for checking if given object is a ServerErrorResponse or isServerSuccessResponse

  * `tests` directory contains tests for the forntend 
    * _dom.test.tsx_: contains the DOM testing for the webapp
    * _unit.test.tsx_ : contains the unit testing for the webapp


## Errors and Bugs 

## Running the Program

* in folder H
* cd into backend --> src --> main --> server and run `Server.java`
  * go to `localhost:3232` and utilize API endpoints and parameters detailed in the API section of README.

* cd into frontend and run first `npm install` and then `npm start`, `npm run dev`, `npm install firebase`, `npm install @mui/material`, `npm install @emotion/styled`

* Run `Server.main()` and go to `localhost:3232` and utilize API endpoints and parameters detailed in the API section.

* Run the tests: `npm test` for frontend and `mvn test`
  * run the server before running integration tests

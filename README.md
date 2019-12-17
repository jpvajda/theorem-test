# theorem-test

# About this Repo

The purpose of this repo is to showcase the solution to the PM interview assignment from Theorem. 


# Exercise 

A Customer has a website that contains a database of thousands of professional quality tracks, which are available to be licensed for use in movies and commercials. Audio professionals use this site as part of their daily jobs to find and license music. There is an engaged and active user base and the company is making money.

Their customers have been asking for some changes to the site. Currently searching is done by using filter tools to narrow down results. The Users have been asking for a keyword search tool. Here are some quotes:

# User Feedback

**Users say** they want to just “type medium into the keyword bar and be able to easily
select the medium tempo”.

**Users say** “I want to search for movie title, track title, composer, tempo & instruments in the same keyword search bar”.

**Users say** “I want to be able to combine keywords in the search tool - for example “slow” may be a keyword that activates the tempo tool and the user can then type
“stringed/guitar” and then songs with ID 4 will be found”.


# General Requirements

## DataBase 

1. The existing Database will not need to change and there should be no change to DB schemas, DB type or DB design for this project. If at any point a DB change is required to move forward please raise that discussion to the PM team for evaluation. 

## Search & Filter API

1. Existing APIs should be leveraged if possible but the need for a new API endpoint such as  `https:musicsearchpro.com/customsearch/v1?[parameters]` may be needed.  to execute a search the user would initiate a `POST` Request on this new search endpoint and pass in their selected search parameters which are defined below.

2. These existing search parameters are currently in use by the UI's existing `UI Search Selectors`: radio buttons,  text fields and check box fields. This functionality should not change. This project will need to address the use of both a search selector and manual entry in the search bar field.  

3. All Filters should be subtractive in nature (current functionality) and only show results for each matching filter applied sequentially. 

### Search Parameters

| Parameter |  meaning |additional info |
|---|---|---|
| ID    | id of the db record  |  integer: unique DB identifer    |
| movie title  | title of movie   | string: char limit of 256   |
| track title | title of music track   | string: char limit of 256  |
| tempo (name)  | general speed of tempo  | string: can only be 1 value|
| tempo (bpm)   |beats per minute count   | integer: 0 - 200 |
| instrument group  | group type of instruments | string: can only be 1 value |
| instruments  | type of individual instruments | string: can only be 1 value   |
| composer  |name of composer   |string: char limit of 256  |
|   |   |   |



## UI / UX 

1. When a user has selected search criteria via the `UI Search Selectors`, the `Search Bar Field` should populate with the search parameters and be a visual queue to the end users that they have applied these parameters to the search query. 

2. Users can manually enter in search parameters in the `Search Bar Field`. 

3. Manually entries should be auto-complete, so a user knows what search parameters are available to them. 

3. When parameters are entered and they match existing database fields, show the parameter in a visual way such as with a highlighted box around the word. (see prototype for example). When a parameter is added the results should return accordingly. The User shouldn't need to refresh their screen to see the new results, the data should be reactive in nature. 

4. A user can easily remove a search parameter by selecting an X on the highlighted word box. When clicking X, the parameter is removed and the results should return accordingly.  The User shouldn't need to refresh their screen to see the new results, the data should be reactive in nature. 

5. Search parameters need to match existing database fields. If a manually entered parameter doesn't match the existing parameters, show an error in the UI: ` No Matches. Invalid Search Parameter`. 

6. A reactive count of results should always be return with each search query. 


## Documentation 

## Prototypes 



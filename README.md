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

1. The existing Database will not need to change and there should be no change to DB schemas, DB software or DB design for this project. If at any point a Database change is required to move forward please raise that discussion to the PM team for evaluation. 

## Search & Filter API

1. Existing APIs should be leveraged if possible but the need for a new API endpoint such as  `/search/music/[query parameters]` may be needed.  to execute a search the user would initiate a `GET` Request on this new search endpoint and pass in their selected search parameters which are defined below.

2. Search query parameters would be added to the URL such as `/search/music/?movie_title=title%of%movie&composer=first&last` which result in filtering of the data.   

2. These existing search query parameters are currently in use by the UI's existing `UI Search Selectors`: radio buttons,  text fields and check box fields. This functionality should not change. This project will need to address the use of both a search selector and manual entry in the search bar field. 

3. Search should also support a URI parameter such as `/search/music/{ID}`

3. All search filters should be subtractive in nature (current functionality) and only show results for each matching filter applied sequentially. 

4. Data should be returned in JSON to the UI. (current functionality).

### Search Parameters

| Parameter |  meaning |type and limitations |
|---|---|---|
| ID    | id of the db record  |  `integer`: unique DB identifer    |
| movie title  | title of movie   | `string`: char limit of 256   |
| track title | title of music track   | `string`: char limit of 256  |
| tempo (name)  | general speed of tempo  | `string`: can only be 1 value|
| tempo (bpm)   |beats per minute count   | `integer`: 0 - 200 |
| instrument group  | group type of instruments | `string`: can only be 1 value |
| instruments  | type of individual instruments | `string`: can only be 1 value  |
| composer  |name of composer   |`string`: char limit of 256  |
|   |   |   |



## UI / UX 

1. When a user has selected search criteria via the `UI Search Selectors`, the `Search Bar Field` should populate with the search parameters and be a visual indicator to the end users that they have applied these parameters to the search query. 

2. Users can manually enter in search parameters in the `Search Bar Field`. 

5. `Exact Search` - search parameters need to match existing database fields If a manually entered parameter doesn't match the existing parameters, show an error in the UI: ` No Matches. Invalid Search Parameter`. 

3. `Exact Search` When parameters are entered and they match existing database fields, show the parameter in a visual way such as with a highlighted box around the search parameter. (see prototype for example). When a parameter is added the results should return accordingly. The User shouldn't need to refresh their screen to see the new results, the data should be reactive in nature. 

3. `Exact Search Auto Complete` an auto-complete should be shown to the user for exact search entries. 

6. `Approximate Search` - search should support approximate string matching in the case of the parameters that are string values, e.g instrument group, instruments, composer, track title, movie title, tempo (name). 

4. `Search Parameter Removal` A user can easily remove a search parameter by selecting an X on the highlighted search parameter box. When clicking X, the parameter is removed and the results should return accordingly.  The User shouldn't need to refresh their screen to see the new results, the data should be reactive in nature. 

6. `Search Count` A reactive count of results should always be return with each search query. 


## Documentation 

## Prototypes 



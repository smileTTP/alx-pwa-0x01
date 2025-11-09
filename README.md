# alx-project-0x14

## API Overview
[MoviesDatabase API](https://rapidapi.com/SAdrian/api/moviesdatabase) is a RESTful web service that offers access to detailed information about movies, TV shows, actors, directors and related content. It provides reviews, ratings, plot summaries, high-quality images/videos and more. It enables search via different categories (title, actor, genre, release year, etc) and supports multiple languages.
This api provides complete and updated data for over 9 million titles (movies, series and episodes) and 11 million actors/crew and cast members.

## API Version
RapidAPI supports version 3 of TMDB. 

## Available Endpoints
Titles, Search, Actors, Obsolete.
Every endpoint returns and object with 'results' key.

| Endpoint | HTTP Method | Description |
| --- | --- | --- |
| /titles | GET | Returns array of titles according to filters / sorting query parameters provided |
| /titles/search/title/{title} | GET | Returns array of titles according to filters / sorting query parameters provided and the title provided in path |
| /actors | GET | Returns array of actors according to filters provided |
| /title/utils/titleType | GET | Returs array of title types |
| /titles/{id}/crew | GET | Returns an array of crew according to id provided |
| Other filters/parameters | GET | - |

## Request and Response Format
#### Example Request 
```git
GET https://moviesdatabase.p.rapidapi.com/titles/search/title/The%20Shawshank%20Redemption?exact=true&titleType=movie
Headers:
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
```

#### Example Response
```git
"results": [
           {"id":"tt0111161",
            "caption":{
                       "plainText":"Morgan Freeman, Tim Robbins, Clancy Brown, Mark Rolston, Gil Bellows, William Sadler, Bob Gunton, Brian Libby, and James Whitmore in The Shawshank Redemption (1994)"
                      },
           "titleType":{"text":"Movie", "id":"movie", "isSeries":false, "isEpisode":false, "__typename":"TitleType"},
          "titleText":{"text":"The Shawshank Redemption", "__typename":"TitleText"},
       "releaseYear":{"year":1994,"endYear":null,"__typename":"YearRange"},
       "releaseDate":{"day":2,"month":3,"year":1995,"__typename":"ReleaseDate"}}
]
```
## Authentication
Authentication is handled through API Key Headers via RapidAPI.

> X-RapidAPI-Key: YOUR_API_KEY
> X-RapidAPI-Host: moviesdatabase.p.rapidapi.com

## Error Handling
- 400: Bad request – Missing or incorrect parameters.
- 404: Not found – The movie or person you are searching for doesn't exist.
- 500: Internal server error – Something went wrong on our end.

## Usage Limits and Best Practices
#### Usage limits:
- Free plan:
1000 requests per hour
Pro plan:
5 requests per second

#### Best practices:
 - Storing the API key in environment variables.
 - Cache responses

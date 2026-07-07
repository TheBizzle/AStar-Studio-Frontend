# AStar-Studio-Frontend

## What is it?

The VueJS-based frontend for my weird A* Studio rewrites (for example, [the Golang one](https://github.com/TheBizzle/AStar-Studio-Golang)).

## What's the API that it expects from the associated server?

### `GET /example-maps`

  * Input (-): N/A
  * Output (JSON): A JSON string consisting of an array of the `{ name, delim, content }` objects
    * `name` (String): The name with which to display the example in the dropdown
    * `delim` (String): The character sequence that delimits lines in this pathing map
    * `content` (String): A string formatted as a 2D pathfinding map

### `POST /find-me-a-path`

  * Input (Plain text): A string formatted as a 2D pathfinding map
  * Output (Plain text): A string formatted like either of:
    * `0,T,M`
      * `T` (String): A `&`-separated sequence of integers that represent timings of the different heuristics
      * `M` (String): A string of the solved pathfinding map
    * `E,M`
      * `E` (Integer): The error code
      * `M` (String): A string of the failed pathfinding map

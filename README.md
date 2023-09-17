# nostr-event-33889

it's a parameterized replaceable event of kind 33889

we are creating a 2d table for each board (consider each board as a sql table or an excel spreadsheet)
so in such scenario we have:
- a title for each board (same as table names in sql)
- a couple of headers (each header is considered as a column name in sql , and also each header has a specific data format for all of its containing pins)
- a couple of pins (each pin is considered as a row in sql)

## event tags

### d
title of board (searchable)

example: `My Favorite Movies`

### image
cover image for board. direct url to image.

example: `https://images.unsplash.com/photo-1598899134739-24c46f58b8c0`

### description
a short text describing the board.

example: `Here is a board of my favorite movies in all genres`

### c
category for categorizing main topics (searchable)

example: `Entertainment` `Technology`

### f
format of pins in a board (searchable)

standard formats so far: `Image` `Video` `Link` `Text` `Profile` `Note`

### headers
consider headers as column names in a sql table (or in an excel sheet)

it's an array of header names followed by their data format, separated by `:`

example: `["headers", "Image:Content", "Text:Title", "Text:IMDB Rating", "Text:Director", "Link:Explore this director"]`

### t
a couple of tags related to each board (searchable)

example: `Movie` `Cinema`

### pin
consider each pin as an array of cells in each row of a sql table. the array is in order of headers.

** so the first item in a pin array is related to the first item in headers array.

also consider an empty string `""` inside the pin array as an empty cell in sql table. so we may have a pin like this:

["pin", "https://image.nostr.build/8634d4a64e4c7554b1b3ee6038ee4353a251fe4444c98473e03bd1c3b53ae97d.png", "Forrest Gump (1994)", "", "Robert Zemeckis", "", ""]


## other stuff
each board can be addressed by its coresponding `a` tag as defined in NIP-1 and also we can have a unique direct url to each board like this:

`https://pinstr.app/p/<pubkey-of-the-author>/<d-tag-of-the-event>`

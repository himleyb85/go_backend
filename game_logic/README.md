# Game Logic

## Contents
+ [Documentation Home](../README.md)
+ [Create New Game](#list-category)
+ [New Move](#search-category)

## Create New Game
**POST:** `/v1/new/`

**Note(s):**
+ User auth to be decided
+ Board sizes can be size 9-26
+ handicap param is optional

**Request:**
```json
{
    "player_w_id": 2,
    "player_b_id": 1138,
    "board_size": 26,
    "handicap": 1,
}
```

**Response:**
```json
{
    "game_id": 4,
}
```

**Status Codes:**
+ `200` if successful
+ `400` if bad request
+ `401` if unauthorized


## Post New Move
**POST:** `/v1/move/`

**Note(s):**
+ `"winner"` parameter only sent on game end

**Request:**
```json
{
    "game_id": "101",
    "new_move": [4, 12],
    "player_color": "b",
}
```

**Response:**
```json
{
    "capture_moves": "TODO-capture_moves",
    "game": "(;FF[4]CA[UTF-8]GM[1]SZ[24];B[cw])\n",
    "not_allowed": "TODO-not_allowed",
    "winner": "b"
}
```


**Status Codes:**
+ `200` if successful
+ `400` if bad request
+ `401` if unauthorized

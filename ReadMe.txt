                Welcome to Team 3's Battleship project!
                                PROJECT 1

In this file we will be explaining how our battleship game was created and how it works.
As a team we decided to use python as our coding language to implement this battleship game.
Our teams Battleship game used pygame as a library to produce a display of our game.

Instructions: When you start you will need to hit a key (1-5), this will choose the size of your fleet.
Once you've hit the number you want, you can either hit a different number to change your choice, or hit enter to confirm
Once you confirm you're in the ship placement phase.
Place a ship by clicking on your bottom grid, confirm the placement of the ship by hitting enter.
Once you have placed all of your ships, start click on the top grid to attack a square
Once the computer or you have sunk all the enemy ships, a win/lose screen will appear.
Hit enter to exit.

Now lets look at how this game was implemented:

    
    1. GameFlow Class

        - Overview: the gameflow class is used to run the game and do any interaction with the player. This class imports the display, computer, board, ship and tile classes.

        - broken into 4 main parts, 
          1: get the number of ships the user wants to place            chooseNumShips()
          2: place those ships and the computer's ships                 placeShipPhase() NOTE: press return key to confirm placement of ships
          3: attack phase where both teams attack the other's board     attackPhase()
          4: win phase, displays who won                                result()
        
        - game(): runs the function that plays the game
    
   2. Board Class
    
        - Overview: This class creates a board using an array to act as the game grid and imports tile and ship classes.

        - setTile(xCoord, yCoord, value): This function sets a valid tile to what ever is passed through value.

        - placeShip(direction, ship, xCoord, yCoord): Places a ship where the user wants it placed as long as it is valid and then sets the tile s acoording to where the ship is using the ships name to keep track of of it.

        - isValid(xCoord, yCoord): returns true if a tile at the given x and y coordinate hasn't been attacked.

        - attackTile(xCoord, yCoord): makes sure it is a valid tile to attack and rreturns true if it attacked and false if it was a invalid tile to attack.

        -getTile(xCoord, yCoord): takes in an x,y coordinate and returns the value inside of the tile.
    
    3. Tile Class

        - Overview: the tile class holds all the information we need to know about a square on the grid.
                    A tile either holds water, a ship or if it has been attacked or not.

        - getTileItem(): returns what type of tile is in a given coordinate.

        - getTileAttacked(): returns true if tile has been attacked before and false if not.

        - setTileAttacked(): sets the bool for the tile to true that it has been attacked.

        - setTileItem(tileItem): sets what is in the tile through the parameters.
    
    4. Ship Class

        - Overview: Holds information on wht kind of ship, its health, how long it is, and where they are on the board.

        - getName(): returns name of ship.

        - damageShip(): decreases a given ship's health by one.

        - isDead(): Checks if the health of the ship is zero and if it is returns true otherwise false.
    
    5. Computer Class

        - Overview: The computer class is used to control all things AI related. This class imports the random library, board, ship and tile classees.
                    In this class it has a private computer board for the AI and two funcitions to randomly select ship placement and how it guesses where to aim on the players board.
        
        - shipPlacement():  randomly selects an x,y coordinate and places a ship there.
                            It checks in a up, down, left, right pattern taking in account the ship to see if it can place the ship and places it if it can.

        - shipGuess(userBoard): randomly selects an x,y coordinate on the board and checks if it has already tried to shoot there and if it has it gets new coordinates and if not the it fires there. 


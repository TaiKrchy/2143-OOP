*will hold the placement of each dice and their corresponding grid to each player*

Class Player::

...Has a relationship with classes Dice and scoring...

[?]Data :: name, score, siceSet, stats

[!}Actions :: rollDice(), getScore(), updateScore()


**********************************************************************************************


*Gather the stats of each roll*

Class Dice:

...Has a relationship with player class...

[?]Data :: Sides, currentValue

[!]Actions :: rollDice(), getValue(), 


***********************************************************************************************


*Correctly calculates the scores from each player based upon their rolls and dice placement*

Class Scoring

...Has a relationship with Dice Class and player class...

[?]Data :: updatedScore, dice

[!]Actions :: getValueDice(), CompareScore()


***********************************************************************************************


*Compares the endGame results based on the scores provided from scoring class and will determine a winner*

Class endGame

...Is a type of scoring class...

[?]Data :: score, totalDice

[!]Actions :: getNumOfDice() [How much dice is in current grid], getScore()


************************************************************************************************


####[Necessary] :: FirstName, Highscore, LastName, PlayerStats, Score, userId, Winner

[Possible] :: coins, Leaderboard, Levels, streak

[Wishful] :: chat, Messaging, teamstats, teams

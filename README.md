# Furit-Teris
> - CMPT 361 Assignment 1
> - Created by Jiaxun He(Victor)
> - Used skeleton code provied by the TA
 
Furit-teris is a game based on the traditonal tetris game. The tiles have a fruit in each unit square with have special eliminating rules.

## Compile and Run
~~~
make
./FruitTeris
~~~

## How to Play
* 'r' -> restart
* 'q' -> quit
* 'p' -> pause
* 'a' -> accelerate
* 'up' -> rotate
* 'down' -> move tile down by 1
* 'left' -> move tile to the left by 1
* 'right' -> move tile to the right by 1

## Completion Status
* All of the required features are implemented
* Additional features:
	* pause game
	* accelerate falling speed


## Game Logic

### Tiles
* The tile, with random fruits and positions, appears in a random position at the top of the board.
	* If out of the board, initial position will be shifted horizontally to fit in the board
	* If colliding with an existing tile, initial position will not be adjusted
* Tiles have 4 shapes:
	* L shape
	* I shape
	* Z shape
	* T shape
* Tiles have 4 rotations for each shape:
	* Even I and Z have 4 rotations due to the different fruits in them.
* Change rotations
	* Press up arrow key to rotate, in counter-clockwise direction.
	* If there is no collison after rotation, rotate it.
	* If there is collison, move it by 1 unit horizontally to find a position without no collision. If it still does not work, then tile will not be rotated.
* Falling speed 
	* The initial falling interval is 1000ms.
	* Press 'a' and the interval will decrease by 200ms.
	* Minimum interval is 200ms.
	* No way to increase the interval except for restarting the game.
* Elimination
	* If there is a full row, it will be eliminated.
	* If there are more than 3 consecutive same fruits, they will be eliminated.
	* Real elimination will happen when all tests is done, which means that the maximum fruits will be eliminated.
	* Elimination will go on untill no fruits can be eliminated.
	* All the fruit will move down accordingly if a fruit below them is eliminated.
* Game termination
	* The game will halt when it's over, prompting on stdout that the game is over.
	


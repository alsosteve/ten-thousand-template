# Python 401d1818
## Lab06: Ten Thousand 1
### Author: 

### Setup
* Work in teams to build a command line version of the dice game Ten Thousand by expanding your understanding of Python standard library.

### Feature Tasks and Requirements
Create a project named `ten-thousand`.
Today is all about tackling the highest risk and/or highest priority features - **scoring, dice rolling and banking of points**.
  * Define a `GameLogic` class in `ten_thousand/game_logic.py` file.
  * Handle calculating score for dice roll
    * Add `calculate_score` static method to GameLogic class.
    * The input to `calculate_score` is a tuple of integers that represent a dice roll.
    * The output from `calculate_score` is an integer representing the roll’s score according to **rules of game**.
    
  * Handle rolling dice
    * Add `roll_dice` static method to GameLogic class.
    * The input to `roll_dice` is an integer between 1 and 6.
    * The output of `roll_dice` is a tuple with random values between 1 and 6.
    * The length of tuple must match the argument given to `roll_dice` method.
  * Handle banking points
    * Define a `Banker` class
    * Add a `shelf` instance method
      * Input to `shelf` is the amount of points (integer) to add to shelf.
      * `shelf` should temporarily store *unbanked* points.
  * Add a `bank` instance method
    * `bank` should add any points on the *shelf* to total and reset shelf to 0.
    * `bank` output should be the amount of points added to total from shelf.
  * Add a `clear_shelf` instance method
    * `clear_shelf` should remove all unbanked points.

#### Implementation Notes
  * Review [rules of game](https://en.wikipedia.org/wiki/Dice_10000)
  * Play [game online](http://www.playonlinedicegames.com/farkle)

#### User Acceptance Tests:
- [Starter tests](https://github.com/codefellows/seattle-python-401d18/blob/main/class-06/demo/parametrized-tests/tests/test_game_logic.py) will be provided that cover cases listed below
  - All tests must pass as written (additional tests are allowed)

### Testing:

#### Roll Dice:
When rolling 1 to 6 dice ensure:
- A sequence of correct length is returned
- Each item in sequence is an integer with value between 1 and 6

#### Calculate Score:
* zilch - roll with no scoring dice should return 0
* ones - rolls with various number of 1s should return correct score
* twos - rolls with various number of 2s should return correct score
* threes - rolls with various number of 3s should return correct score
* fours - rolls with various number of 4s should return correct score
* fives - rolls with various number of 5s should return correct score
* sixes - rolls with various number of 6s should return correct score
* straight - 1,2,3,4,5,6 should return correct score
* three_pairs - 3 pairs should return correct score
* two_trios - 2 sets of 3 should return correct score
* leftover_ones - 1s not used in set of 3 (or greater) should return correct score
* leftover_fives - 5s not used in set of 3 (or greater) should return correct score

#### Banker:
* shelf
  * should properly track unbanked points
* bank
  * should properly add unbanked points to total and return the deposited amount
* clear_shelf
  * should remove any unbanked points, resetting to zero.
  * should not affect previously banked points

### Stretch:
- Research `parametrized tests in PyTest`
- Research `Behavior Driven Development`

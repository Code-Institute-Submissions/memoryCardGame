# Testing

### Manual testing

#### Tested responsiveness in Chrome:
Page was tested to make sure it was responsive to all devices. "Responsive" slider was used to make sure content is shown correctly on desktop, tablet and mobile, that they look as desired by the developer.

Tested the pages on all sizes/devices available in Chrome.
- 360 x 640 Blackberry Z30 & Galaxy Note
- 375 x 812 iPhone X
- 375 x 687 iPhone 6/7/8
- 411 x 731 Pixel 2
- 411 x 823 Pixel 2 XL
- 414 x 736 iPhone 6/7/8 Plus
- 600 x 1024 Blackberry PlayBook
- 768 x 1024 iPad
- 1024 x 1366 iPad Pro

#### Tested interaction in Chrome, Firefox and Opera(mobile):
Page buttons were tested for correct operation and whether they operated and opened intended parts of page(difficulty levels etc.)
1. Easy button - opened easy level assigning 8 tiles to the grid
2. Medium button - opened medium level assigning 12 tiled to the grid
3. Hard button - opened hard level assigning 16 tiles to the grid, opening timer
4. ? in the footer, opens welcome modal that explains game rules
5. Clicking close in win modal reloads the game
6. clicking close in game over modal reloads the game
7. Clicking close in welcome modal closes it allowing for the difficulty level to be picked 

#### Tested game logic using using Chrome, Firefox and Opera(mobile):
This test was done to make sure JavaScript runs correctly (as desired) on these browsers.
1. Attempted to click more than 2 cards in 1 turn
2. Attempted to double click in order to achieve a match on 1 card
3. Tried to change difficulty levels many times in order for grid to be created incorrectly
4. Changed difficulty level from hard to other one and then returning to hard trying to overlap setInterval timer function for the timer to count down quicker than every second
5. Picking the same level and uncovering the same card in a grid hoping card deck stays not shuffled
6. Playing game on 1 level then changing the game hoping for tiles on new level that were also displayed on previous level to remain not shuffled
7. Changing level mid way playing the game hoping for the turn counter to remain unchanged

#### Testing summary:

##### Responsiveness problems:
- Difficulty buttons were moving from inline to block early, when the board was still underneath them not to the right. This was very bad UX - changed media in css

##### Interaction problems:
- no problems recorded

##### Game logic problems:
- Double clicking of the card was assigned as a card match - fixed
- Game switched mid way was not resetting turn counter - fixed

### Automated testing

Following online validators were used to test the code:
- [W3C Markaup Validation Service](https://validator.w3.org/) for HTML validation
- [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/) for CSS validation
- [JS Hint](https://jshint.com/) for JavaScript validation

#### Testing summary

##### HTML validation:
It brought up no errors and 1 warning about empty header h2 - this tag is used by JavaScript to display timer. Left unfixed.

##### CSS validation:
No errors found.

##### JavaScript validation:
Few semicolons missing - fixed.
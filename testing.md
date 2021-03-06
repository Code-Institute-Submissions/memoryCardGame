# Testing

- [Testing](#testing)
  - [Manual testing](#manual-testing)
    - [Responsiveness](#responsiveness)
      - [Bugs - responsiveness](#bugs---responsiveness)
    - [Interaction](#interaction)
      - [Bugs - interaction](#bugs---interaction)
    - [Logic](#logic)
      - [Bugs - logic](#bugs---logic)
  - [User stories testing](#user-stories-testing)
  - [Automated testing](#automated-testing)
    - [HTML validation](#html-validation)
    - [CSS validation](#css-validation)
    - [JavaScript validation](#javascript-validation)

## Manual testing

### Responsiveness

- **Plan:** this game was planned to be responsive, working on all devices - mobile phones, tablets and desktops. Following this it was planned for Bootstrap library to be used for a page design.
- **Implementation:** page was **tested in Chrome Developer Tools** throughout the process of putting it together to make sure it was responsive to all devices. "Responsive" slider was used to make sure content is shown correctly on desktop, tablet and mobile, that they look as desired by the developer. Bootstrap classes as well as media rules were used to adjust responsiveness.
**Tested** the pages **on** all sizes/devices **available in Chrome**, these were:
  - 360 x 640 Blackberry Z30 & Galaxy Note
  - 375 x 812 iPhone X
  - 375 x 687 iPhone 6/7/8
  - 411 x 731 Pixel 2
  - 411 x 823 Pixel 2 XL
  - 414 x 736 iPhone 6/7/8 Plus
  - 600 x 1024 Blackberry PlayBook
  - 768 x 1024 iPad
  - 1024 x 1366 iPad Pro

- **Results:** page is responsive and can be used on all planned devices. There are no elements on this page that are not responding as planned.
- **Conclusion:** all tests that were run on responsivenes were passed therefore page is fully responsive.

#### Bugs - responsiveness

Throughout the develompment process I came across several bugs related to responsiveness.

1. **Difficulty buttons**
      - **Bug:** buttons were moving from inline to block too early, they were stacking on top of each other while the board was still displayed underneath them and not to the right
      - **Fix:** amended media rule in CSS
      - **Result:** this bug was removed and difficuty buttons are not fully responsive and as expected
2. **Cards**
      - **Bug:** buttons were moving from inline to block too early, they were stacking on top of each other while the board was still displayed underneath them and not to the right
      - **Fix:** amended media rule in CSS
      - **Result:** this bug was removed and difficuty buttons are not fully responsive and as expected
3. **Number of cards in a row**
      - **Bug:** there were more than 4 cards displayed in 1 row misshaping the grid
      - **Fix:** amended card sizes for certain screen sizes in media rules in CSS
      - **Result:** this bug was removed and cards are now displayed 4 in a row on all devices tested

### Interaction

- **Plan:** there are elements that are planned to be interactive on this page, these are buttons, cards and modals
- **Implementation:** was carried out on many devices and on several browsers, including Chrome, Firefox and Opera. Following elements were tested:
  - Easy level button:
    - seleceted easy level and confirmed assigning 8 tiles to the grid
    - played the game finding 3 out of 4 matches and re-clicked easy button to make sure new grid is created and game is reset
    - confrimed that each time easy button is clicked all cards are being re-shufled
    - completed the game in easy mode and confirmed that win modal is displayed
    - clicked another diffuculty and confirmed that easy grid is being replaced with another difficulty grid
  - Medium level button:
    - repeated all steps from easy button level and confirmed that correct grid is assigned/displayed, cards are re-shuffled and game reset when clicked
  - Hard level button:
    - repeated all steps from easy button level and confirmed that correct grid is assigned/displayed, cards are re-shuffled and game reset when clicked
    - selected hard level and confirmed the timer is reset to count down
  - Win modal:
    - confirmed that clicking close in this modal reloads the game
    - confirmed that there is no possibility to click on the backdrop of this modal
    - confirmed that there is no possbility of closing this modal using keyboard
  - Game over modal:
    - confirmed that clicking close in this modal reloads the game
    - confirmed that there is no possibility to click on the backdrop of this modal
    - confirmed that there is no possbility of closing this modal using keyboard
  - Welcome modal:
    - confirmed that clicking close in this modal modal closes it allowing for the difficulty level to be picked
  
- **Results:** all tested elements are interactive as planned . There are no elements on this page that are not responding as planned
- **Conclusion:** all tests that were run on interactivity were passed therefore page is interactive
  
#### Bugs - interaction

Throughout the develompment process I came across two bugs related to page/game interaction.

1. **Game over modal**
   - **Bug:** clicking keyboard or modal backdrop was allowing for a game to be carried on even though time has run out and modal was still displayed
   - **Fix:** switching backdrop off in this modal as well as initializing modal without keyboard
   - **Result:** this bug was removed and only clicking x will close the modal
2. **Win modal**
   - **Bug:** clicking keyboard or modal backdrop was allowing for another game to be started without reset
   - **Fix:** switching backdrop off in this modal as well as initializing modal without keyboard
   - **Result:** this bug was removed and only clicking x  or "Close" will close the modal

### Logic

- **Plan:** this game is planned to have 3 difficulty levels with either 8, 12 or 16 tiles displaying and requiring from the player to match 4, 6 or 8 pairs. Game should count turns after 2 cards are revealed, it designed to display win modal after all pairs are matched. There is also time limit on level hard - this will be displayed to the player as a counting down timer. Should player fail to match all pairs in this time game over modal is going to be displayed. The game is starting with Welcome modal explaining game rules, this will be repeated each time game is reset.
- **Implementation:**
  - attempted to click more than 2 cards in 1 turn
  - attempted to double click in order to achieve a match on 1 card
  - tried to change difficulty levels many times in order for grid to be created incorrectly
  - changed difficulty level from hard to other one and then returning to hard trying to overlap setInterval timer function for the timer to count down quicker than every second
  - picking the same level and uncovering the same card in a grid hoping card deck stays not shuffled
  - playing game on 1 level then changing the game hoping for tiles on new level that were also displayed on previous level to remain not shuffled
  - changing level mid way playing the game hoping for the turn counter to remain unchanged
  - clicked hard level few times to check whether the timer resets
- **Results:** all tested elements are working properly. There are no elements that present problems with logic
- **Conclusion:** all tests that were run on logic were passed
  
#### Bugs - logic

1. **Cards:**
   - **Bug:** double clicking on the card was assigned as a card match
   - **Fix:** added another level of comparing card matching, making sure that both cards don't have the same Id
   - **Result:** this bug was removed and double clicking in not resulting in card match but it is forcing the player to carry on the game
2. **Difficulty level**
   - **Bug:** difficulty level changed in the middle of the game was not resetting the timer
   - **Fix:** fixed by adding timeLeft = 0 every time after new grid is created
   - **Result:** this bug was removed and every time level is changed before game is finished timer is reset
3. **Hard level**
   - **Bug:** double clicking hard level button caused the timer to count down fast, faster than every second,
   - **Fix:** added clearInterval(timer) before the interval is set within the function that checks which difficulty is being picked
   - **Result:** this bug was removed and the timer works correctly now
4. **Timer**
   - **Bug:** changing difficulty level after the fast count down started reset the grid to another one but the timer was still running down to 0 and bringing up game over modal
   - **Fix:** added clearInterval(timer) before the interval is set within the function that checks which difficulty is being picked
   - **Result:** this bug was removed and the timer works correctly now

## User stories testing

1. As a user I want to play easy but not too involving game to kill spare time (eg. during travel etc.):
    - this game is perfect to play in spare time, it is easy to operate, engaging and not too complicated
    - playing this game does not require too much concentration therefore can be played on the move
    - easy and quick game for a user to keep themselves occupied during spare time
  
2. As a user and a parent I want the game that is easy enough for my children to operate:
    - game that requires matching 2 cards only is not too complicated even for very yung children
    - game is easy to operate - just couple of clicks gets children engaged and challenged
    - game allows user to pick easy level that requires matching only 4 pairs
    - for older children there is also added difficulty of time limit on leve hard - easy but challenging

3. As a user I want to play the game that is visually appealing:
    - game is very colorful and nice looking
    - game presents user with characters that attract attention
    - fonts and colors used evoke emotion

4. As a user and a parent I want to be presented with cards that present known to me characters:
    - game presents users with very popular game and comic book characters from 80s: Mario and Luigi - 2 plumbers from [Mario Bros](https://en.wikipedia.org/wiki/Mario_Bros.), [Donkey Kong](https://en.wikipedia.org/wiki/Donkey_Kong) from very popular game of the same name, Arcade's [Frogger](https://en.wikipedia.org/wiki/Frogger), [Bomb Jack](https://en.wikipedia.org/wiki/Bomb_Jack) as well as ghost from [Pac-Man](https://en.wikipedia.org/wiki/Pac-Man), complimented with 2 from the list of the most popular comic book characters that debuted in 1980s - [Robin](https://en.wikipedia.org/wiki/Tim_Drake) & Leonardo - one of 4 [Ninja Turtles](https://en.wikipedia.org/wiki/Teenage_Mutant_Ninja_Turtles).

5. As a user I want to be presented with the characters that can spark conversation between parents and children:
    - introducing characters that were very popular in 80s and beginning of 90s will allow children to ask parents some questions about them
    - characters used in the cards can also allow parents to present children with original games and comics that the characters come from
  
## Automated testing

Following online validators were used to test the code:

- [W3C Markaup Validation Service](https://validator.w3.org/) for HTML validation
- [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/) for CSS validation
- [JS Hint](https://jshint.com/) for JavaScript validation

### HTML validation

It brought up no errors and 1 warning about empty header h2 - this tag is used by JavaScript to display timer. Left unfixed.

### CSS validation

No errors found.

### JavaScript validation

Few semicolons misplaced - fixed.

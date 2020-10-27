<!-- # my-first-readme
Repo explaining README.md

## Steps to install on local computer
1. Go to [repo](https://github.com/SEI-ATL/tic-tac-toe) on Github profile
2. `fork` and `clone` repo
3. Clone to local machine
```text
git clone https://github.com/SEI-ATL/tic-tac-toe.git
```
4. Go to `tic-tac-toe` directory
5. Open `index.html` in browser
```text
open index.html
```

```Javascript
const handleWin = (letter) => {
  gameIsLive = false;
  if (letter === "x") {
    statusDiv.innerHTML = `${letterToSymbol(letter)} has won!`;
  } else {
    statusDiv.innerHTML = `<span>${letterToSymbol(letter)} has won!</span>`;
  }
};
```

```css
.grid {
    background-color: salmon;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 15px;
    margin-top: 50px;
}
```

```html
<div class="grid">
    <div class="box" id="box-1"></div>
    <div class="box" id="box-2"></div>
    <div class="box" id="box-3"></div>
    <div class="box" id="box-4"></div>
    <div class="box" id="box-5"></div>
    <div class="box" id="box-6"></div>
    <div class="box" id="box-7"></div>
    <div class="box" id="box-8"></div>
    <div class="box" id="box-9"></div>
</div>
```

| functions           | Description |
| -----------         | ----------- |
| `handleWin()`       | Handle the win |
| `checkGameStatus()` | Check the status after each turn | -->


# Tic Tac Toe README.md
Repo explaining my 1v1 tic tac toe game

## Javascript
With this `handleTurn()` function I first set my conditional statement to not declare a winner and then proceeded to find the index of the squares that were clicked by the event handler and returned that statement. I then proceded to let the turn continue by setting another conditional statement to continue if the turn was X's then the turn would become O's and so forth until a winner is determined then i would run my `getWinner()` function and `render()` function. I returned the conditional statement at the end in order to let the reset button restart the game
```javascript
function handleTurn() {
    if (!winner) {
        let idx = squares.findIndex(function(square) {
            return square === event.target;
            });
            
            board[idx] = turn;
            if (turn === 'X') {
                turn = 'O'
            } else {
                turn = 'X'
            };
            winner = getWinner();
            render();

    } else {
        return
    };
};
```

## CSS Styling for hover
I wanted the squares that held the X's and O's to change when a cursor was pointed at it. So I included this effect on my CSS which allowed me to include a background image which helped me give the game a distinct attribute that reminded me of an old fighting game.
```css
.square:hover {
  cursor: pointer;
  background-image: url(https://cdn.hipwallpaper.com/i/84/80/pREXMc.png);
  background-position: center;
  transition: 0.2s ease-in-out;
}
```
## HTML

Now with the `html` I decided to create my gameboard using one div with the `class="square"`. I figured it would be my best approach in making it easier to style as well as helping me add IDs for each box in the `JS` itself. That way I was able to save some time and not add a different `ID` element to each `.square` in the `HTML`.
```html
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
<div class="square"></div>
```

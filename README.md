# Juegos
### A Discord in-app game bot
https://panley.co.uk/juegos

Coded in Python using the following Dependencies:
[Python version 3.6.X](https://www.python.org/downloads/release/python-368/)
[Discord.py wrapper (Async Branch)](https://discordpy.readthedocs.io/en/async/api.html)


### Installation

Simply download the files above and run them from the same folder.
On fisrt run, your bot token file will assumedly be empty, you will be asked to provide your bots token within the first running of the script to fix this.

**The bot comes with TicTacToe and connect 4 pre-installed!**

Games are installed by adding the PY files to the same folder as the main script and appending thier functions to main.py

# Adding a game to Juegos

## 1. Create a new PY file with functions to be called by main.py

### Example of a game PY file

```py
def firstrender():
  #Used to define the board status and size before any turns have been enacted
  return "some nested list of emoji that represent pixels"
def makeplay(user,msg):
  #Carries out a "play" based on user input, returning false simply insinuates an invaild or no play was made. If the user says "exit" they leave the game
  return "user object with amended board if a valid play is made, or False if not (or "exit" if the player said exit and the game accepts user leaving)"
def wincond(user):
  #Systematically checks for any 3 of the same emote in a row where one can't be the blank emote, stopping a blank board from being a win
  return "True or False"
def losscond(user):
  # Simple function to check if the board is full, thus meaning there are no possible moves and no-one wins
  return "True or False"
```

You can add functions that are not listed here, import other scripts for advanced functions etc. Any functions can be added to main.py and called as is standard with any py script

## 2. Create a list of game aliases with arbritrary mp/sp declarations and a dict of all of your games info

### Example of game list and gameinfo dict entry:

```py
["tictactoe","ox","mp","noughts&crosses","ox","mp"]
{"ox":{"desc":"basic match three game","selfname":"ox","aliases":"tictactoe | noughts&crosses","creator":"Panley#3274","minplayers":2,"maxplayers":2,"ctrlmsg":"To control the game, reply with game commands. In this game, reposnd in the following fashion:\n`tl` `tm` `tr`\n`ml` `mm` `mr`\n`bl` `bm` `br`","cscheme":[0,0]}}
```

The list and dict **MUST** be seperated by a newline so they may be seperated and handled seperately, this list must also be the highest line.

The entries require all info listed here **if you want your game to respond to reactions** you should also define the emoji with the format: `"reactions":["👍","🖓"]` This currently doesn't take custom emote arguments, but it would not be a hard task to have the bot check if an object in the list is a 1 char long unicode emote or a discord role ID and have it fetch the emoji.

## 3a. Use the ~addgamefile command to add the relevant game files to your install of the bot

**THIS COMMAND IS EXPERIMENTAL AND WILL TAKE ANY FILE AT FACE VALUE**
This means if you pass it bad files with no or incorrect code or configs, it will still update the bot file. This may be destructive to the bot.

The command will guide you through the process, simply pass it the files you wish to add and it will do all the hard work for you!

## 3b. import your script and call functions in main.py and add the info to the config files manually

**THIS METHOD IS REQUIRED FOR CUSTOM TRIGGERS**

Simply appned your game configs to the existing ones in the relevant files to add their configurations.

All locations for calling functions are marked in main.py with comments. Additional functions may be added and accounted for outside of the standard ones provided by simply calling additional functions on the standard triggers or coding a custom trigger and control scheme value.

## Like the code?
[Join the creators discord server and test the bot!](https://discord.gg/tBs8MRE) | [Keep me coding and drop me a donation!](https://panley.co.uk/pp) | [Buy some awesome pride month programmer merch!](https://panley.co.uk/shop-pantopia)

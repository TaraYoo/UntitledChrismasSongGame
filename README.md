# UntitledChrismasSongGame - GDD

## Introduction
The player is a retail worker who needs to navigate their department store to turn off Christmas music. The player needs to hide their sabotage from managers and evade customers as much as possible.

### Genre
Pacman clone
### Player Type
Single player
### Game Play
Stealth
### Technical Form
?????????
### History
??????????
### Reference
Pacman (I've actually never played Pacman)
### Theme
??????????
### Design Intentions (original or cloned)
????.. cloned??


## Game Analysis
### Game Description
1. Genre: Stealth
2. Game Elements: Hiding, moving, time management
3. Game Content: Existential horror (?), stealth, humor
4. Theme: Modern dystopian
5. Style: ?????????????
6. Game Sequence: 3 levels
7. Player: 1

### Reference
#### MVP version
The AI's view scope (whether or not a manager or customer can spot you) could follow the stealth mechanics in the monkey trailer section of Eastward
The player needs to balance two status bars over a set time per game level (similar to Stardew Valley)
- a sanity rating (goes down while the music is playing), 
- and an employability rating (goes down when the manager or when customers catch you turning off the music or sneaking around)
#### Beyond MVP
- Once we have a finalized MVP of *just* the gameplay, I'd like to incorporate more story that ties each day to the next and some basic
resource management with a story and vibe similar to Papers, Please
- Having environment management puzzles, such as disrupting a product layout, etc, to distract managers and customers like the Untitled Goose Game might also be fun

### Game Technical
#### Technical Form
2D graphics
#### View
Top-down
#### Platform
PC
#### Language
C# (I'm planning to do this in Unity since there's a lot of tutorials and resources available)
#### Device
PC

### Game Atmosphere
#### Atmostphere Section
?????????????

### Gameplay
#### Game Loop
##### Basics (MVP) (numbers are only included for reference)
1. Player's shift starts -- a timer at the top right hand corner indicates how much time the player has left
2. Player's sanity bar and employability bar starts full. Both are at 50/50
3. Sanity score decreases by 1 x number of speakers that are playing music per second (or per timer tick)
4. Each level has a box of displays. Characters cannot walk through these displays. Managers and customers can't see through the displays
5. Each display holds objects for sale.
6. Player navigates to a speaker and clicks on it. This will turn the speaker off. Turning a speaker off changes the speaker animation or indicates in some other visual way that the speaker is turned off
7. Manager has a cone-shaped line of sight that cannot see through displays. If a player turns off a speaker within the manager's line of sight, player's employability goes down by 10
8. When a speaker gets turned off, the manager will start navigating towards the speaker to turn it back on
9. If the player runs into the manager, their employability goes up by 10 and their sanity decreases by 10
10. If the player runs into a customer, they have to lead the customer to an object they want to buy. The customer will keep following the player. The player's sanity keeps ticking down. The player's employablity will keep ticking down the longer they take to find the thing. Finding the object increases employability by 10. 
11. If the player runs into a customer, and *don't* lead the customer to the object they want to buy, the player's employability decreases by 10.
12. If the player's employability goes to 0 before the end of their shift, they get fired (game over)
13. If the player's sanity goes to 0 before the end of their shift, they get fired (game over)

##### Nice-to-haves
1. Running into a manager starts a mini game. While the player is completing the minigame, such as catching birds, sorting cans, etc, their sanity will keep ticking down. Employability goes up depending on how quickly and well the player finishes
2. The player can run away from the customer without helping them. This does *not* immediately decrease the player's employability. But the customer will go find the manager, and after that, the manager and customer will move around together to find the player. If the player gets caught by both the manager and customer, their employability decreases by double the normal score. (bonus challenge -- player runs away from *multiple* customers, creating a mob of customers + manager)
3. Each customer can always buy the same thing. A player, if they spot the pattern, can start picking up the object and placing it in the customer's path. This will increase their employability by 15
4. There could be movable obstacles the player could arrange to direct customers towards the manager. If a customer runs into a manager, both will stop bothering the player for a short amount of time.
5. Ending the day with a full employability + sanity levels up the player and gives them TBD bonuses
6. Player can break a speaker via a mini game (but they'll stay in place while they're breaking the speaker, which means a manager or customer can run into them, and sanity will keep ticking down)


#### Opening the game application
TBD
#### Game Options
- screen size
- level length (?)
#### Story Synopsis
- MVP will not have a story
- Beyond MVP .. maybe a unionization storyline? Survival on minimum wage?
#### Modes
TBD
#### Game Elements
##### Player
Player has a top-down view of the entire map because that's the only viewpoint I can play without getting nauseous
##### Manager(s)
Manager(s) have a cone-shaped line of sight that gets blocked by the display blocks. Managers will move around randomly until they run into the player, or see the player turning off speakers. (Should their vision be limited? How do we indicate what their sight range is?) If the player turns off a speaker, the manager will go towards the speaker to turn it back on.
##### Customer(s)
Customers move around randomly until they run into the player. When they run into the player, they'll ask for help finding something. They'll then follow the player around until the player takes them to a display block for the thing they want to buy.
##### Display blocks
Each display block clearly indicates somehow that they're displays of a thing for sale. Game characters can't go through these blocks or see through the blocks. This means that if the manager is on the other side of a display block while the player turns off a speaker, the manager won't catch them.
##### Speakers
Each speaker clearly indicates whether it's off or on. 
##### Shift Timer
Shift timer shows how much time the player has left on their level
##### Employability Bar
Employability scores increase when:
1. Player leads the customer to the display block for the thing they wanted to buy
2. Player runs into a manager when they *weren't* turning off speakers
Employability scores decrease when:
1. Manager catches the player turning off speakers
2. Customer is following player around, waiting for them to lead them to the object they want to buy
##### Sanity Bar
Sanity scores increase per timer tick as long as there's at least one speaker playing music. Sanity score will decrease faster the more speakers are on


#### Game Levels
##### Basics (MVP)
A square grid. The display blocks get procedurally generated, so each level is slightly different. Each display block will stand for one object for sale.
There's 1 manager, 1 customer (at a time), 1 player, ~4 things for sale, and ~3 speakers

##### Nice-to-have
Every...3(?) levels or so, the player will advance to working at a bigger store with more customers and display blocks. 
Bigger layouts will increase the number of managers, customers, things for sale, and speakers.


#### End
MVP: game ends after 2 levels
Beyond: Union? Becomes the manager? 
#### Why is this fun?
TBD

### Key Features
#### Number of levels
MVP: 1 (or maybe 2)
#### Number of enemies / characters
MVP: 1 manager, 1 customer (at a time)
#### Time of Game Play
3 minutes or less per level?
#### Replayability
MVP should be a fun way to kill a few minutes once or twice and not much beyond that
#### Audio Specifications
????????
#### Graphic Specifications
low
#### Device compatibility
?????????
#### Number of Players
MVP: single player
#### Online Activities
None
#### Number / Type Modes
????







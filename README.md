# QMonopoly
A quantum monopoly game

![image](https://user-images.githubusercontent.com/29524895/141688811-42082c55-de54-4a8f-834e-708b4042ca19.png)

## The idea
Combining with the well-known fable "The Little Prince", we present a quantum online board game allowing quantum novices play together during the pandemic!

(This game was devleoped during the Qiskit Fall Fest Hachathon and was selected as Second Place award among 6 other projects in the [Taiwan SQCS Quantum Hackathon, 2021](https://qiskitfallfest.hypeinnovation.com/servlet/hype/IMT?documentTableId=396317851979055264&userAction=Browse&templateName=&documentId=1a0c3bc2a3e054f2f9fcce91f3584020))

## Teammates
- 精誠中學 林祐平: Art design and initial game dev 
- 精誠中學 辛珮瑄: Chance/Fortune system design and initial game dev
- 惠文高中 郭峻維: Game flow and map design
- 建國中學 賴昱錡: Bank system design
- 陽明高中 謝卓翰: Host system design

## The issue description
As the fundamental building block for quantum information science, the idea of Quantum Circuits language is usually confusing for beginners.
To promote the idea of quantum circuit and let players practice through playing and during the pandemics, we aimed to design a board-game which allows players to compete online with each other by solving quantum circuits which maps to given quantum state set.

## Our proposal
Kids love games, and in this game we adopted the game mechanism from the well-known Monopoly game with the aim that global audiences are more familiar with.
To make this game suitable to play with adolescents and adults alike, we derived our story line from the fable "The Little Prince".

## Rule 101
The players are going to collect quantum logic gates (X, H, CX gates) from the monopoly-like game map to put together some quantum circuits which generate the given challenge quantum state set (|000> + |011>, for example). The player will be rewarded with a rose when solved a challenge, and the first player who collected 5 roses will be the winner!

## Procedure:

### Preparation phase

### Main game phase
After the preparation phase, the main game phase follows and all players proceed in turns. During each turn a player will:
1. Throw a plain dice () or initiate remote dice to use his/her gates to go to projected spots based on the measurement of his/her quantum circuit.
2. Interact with the map depends on the spot landed
- The Gate spot: Collect corresponding gates. If there's a x2 then got doubled gates. If the player is in superpositioned/entangled states then he/she may collect all gates based on the spots that he/she landed on.
- The "Fortune/Chance" spot: Activate Fortune/Chance mode and draw one card from the corresponding deck. Some Fortune/Chance cards may be saved to be used later in the game. There is no limitation in how many cards may be used during each turn, and players may activate a card at any moment during the game as long as it's his/her turn.
- The Stair spot: Activate storymode and draw one story card from the deck, the story mode rewards gates immediately to the player once the card is drawn.
3. Propose one quantum circuit solution to the given challenge and get one rose as a reward. Can only solve one challenge per turn.
4. Decide how many roses to be stored into or move out from greenhouse. The number of roses in greenhouse are counted as x1.2 times during the end of his/her turn due to getting better care. (note: the factor only counted once during the turn and do not stack between turns - i.e. if a player has 10 roses in greenhouse and stay for two turns, then the number counted as 12 roses throughout the turns instead of 12 in the first turn and 14 in the second turn.) Rose counts follows four-in-five rule.
5. Decide if he/she want to break the lock to other player's greenhouse by submitting a quantum circuit. If the lock-picking is successful then he/she can steal 70% of the roses in the greenhouse. (steal counts follows four-in-five rule) No roses outside of the greenhouse can be stolen.

### Winning condition
During the end of each player's turn, apply the greenhouse factor (x1.2) and count all roses the current player has. If the rose count is greater or equal to 10 roses (after four-in-five rule applied) the player wins. If not, continue to the next player.

### Further explanation
1. How the dice work:
- A plain dice: a simple random 8-faced dice.
- Remote dice: Player are allow to use gates from their hand in a 3-qubits circuit to project themselves to up to 2 particular spots (the ones closest to the player) predicted by the measurement results. For example if the user puts an H gate at qubit 0 and CX target at qubit 1 and control at qubit 0, then he/she can move to two spots which are 1 and 4 steps away from his/her current location (000 gives 1 while 011 gives 4) The player will then be able to perform up to two interactions as described in the second step during the main game phase during the same turn (collect two types of gates/draw a card and collect a gate etc).  
2. How the greenhouse lock (and lock-picking) works
- 每位玩家在遊戲的一開始皆會收到主持方給的溫室密碼
- 各個玩家皆可透過手邊的量子閘，最多嘗試兩次量子電路猜到其他玩家的溫室密碼，以進入溫室偷取玫瑰
- 在偷取玫瑰後，玩家在下一輪須因犯法而關進牢中一輪（一旦偷皆需要關），不可進行擲骰、解題、偷竊等一切行為

### Cards at a glance
#### Fortune cards
- go to the nearest “X” gate (up to player) x2
- go to the nearest “H” gate (up to player) x2
- go to the nearest “CX” gate (up to player) x2
- Meet the naughty foxes and take a break for one turn to protect your roses
- Fell down on the way (Back three spots)
- Unexpected surge of signal crosstalks and reduce the number of each gates on hand by one for the player.

#### Chance cards
- "SWAP card": Change the challenge question (can be saved for later use)
- "RESET card": Meet the pilot and take his plane back to “GO” on the map (can be saved for later use)
- “ANGEL card” Can choose any one gate you want and add to your hand, all player also get one as well (can be saved for later use)
- “WISH card” Can move to any one spot on the map as you wish
- “BOSS card” For a certain type of gate, you can get two-thirds of the number of that gate within all players' hands. (gate count follows four-in-five rule; can be saved for later use)
- “REWARD card” Won first place during a rose beauty pageant and collect double gates for one round when land on the map (can be saved for later use)
- “STEERING card” Reverse the order of players (can be saved for later use)
- “SNATCH card” Steal one type of gate from one other player's hand (the target player will be left with none of that type of gates; can be saved for later use)
- “LOVE card” Roses in the greenhouse enables to thrive 

#### Story cards
1. 在與玫瑰分離時，小王子終於明白:我愛你，所以待不待在彼此身邊，不再重要(CX+X)
2. 如果你愛著一朵盛開在浩瀚繁星裡的花，那麼，當你抬頭仰望繁星時，便會感到心滿意足(CX,X,H)
3. 小王子理解到甚麼才是真正的馴服，一次一次的伸出觸角去摸索，接著找到付出愛的方式(H+X)
4. 小王子從狐狸身上學到"人只有用心看才能看清一切；最重要的事務室眼睛看不出來的(H)
5. 小王子領悟到了甚麼是愛，狐狸對他說"你在玫瑰身上所花費的時間，讓你的玫瑰變得如此重要(X)
6. 蛇對小王子說“孤單跟你在哪身邊有誰無關”(X)
7. 小王子了解到解除孤單的方法並不是逃離並不是把自己塞進人群裡，而是學著面對接受自己感到孤單這件事(CX+H)
8. 小王子對其他玫瑰說"當然一個路人可能會覺得你們和我的玫瑰是一樣的，但是對我而言，我的玫瑰比你們更重要，因為他是我澆灌的，因為他是我的玫瑰。"(CX,X,H)
9. 狐狸告訴小王子"當你遇見無可取代的人，請用盡一輩子的時間與力氣去愛。"(H+X)

## Looking for feedbacks!
Simple as it firstly looks like, the rule and map of this game have been tested and modified extensively to balance and improve playing experience. From the amount of gates on the map, various fortune/chance cards serve as useful (and sometimes surprise!) tools to assist competition, and also the winning condition of rose scores are carefully chosen after our thorough tests. This game is, nevertheless, still under testing and we would like to hear everyone's comment to make it more fun and even competitive. Please try it out and give us some thoughts/feedbacks!

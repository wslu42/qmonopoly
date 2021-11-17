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
The players are going to collect quantum logic gates (X, H, CX gates) from the monopoly-like game map to put together some quantum circuits which generate the given challenge quantum state set (|000> + |011>, for example). The player will be rewarded with a rose when solved a challenge, and the first player who collected 10 roses will be the winner!

## Procedure:

### Preparation phase
- The host assigns one challenge question (a combination 1 or 2 of quantum states can be obtained from 3-qubit quantum circuits) to each player
- Each player decide one integer between 1-8 as their passcode to the greenhouse. Be aware that other player can guess your number by putting together a quantum circuit generate the binary state maps to your number. (For example, if a player uses X gate on qubit two and generate 010, that means he/she "guess" your passcode to be "3" (we started from 1 instead of 0 in the passcode)
- Each player picks one token and decide the playing sequence (from the youngest to the oldest), and the host arrange the sequence of the token by the map accordingly as a reminder.

### Main game phase
After the preparation phase, the main game phase follows and all players proceed in turns. During each turn a player will:
1. Throw a 8-faced plain dice or initiate remote dice to use his/her gates to go to projected spots based on the measurement of his/her quantum circuit.
2. Interact with the map depends on the spot landed
- The Gate spot: Collect corresponding gates. If there's a x2 then got doubled gates. If the player is in superpositioned/entangled states then he/she may collect all gates based on the spots that he/she landed on.
- The "Fortune/Chance" spot: Activate Fortune/Chance mode and draw one card from the corresponding deck. Some Chance cards may be saved to be used later in the game. There is no limitation in how many chance cards may be used during each turn, and players may activate a card at any moment during the game as long as it's his/her turn.
- The Stair spot: Activate storymode and draw one story card from the deck, the story mode rewards gates immediately to the player once the card is drawn.
3. Propose one quantum circuit solution to the given challenge and get one rose as a reward. Can only solve one challenge per turn.
4. Decide how many roses to be stored into or move out from greenhouse. The number of roses in greenhouse are counted as x1.2 times during the end of his/her turn due to getting better care. (note: the factor only counted once during the turn and do not stack between turns - i.e. if a player has 10 roses in greenhouse and stay for two turns, then the number counted as 12 roses throughout the turns instead of 12 in the first turn and 14 in the second turn.) Rose counts follows four-in-five rule.
5. Decide if he/she want to break the lock to other player's greenhouse by submitting up to two quantum circuits to the host. If the lock-picking is successful then he/she can steal 70% of the roses in the greenhouse. (steal counts follows four-in-five rule) No roses outside of the greenhouse can be stolen.

### Winning condition
During the end of each player's turn, apply the greenhouse factor (x1.2) and count all roses the current player has. If the rose count is greater or equal to 10 roses (after four-in-five rule applied) the player wins. If not, continue to the next player.

### Add-on explanations
1. How the dice work:
- A plain dice: a simple random 8-faced dice.
- Remote dice: Player are allow to use gates from their hand in a 3-qubits circuit to project themselves to up to 2 particular spots (the ones closest to the player) predicted by the measurement results. For example if the user puts an H gate at qubit 0 and CX target at qubit 1 and control at qubit 0, then he/she can move to two spots which are 1 and 4 steps away from his/her current location (we started from 1 instead of 0 after translate binary to decimal numbers. For example 000 gives 1 while 011 gives 4) The player will then be able to perform up to two interactions as described in the second step during the main game phase during the same turn (collect two types of gates/draw a card and collect a gate etc).  
2. How the greenhouse lock (and lock-picking) works
- At the preparation phase, every player will decide their own passcode and let the host know (an integer between 1 to 8) to protect their greenhouse.
- During each player's turn, he/she can guess one opponent's passcode by putting together up to two quantum circuits which generate the binary state maps to the passcode. (For example, if a player uses X gate on qubit two and generate 010, that means he/she "guess" the opponent's passcode to be "3" (we started from 1 instead of 0 in the passcode)
- If the guess matches the passcode, the player successfully break the code can move 70% (steal counts follows four-in-five rule) of the roses from the opponent's greenhouse to his own. The roses stolen from that turn will remain outside of the new owner's greenhouse.
- As long as a player attempts to break passcodes, he/she will skip his/her next turn.

### Cards at a glance

#### Fortune cards
- “Only the children know what they are looking for.", go to the nearest “X” gate (either forward or backward, up to the player)
- “You're not a man, you're a mushroom!”, go to the nearest “X” gate (either forward or backward, up to the player)
- “The thing that is important is the thing that is not seen.”, go to the nearest “H” gate (either forward or backward, up to the player)
- “The house, the stars, the desert -- what gives them their beauty is something that is invisible!”, go to the nearest “H” gate (either forward or backward, up to the player)
- “What does tamed mean? It's something that's been too often neglected. It means to create ties.” go to the nearest “CX” gate (either forward or backward, up to the player) x2
- “Sometimes, there is no harm in putting off a piece of work until another day.”, take a break for one turn.
- “Straight ahead you can't go very far.” Fell down on the way and backward three spots
- Unexpected surge of signal crosstalks and reduce the number of each gates on hand by one for the player.

#### Chance cards
- "SWAP card": Change the challenge question (can be saved for later use)
- "RESET card": Meet the pilot and take his plane back to “GO” on the map (can be saved for later use)
- “ANGEL card” Can choose any one gate you want and add to your hand, all player also get one as well (can be saved for later use)
- “WISH card” Can move to any one spot on the map as you wish
- “BOSS card” For a certain type of gate, you can get two-thirds of the number of that gate within all players' hands. (gate count follows four-in-five rule; can be saved for later use)
- “REWARD card” Won first place during a rose beauty pageant and collect double gates for one round whenever the player gets reward (can be saved for later use)
- “STEERING card” Reverse the order of players (can be saved for later use)
- “SNATCH card” Steal one type of gate from one other player's hand (the target player will be left with none of that type of gates; can be saved for later use)

#### Story cards
- “All grown-ups were once children... but only few of them remember it.” (Reward: 3 X gates)
- “You see, one loves the sunset when one is so sad.” (Reward: 3 X gates)
- “If you love a flower that lives on a star, it is sweet to look at the sky at night. All the stars are a-bloom with flowers...” (Reward: 1 X and 1 H gates)
- “In one of the stars I shall be living. In one of them I shall be laughing...You - only you - will have stars that can laugh.” (Reward: 1 X and 1 H gates)
- “But eyes are blind. You have to look with the heart.”(Reward: 3 H gates)
- “The most beautiful things in the world cannot be seen or touched, they are felt with the heart.” (Reward: 1 X, 1 H, and 1 CX gates)
- “The only things you learn are the things you tame” (Reward: 1 H, and 1 CX gates)
- “But in herself alone she is more important than all the hundreds of you other roses... Because she is my rose.” (Reward: 1 X, and 1 CX gates)
- “It is the time you have wasted for your rose that makes your rose so important.” (Reward: 1 X, 1 H, and 1 CX gates)

## Looking for feedbacks!
Simple as it firstly looks like, the rule and map of this game have been tested and modified extensively to balance and improve playing experience. From the amount of gates on the map, various fortune/chance cards serve as useful (and sometimes surprise!) tools to assist competition, and also the winning condition of rose scores are carefully chosen after our thorough tests. This game is, nevertheless, still under testing and we would like to hear everyone's comment to make it more fun and even competitive. Please try it out and give us some thoughts/feedbacks!

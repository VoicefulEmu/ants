# ants
see https://cs111.byu.edu/proj/ants/ for more information

## Problem 12 (3 pt)
Finally, implement the QueenAnt. The queen is a waterproof ScubaThrower that inspires her fellow ants through her bravery. In addition to the standard ScubaThrower action, the QueenAnt doubles the damage of all the ants behind her each time she performs an action. Once an ant’s damage has been doubled, it is not doubled again for subsequent turns.

FOod cost = 7

Init health = 1

## However, with great power comes great responsibility. The QueenAnt is governed by three special rules:

1) If the queen ever has its health reduced to 0, the ants lose. You will need to override Ant.reduce_health in QueenAnt and call ants_lose() in that case in order to signal to the simulator that the game is over. (The ants also still lose if any bee reaches the end of a tunnel.)

2) There can be only one queen. A second queen cannot be constructed. To check if an Ant can be constructed, we use the Ant.construct() class method to either construct an Ant if possible, or return None if not. You will need to override Ant.construct as a class method of QueenAnt in order to add this check. To keep track of whether a queen has already been created, you can use an instance variable added to the current GameState.

3) The queen cannot be removed. Attempts to remove the queen should have no effect (but should not cause an error). You will need to override Ant.remove_from in QueenAnt to enforce this condition.
Hint: Think about how you can call the construct method of the superclass of QueenAnt. Remember that you ultimately want to construct a QueenAnt, not a regular Ant or a ScubaThrower.

Hint: You can find each Place in a tunnel behind the QueenAnt by starting at the ant’s place.exit and then repeatedly following its exit. The exit of a Place at the end of a tunnel is None.

Hint: To avoid doubling an ant’s damage twice, mark the ants that have been buffed in some way, in a way that persists across calls to QueenAnt.action.

Hint: When buffing the ants’ damage, keep in mind that there can be more than one ant in a Place, such as if one ant is guarding another.

After writing code, test your implementation:

python3 ok -q 12

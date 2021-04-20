# reinforcementlearning
## The problem
The Wumpus world is a well-known toy problem in artificial intelligence popularized by the reference book of Russell and Norvig, 2003. The game consists in a grid world where an agent is looking for a treasure while avoiding the deadly Wumpus and some holes. We assume that the time is discretized and that the agent can take only one action per time step. The agent can explore the grid by moving in the four cardinal directions. Also, it has a flashlight with a limited number of power units that can be used to kill the Wumpus. For the project, the Wumpus world will be our benchmark problem for studying reinforcement learning (RL) algorithms. Moreover, these algorithms are general enough to be applied to different problems (environment).

## Explanation

In the RL framework, we define an environment, which specifies the information to be used by the agent to take some actions. For the Wumpus world, the environment is partially observable since the locations of the holes, the Wumpus and the treasure are unknown to the agent. However, the environment provides some signals to the agent:

* if the agent is adjacent to the Wumpus, it receives a _smell_ signal
* if the agent is adjacent to the hole, it receives a _breeze_ signal
* the location of the agent is _deterministically_ determined by the initial position and the actions
* the number of _power units_ is known

## Code structure

The only files we have action on are: agent.py and main.py.

1 - agent.py:

This one is the file containing the strategy.

2 - main.py:

This one is the program that will actually run the agent.
You can run it with the command:
```python
python main.py
```

It also accepts a few command-line arguments:

* --ngames N will run the agent for N games against in the same environment (the same initial grid setup) and report the total cumulative reward
* --niter N maximum number of iterations allowed for each game
* --batch B will run B instances of the game (B different Wumpus worlds, i.e. with the same rules but different initial grid setups)
* --verbose will print details at each step of what your agent did. In particular, it will show in ASCII art its current location on the grid as well as the one of the Wumpus (which is moving).

The running of your agent follows a general procedure that will be shared for all later practicals:
* The environment generates an observation
* This observation is provided to your agent via the act method which chooses an action

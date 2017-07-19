# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propagation is a technique used to solve a problem by cumulatively adding
   several constraints to a known problem, and therefore chaining their effects together
   until that problem is solved.
   With the naked twins problem, this is achieved by finding two peers on a sudoku board
   that both have two possible values that are exactly the same. Since these two peers have 
   the same possible values, those values cannot exist in any of their shared peers, so those
   values are removed from the twins' shared peers. Once this has occured the state of the
   sudoku board has changed and is closer to a solution. Now, the naked peers technique
   can be applied once again. The technique can be chained with itself and with other
   techniques, such as elimination and only choice, to further apply cumulative constraints
   upon the sudoku board.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: The diagonal sudoku problem is similar to a normal sudoku board, except that there
   are two additional, diagonal units added. These units must pass the same constraints
   as all other units: each one of the digits 1-9 must be present in the unit with no
   repetitions.
   This problem is solved by repeatedly applying techniques such as elimination, only choice,
   and naked twins to the entire board. Since the diagonal units share its units with other
   sets of units on the board, any information gained on any part of the board can
   potentially help to solve the diagonal units. This is what allows constraint
   propagation to occur in this case; solutions to non-diagonal units can prove helpful
   in solving the puzzle when combined with additional contraints.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the `assign_value` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login) for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.


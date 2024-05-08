# FindMyPath - Multi Agent Pathfinding for Large Agents


This project contains multiple solvers for the Multi-Agent Path Finding problem with large size (2x2 and 3x3) agents. Essentially, this means that the code in this repository allows the user to plan and visualize the movement of agents in such a manner that they find their way to their destinations without colliding with each other, while still taking as short of a path as possible.
Additionally, agents can be of varying sizes, up to a size that takes up an area of 3x3 spaces on a grid.


## Execution

These solvers are implemented inside `code/code/mccbs.py` and can be invoked from the command line with:

`python run_experiments.py`

With a number of arguments.

**Required Arguments:**\
`--instance <file_path/file_name>` Specify the instance to attempt to solve.\
`--solver <solver_name> (Options: MCCBS, Prioritized)` Specify which solver to use.

**Optional Arguments:**\
`--batch` Run the solver against a batch of instances. Incompatible with Prioritized Planning.\
`--splitter <splitter_name> (Options: standard, disjoint, symmetrical, asymmetrical)` Choose the splitting strategy to use. Defaults to `standard` if omitted.\
`--maxnodes <max_number_of_generated_nodes>` Choose a number of generated nodes at which to stop the solver. If omitted, will run until a solution is found or the computer runs out of memory.


It also contains a suite of instances for benchmarking the solvers, located inside `/code/code/benchmarking/`.

Some extra hard instances can also be found in `/code/code/benchmarking/hard/`

For example, to invoke the MCCBS solver with symmetrical splitting on the set of benchmarking instances and a limit of 500,000 generated nodes run:\
`cd code`\
`cd code`\
`python run_experiments.py --instance "benchmarking/inst_*" --solver MCCBS --splitter symmetrical --batch --maxnodes 500000`

The results of the solver are found in `/code/code/mccbs_<splitter_name>_results.csv`.

An example of the results of previous runs with various solvers can be found inside `data/`.

Thanks for reading!

Basic Explanation: -
In the natural world, ants of some species (initially) wander randomly, and upon finding food return to their colony while laying down pheromone trails. If other ants find such a path, they are likely not to keep travelling at random, but instead to follow the trail, returning and reinforcing it if they eventually find food.
Over time, however, the pheromone trail starts to evaporate, thus reducing its attractive strength. The more time it takes for an ant to travel down the path and back again, the more time the pheromones have to evaporate. A short path, by comparison, gets marched over more frequently, and thus the pheromone density becomes higher on shorter paths than longer ones. Pheromone evaporation also has the advantage of avoiding the convergence to a locally optimal solution. If there were no evaporation at all, the paths chosen by the first ants would tend to be excessively attractive to the following ones. In that case, the exploration of the solution space would be constrained. The influence of pheromone evaporation in real ant systems is unclear, but it is very important in artificial systems.
The overall result is that when one ant finds a good (i.e., short) path from the colony to a food source, other ants are more likely to follow that path, and positive feedback eventually leads to many ants following a single path. The idea of the ant colony algorithm is to mimic this behaviour with "simulated ants" walking around the graph representing the problem to solve.
Given an n-city TSP with distances dij , the artificial ants are distributed to these n cities
randomly. Each ant will choose the next to visit according to the pheromone trail remained on the paths just as mentioned in the above example. However, there are two main differences between artificial ants and real ants: (1) the artificial ants have “memory”; they can remember the cities they have visited and therefore they would not select those cities again. (2) The artificial ants are not completely “blind”; they know the distances between two cities and prefer to choose the nearby cities from their positions. Therefore, the probability that city j is selected by ant k to be visited after city i could be written as follows:
 
where τij the influence of τij is the intensity of pheromone trail between cities i and j, α the parameter to regulate , ηij the visibility of city j from city i, which is always set as 1/dij (dij distance between city i and j), β the parameter to regulate the influence of ηij set of cities that have not been visited yet, respectively.
At the beginning, l ants are placed to the n cities randomly. Then each ant decides the next city to be visited according to the probability pijk given by Eq. (1). After n iterations of this process, every ant completes a tour. Obviously, the ants with shorter tours should leave more pheromone than those with longer tours. Therefore, the trail levels are updated as on a tour each ant leaves pheromone quantity given by Q/Lk, where Q is a constant and Lk the length of its tour, respectively. On the other hand, the pheromone will evaporate as the time goes by. Then the updating rule of τij could be written as follows:
 
where t is the iteration counter, ρ ϵ [0, 1] the parameter to regulate the reduction of τij , Δτij the total increase of trail level on edge (i, j) and Δτijk the increase of trail level on edge (i, j) caused by ant k, respectively. After the pheromone trail updating process, the next iteration t + 1 will start.

Base Papers:
• An ant colony optimization method for generalized TSP problem 
Jinhui Yang a, Xiaohu Shi a, Maurizio Marchese b, Yanchun Liang a,*
• Ant colony optimization for real-world vehicle routing problems From theory to applications 
A.E. Rizzoli, · R. Montemanni · E. Lucibello · L.M. Gambardella

# ant-colony-tsp
Solve TSP using Ant Colony Optimization in Python 3

### Requirements
* Python3
* matplotlib

### Usage
Run `main.py` to see the results.
Run 'plot.py' to see the graph

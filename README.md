# Algorithm (QUIZ 6)

---

# Option 1: Min Cost to Connect All Points

### Algorithm Used:

Prim’s Algorithm (Minimum Spanning Tree)

### Explanation:

This problem asks us to connect all points with the minimum total cost. The cost between two points is calculated using Manhattan Distance.

The code uses Prim’s Algorithm. We start from one point and repeatedly connect the nearest unvisited point. The `minDist` array stores the minimum cost needed to connect each point, while the `visited` array checks whether a point has already been connected.
At every step, the algorithm:
--Finds the unvisited point with the smallest connection cost.
--Adds that cost to the final answer.
--Updates the minimum distances of neighboring points.
     This process continues untill all points are connected.
### Time Complexity:
O(n²)
Because for every point, the algorithm checks all other points to find the minimum connection cost. Since there are two nested loops running up to n times, the total operations become proportional to n squared.


# Option 2: Cheapest Flights Within K Stops

### Algorithm Used:

Bellman-Ford Algorithm

### Explanation:

This problem asks us to find the cheapest flight price from a source city to a destination city with at most `k` stops.
The code uses the Bellman-Ford Algorithm. We store the cheapest price to each city in a `price` array. 
Initially, all cities are unreachable except the source city.
The algorithm relaxes all flights `k + 1` times because:
   `k` stops means at most `k + 1` flights.
A temporary array is used so that updates from the current round do not affect calculations in the same iteration.

And, at every step, the algorithm:
--Checks every flight.
--Determines whether a cheaper path exists.
--Updates the cheapest price if a better route is found.

If the destination cannot be reached, the code returns `-1`.

### Time Complexity:

O(k × flights)
Because because the algorithm repeats the relaxation process k + 1 times, and during each iteration it checks every flight once. Therefore, the total work depends on the number of flights multiplied by the number of allowed stops.


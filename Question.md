# [2257. Count Unguarded Cells in the Grid](https://leetcode.com/problems/count-unguarded-cells-in-the-grid)

__Type:__ Medium <br>
__Topics:__ Array, Matrix, Simulation <br>
__Companies:__ Poshmark
<hr>

You are given two integers `m` and `n` representing a **0-indexed** `m x n` grid. You are also given two 2D integer arrays `guards` and `walls` where <code>guards[i] = [row<sub>i</sub>, col<sub>i</sub>]</code> and <code>walls[j] = [row<sub>j</sub>, col<sub>j</sub>]</code> represent the positions of the <code>i<sup>th</sup></code> guard and <code>j<sup>th</sup></code> wall respectively.

A guard can see **every** cell in the four cardinal directions (north, east, south, or west) starting from their position unless **obstructed** by a wall or another guard. A cell is **guarded** if there is **at least** one guard that can see it.

Return _the number of unoccupied cells that are **not guarded**_.
<hr>

### Examples:

- **Example 1:** <br>
![](https://assets.leetcode.com/uploads/2022/03/10/example1drawio2.png) <br>
**Input:** m = 4, n = 6, guards = [[0,0],[1,1],[2,3]], walls = [[0,1],[2,2],[1,4]] <br>
**Output:** 7 <br>
**Explanation:** The guarded and unguarded cells are shown in red and green respectively in the above diagram. <br>
There are a total of 7 unguarded cells, so we return 7.

- **Example 2:** <br>
![](https://assets.leetcode.com/uploads/2022/03/10/example2drawio.png) <br>
**Input:** m = 3, n = 3, guards = [[1,1]], walls = [[0,1],[1,0],[2,1],[1,2]] <br>
**Output:** 4 <br>
**Explanation:** The unguarded cells are shown in green in the above diagram. <br>
There are a total of 4 unguarded cells, so we return 4.
<hr>

### Constraints:
- <code>1 <= m, n <= 10<sup>5</sup></code>
- <code>2 <= m * n <= 10<sup>5</sup></code>
- <code>1 <= guards.length, walls.length <= 5 * 10<sup>4</sup></code>
- <code>2 <= guards.length + walls.length <= m * n</code>
- <code>guards[i].length == walls[j].length == 2</code>
- <code>0 <= row<sub>i</sub>, row<sub>j</sub> < m</code>
<hr>

### Hints:
- Create a 2D array to represent the grid. Can you mark the tiles that can be seen by a guard?
- Iterate over the guards, and for each of the 4 directions, advance the current tile and mark the tile. When should you stop advancing?
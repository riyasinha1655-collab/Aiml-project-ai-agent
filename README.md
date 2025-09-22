# Autonomous Delivery Agent

This project is about designing a simple autonomous delivery agent that navigates a 2D grid city to deliver packages.
The agent must avoid obstacles, handle different terrain costs, and even replan if something blocks its path.

>>Features

-> Environment:

    Grid-based map.

    Obstacles (-1 = wall).

    Terrain cost (1 = normal road, 2+ = slower road).

-> Algorithms Implemented:

  1. BFS → Basic uninformed search (all roads same cost).

  2. Uniform Cost Search (UCS) → Like Dijkstra, considers road costs.

  3. A* → Best balance (road cost + heuristic).

  4. ill Climbing → Local search (not always optimal, but fun to test).

  5. Dynamic replanning → If a new obstacle appears, agent replans the path.

-> Agent Movement:

    Moves up, down, left, right (4-connected).

🛠 Requirements

Python 3.x

No extra libraries needed (only heapq, random, time, all built-in).

▶ How to Run

1. Open Google Colab or your terminal.

2. Copy the code from main.py (or notebook cell).

3. Run it, and see the output :
BFS path: [(0,0), (0,1), ... , (3,5)]
UCS path: [(0,0), (1,0), ... , (3,5)]
A* path:  [(0,0), (0,1), ... , (3,5)]
Hill Climbing path: [(0,0), (0,1), (1,1), ...]
--- Dynamic replanning ---
Initial path: [...]
New obstacle appeared at: (2,3)
Replanned path: [...]
 
🗺 Test Maps

We can edit the city variables to test different maps.

Small Map
city = [
    [1, 1, 1],
    [1, -1, 1],
    [1, 1, 1]
]
Medium Map
city = [
    [1, 1, 1, 1, -1, 1],
    [1, -1, 2, 1, -1, 1],
    [1,  1, 2, 1,  1, 1],
    [1,  1, 1, 1, -1, 1]
]

Large Map
city = [
    [1,1,1,1,1,1,1,1,1,1],
    [1,-1,-1,1,2,2,1,-1,1,1],
    [1,1,1,1,1,-1,1,1,1,1],
    [1,2,2,2,1,-1,1,2,2,1],
    [1,1,1,1,1,1,1,1,1,1]
]

Dynamic Map {for replanning}
city = [
    [1,1,1,1],
    [1,1,-1,1],
    [1,1,1,1],
    [1,1,1,1]
]

📊 Experimental Notes

- BFS is fast but ignores road costs.

- UCS finds cheaper routes but can expand many nodes.

- A* is usually the most efficient (best path with fewer expansions).

- Hill Climbing sometimes gets stuck (not reliable but shows local search).

- Dynamic replanning works with A* (if new obstacle shows up, it recalculates).

🎥 Demo

You can run the dynamic_demo() function to see how the agent replans when an obstacle suddenly appears.

Example output is printed in the console.

📚 Author Notes

This project is made for learning AI search algorithms in a fun way using a delivery agent.
Code is kept simple and in a readable form, more like an student project than an industrial one.

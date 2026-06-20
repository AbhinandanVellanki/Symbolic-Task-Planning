# HW3 — Symbolic Task Planning

A STRIPS-style symbolic planner that searches over robot/object predicate states (room location, "chopped", "on robot", etc.) to find a plan from an initial state to a goal state. Assignment for 16-662 (Robot Autonomy), CMU.

## Contents

- `SymDiscreteSearch.py` — the entire implementation:
  - `InitializePreconditionsAndEffects` defines the action set (move between rooms, move to/from the pantry, cut fruit, pick up/drop objects, etc.) as precondition/effect matrices over `Predicates x Objects`.
  - `InitializeStateAndGoal` defines the initial world state and the goal state (e.g. strawberry chopped and in the kitchen, lemon in the garden).
  - `Heuristic` scores how close a state is to the goal, for use as an A* heuristic (currently the search runs as Dijkstra, with the A* line commented out).
  - The bottom of the file runs a priority-queue graph search (`heapq`) over the state space, reconstructs the parent chain, and prints the resulting action plan.
- `HW3.pdf` — assignment spec.
- `abhinanv_HW3.pdf` / `.docx` — submitted write-up.

## Running

```bash
pip install numpy
python SymDiscreteSearch.py
```

Prints the number of states explored, the plan length, and the ordered list of actions (`ActionDesc`) that reach the goal.

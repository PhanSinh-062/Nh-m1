### 1. Chạy chấm điểm toàn bộ câu hỏi (Q1 đến Q8)
```bash
python autograder.py
```
> Kết quả đạt tối đa: **26/25** điểm (bao gồm cả điểm thưởng cho câu Q7).

---

### 2. Chạy chấm điểm từng câu riêng lẻ

* **Q1 (3 pts) - Depth First Search (DFS)**:
  ```bash
  python autograder.py -q q1
  ```

* **Q2 (3 pts) - Breadth First Search (BFS)**:
  ```bash
  python autograder.py -q q2
  ```

* **Q3 (3 pts) - Uniform Cost Search (UCS)**:
  ```bash
  python autograder.py -q q3
  ```

* **Q4 (3 pts) - A* Search**:
  ```bash
  python autograder.py -q q4
  ```

* **Q5 (3 pts) - Finding All the Corners (CornersProblem)**:
  ```bash
  python autograder.py -q q5
  ```

* **Q6 (3 pts) - Corners Problem Heuristic**:
  ```bash
  python autograder.py -q q6
  ```

* **Q7 (4 pts + 1 bonus) - Eating All The Dots (Food Heuristic)**:
  ```bash
  python autograder.py -q q7
  ```

* **Q8 (3 pts) - Suboptimal Food Search (Closest Dot Search)**:
  ```bash
  python autograder.py -q q8
  ```

### 3. Chạy một bài test cụ thể

## 🎮 Các câu lệnh xem giao diện đồ họa Pacman di chuyển (GUI)

Để quan sát Pacman tìm đường và di chuyển trực tiếp trên bản đồ:

### Q1: Depth First Search (DFS)
```bash
python pacman.py -l tinyMaze -p SearchAgent -a fn=tinyMazeSearch
python pacman.py -l mediumMaze -p SearchAgent -a fn=depthFirstSearch
python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=depthFirstSearch
```

### Q2: Breadth First Search (BFS)
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=breadthFirstSearch
python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=breadthFirstSearch
```

### Q3: Uniform Cost Search (UCS)
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs
python pacman.py -l mediumScaryMaze -p StayWestSearchAgent
```

### Q4: A* Search
```bash
python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
```

### Q5: Finding All the Corners (BFS)
```bash
python pacman.py -l tinyCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
```

### Q6: Corners Problem Heuristic (A*)
```bash
python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.8
```

### Q7: Eating All The Dots (A* với Food Heuristic)
```bash
python pacman.py -l testSearch -p AStarFoodSearchAgent
python pacman.py -l trickySearch -p AStarFoodSearchAgent
```

### Q8: Closest Dot Search Agent
```bash
python pacman.py -l bigSearch -p ClosestDotSearchAgent -z .5
```

### Tự chơi thủ công bằng phím mũi tên:
```bash
python pacman.py
```


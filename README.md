# Multi_Agent_Search
### 1. Chạy chấm điểm toàn bộ câu hỏi (Q1 đến Q5)
```bash
python autograder.py
```
> Kết quả đạt tối đa: **25/25** điểm.

---

### 2. Chạy chấm điểm từng câu riêng lẻ

* **Q1 (4 pts) - Reflex Agent**:
  ```bash
  python autograder.py -q q1
  ```

* **Q2 (5 pts) - Minimax**:
  ```bash
  python autograder.py -q q2
  ```

* **Q3 (5 pts) - Alpha-Beta Pruning**:
  ```bash
  python autograder.py -q q3
  ```

* **Q4 (5 pts) - Expectimax**:
  ```bash
  python autograder.py -q q4
  ```

* **Q5 (6 pts) - Evaluation Function (betterEvaluationFunction)**:
  ```bash
  python autograder.py -q q5
  ```

### 3. Chạy một bài test cụ thể

Mỗi câu gồm nhiều test nằm trong `test_cases/qN/`. Để chạy riêng một test (hữu ích khi tìm lỗi), dùng tham số `-t` với đường dẫn test **không có đuôi `.test`**:

```bash
python autograder.py -t test_cases/q2/0-small-tree
python autograder.py -t test_cases/q4/0-expectimax1
```

Thêm `--no-graphics` để chấm mà không hiện cửa sổ game:

```bash
python autograder.py -q q2 --no-graphics
```

Dùng `-p` (`--print-tests`) để in nội dung từng test trước khi chạy:

```bash
python autograder.py -q q2 -p
```

Kết quả `*** PASS` nghĩa là test đạt, `*** FAIL` nghĩa là test không đạt, kèm thông tin để đối chiếu.

### 4. Xem Pacman chạy bằng giao diện đồ họa (GUI)

Để quan sát Pacman tự di chuyển trên bản đồ, dùng `-p` để chọn agent, `-l` để chọn bản đồ, `-a` để truyền tham số (ví dụ `depth=3`, không có khoảng trắng sau dấu phẩy):

#### Q1: Reflex Agent
```bash
python pacman.py -p ReflexAgent -l testClassic
python pacman.py -p ReflexAgent -k 1 -l openClassic
python pacman.py -p ReflexAgent -k 2 -l mediumClassic
```
`-k 1` hoặc `-k 2` là số lượng ma. Agent chỉ nhìn 1 bước nên chơi tốt trên bản đồ thoáng (`openClassic`) và yếu hơn khi nhiều ma (`mediumClassic`).

#### Q2: Minimax
```bash
python pacman.py -p MinimaxAgent -l minimaxClassic -a depth=4
python pacman.py -p MinimaxAgent -l trappedClassic -a depth=3
```
`depth` là số mức nhìn trước (một mức gồm một lượt của Pacman và lượt của tất cả ma). Depth càng lớn thì Pacman nghĩ càng xa nhưng càng chậm, nên có thể đứng yên vài giây giữa các nước đi. Trên `trappedClassic`, Minimax luôn chọn tự sát vì giả định ma chơi hoàn hảo.

#### Q3: Alpha-Beta Pruning
```bash
python pacman.py -p AlphaBetaAgent -l smallClassic -a depth=3
python pacman.py -p AlphaBetaAgent -l minimaxClassic -a depth=4
```
Cho kết quả như Minimax nhưng chạy nhanh hơn nhờ cắt tỉa các nhánh không cần xét.

#### Q4: Expectimax
```bash
python pacman.py -p ExpectimaxAgent -l minimaxClassic -a depth=3
python pacman.py -p ExpectimaxAgent -l trappedClassic -a depth=3
```
Coi ma đi ngẫu nhiên đều nên tầng ma lấy trung bình thay vì lấy giá trị nhỏ nhất. Trên `trappedClassic`, Expectimax có thể thoát, khác với Minimax.

#### Q5: Hàm đánh giá tốt hơn
```bash
python pacman.py -p ExpectimaxAgent -l smallClassic -a evalFn=better,depth=2
```
`evalFn=better` bảo agent dùng `betterEvaluationFunction` thay cho hàm điểm mặc định.

#### Chạy nhiều ván, không hiện đồ họa (để lấy số liệu)
```bash
python pacman.py -p AlphaBetaAgent -l smallClassic -a depth=3 -n 10 -q -f
```
* `-n 10`: chạy 10 ván liên tiếp.
* `-q`: không hiện đồ họa, chỉ in điểm trung bình và tỉ lệ thắng.
* `-f`: cố định ngẫu nhiên, để các lần chạy cho kết quả giống nhau.

#### Tự chơi thủ công bằng phím mũi tên:
```bash
python pacman.py
```
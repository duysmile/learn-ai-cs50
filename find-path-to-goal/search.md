# Search algorithms

Link: https://cs50.harvard.edu/ai/2020/weeks/0/

### Uninformed Search
- Search mà không quan tâm đến những thông tin của vấn đề
1. Depth first search (DFS):

- Tìm sâu nhất có thể, có thể dùng stack để implement
- Có thể đường đi tìm được không tối ưu
- Example: `class StackFrontier`
- Kết quả:
    - 11 steps với maze1.txt
    - 194 steps với maze2.txt
    - 17 steps với maze3.txt

2. Breadth first search (BFS)

- Tìm rộng nhất có thể, có thể dùng queue để implement
- Đường đi tìm được sẽ tối ưu nhưng chi phí để tìm sẽ cao
- Example: `class QueueFrontier`
- Kết quả
    - 11 steps với maze1.txt
    - 77 steps với maze2.txt
    - 6 steps với maze3.txt

### Informed Search
- Search dựa trên thông tin liên quan đến vấn đề

1. Greedy best-first search

- Xây dựng một hàm h(x) - heuristic function để ước lượng khoảng cách từ vị trí hiện tại tới đích là bao nhiêu (giá trị này chỉ là tương đối, không đảm bảo là giá trị chính xác khoảng cách từ node -> đích), và ưu tiên tìm dựa trên những node có giá trị h(x) nhỏ trước - tương ứng với node mà ta cho là gần đích.
- Đường đi có thể không tối ưu vì h(x) có thể có sai sô.
- Chi phí có thể giảm so với việc search không có thông tin, vì `h(x)` cho chúng ta cơ sở để tìm đường tốt hơn.
- Example: `class PriorityFrontier`
- Kết quả
    - 11 steps với maze1.txt
    - 54 steps với maze2.txt
    - 5 steps với maze3.txt
    - 34 steps với maze3.txt (không tối ưu)

2. A* search
- Vì thuật toán GBFS dựa vào hàm heuristic nên trong trường hợp `maze4.txt` nó sẽ không tìm được đường đi tối ưu, đó là lí do thuật toán A* ra đời
- A* sử dụng nguyên lí là tính toán cost để đi đến điểm hiện tại, và giá trị ước tính tới đích để làm trọng số, do đó trong trường hợp này A* sẽ luôn tìm được đường đi tối ưu nhất
- Về mặt toán học thì ta sẽ dựa vào tổng 2 giá trị sau để xác định nên chọn điểm nào để đi tiếp theo:
    - `g(n)`: cost để đến được 1 node
    - `h(n)`: estimate từ node tới đích
- Example: `class AAsteriskFrontier`
- Kết quả
    - 11 steps với maze1.txt
    - 59 steps với maze2.txt
    - 5 steps với maze3.txt
    - 32 steps với maze4.txt

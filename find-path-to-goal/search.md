# Search algorithms

### Uninformed Search
- Search mà không quan tâm đến những thông tin của vấn đề
1. Depth first search (DFS)

- Tìm sâu nhất có thể, có thể dùng stack để implement
- Có thể đường đi tìm được không tối ưu
- Example: `class StackFrontier`

2. Breadth first search (BFS)

- Tìm rộng nhất có thể, có thể dùng queue để implement
- Đường đi tìm được sẽ tối ưu nhưng chi phí để tìm sẽ cao
- Example: `class QueueFrontier`

### Informed Search
- Search dựa trên thông tin liên quan đến vấn đề

1. Greedy best-first search

- Xây dựng một hàm h(x) - heuristic function để ước lượng khoảng cách từ vị trí hiện tại tới đích là bao nhiêu (giá trị này chỉ là tương đối, không đảm bảo là giá trị chính xác khoảng cách từ node -> đích), và ưu tiên tìm dựa trên những node có giá trị h(x) nhỏ trước - tương ứng với node mà ta cho là gần đích.
- Đường đi có thể không tối ưu vì h(x) có thể có sai sô.
- Chi phí có thể giảm so với việc search không có thông tin, vì `h(x)` cho chúng ta cơ sở để tìm đường tốt hơn.
- Example: `class PriorityFrontier`

2. A* search

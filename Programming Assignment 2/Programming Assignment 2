from collections import deque
import time



def bfs(graph, start, end):
    start_time = time.time()
    
    queue = deque([(start, [start], [])])  # Queue stores (node, path, edges) tuples
    visited = set()
    explored_nodes = set()
    paths = []
    
    while queue:
        node, path, edges = queue.popleft()
        
        if node == end:
            paths.append((path, edges))
            break  # Stop exploring once end_node is found
        
        visited.add(node)
        explored_nodes.add(node)
        
        for neighbor in graph[node]:
            if neighbor not in visited:
                new_path = path + [neighbor]
                new_edges = edges + [(node, neighbor)]
                queue.append((neighbor, new_path, new_edges))
                
    end_time = time.time()
    elapsed_time = (end_time - start_time) * 1000  # Convert to milliseconds
    
    return paths, explored_nodes, elapsed_time



def dfs(graph, start, end):
    start_time = time.time()
    
    stack = [(start, [start], [])]  # Stack stores (node, path, edges) tuples
    visited = set()
    explored_nodes = set()
    paths = []
    
    while stack:
        node, path, edges = stack.pop()
        
        if node == end:
            paths.append((path, edges))
            break  # Stop exploring once end_node is found
        
        visited.add(node)
        explored_nodes.add(node)
        
        for neighbor in graph[node]:
            if neighbor not in visited:
                new_path = path + [neighbor]
                new_edges = edges + [(node, neighbor)]
                stack.append((neighbor, new_path, new_edges))
                
    end_time = time.time()
    elapsed_time = (end_time - start_time) * 1000  # Convert to milliseconds
    
    return paths, explored_nodes, elapsed_time


# Function to build the graph
graph = {
    '0':['1'],
    '1':['0','2','6'],
    '2':['3','1'],
    '3':['2'],
    '4':['9'],
    '5':['10', '6'],
    '6':['5','7','1'],
    '7':['12', '6'],
    '8':['13', '9'],
    '9':['8', '4'],
    '10':['5','11','15'],
    '11':['10','16'],
    '12':['7','13','17'],
    '13':['12','8','14','18'],
    '14':['13'],
    '15':['10','20'],
    '16':['11'],
    '17':['12','22'],
    '18':['13','19'],
    '19':['18','24'],
    '20':['15','21'],
    '21':['20'],
    '22':['17','23'],
    '23':['22'],
    '24':['19']
}

#Print BFS Info
start_node = '0'
end_node = '24'

all_paths, explored_nodes, elapsed_time = bfs(graph, start_node, end_node)
if all_paths:
    print(f"Paths between {start_node} and {end_node} with BFS:")
    for path, edges in all_paths:
        print("Path:", ' -> '.join(path))
        print("Traversed Edges:")
        for edge in edges:
            print(edge)
        print()
    print("Explored Nodes with BFS:", explored_nodes)
    print("Elapsed Time with BFS (ms):", elapsed_time)
else:
    print(f"There is no path between {start_node} and {end_node}")

#Print DFS Info
start_node = '0'
end_node = '24'
all_paths, explored_nodes, elapsed_time = dfs(graph, start_node, end_node)
if all_paths:
    print(f"Paths between {start_node} and {end_node} with DFS:")
    for path, edges in all_paths:
        print("Path:", ' -> '.join(path))
        print("Traversed Edges:")
        for edge in edges:
            print(edge)
        print()
    print("Explored Nodes with DFS:", explored_nodes)
    print("Elapsed Time with DFS (ms):", elapsed_time)
else:
    print(f"There is no path between {start_node} and {end_node}")


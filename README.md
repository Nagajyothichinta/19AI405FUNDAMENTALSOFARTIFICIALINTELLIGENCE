### EXP01-Implement-Depth-First-Search-Traversal-of-a-Graph

### AIM:
To Implement Depth First Search Traversal of a Graph using Python

### THEORY:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. Step 1: Initially, stack and visited arrays are empty.

1.Queue and visited arrays are empty initially. Stack and visited arrays are empty initially.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/9fbc383c-9af6-46fa-9ae9-e52dc8f11d8d)
Queue and visited arrays are empty initially. Stack and visited arrays are empty initially.

Visit 0 and put its adjacent nodes which are not visited yet into the stack.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/ae974dfa-938d-46dc-8a70-fd6872be8cb4)
Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

3.Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/389e0b45-ba5e-4789-9266-71a33dab82f6)
Visit node 1 Visit node 1

Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/a985aebb-a235-4f8b-a70a-cb2728cbb9d8)
Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/eab35794-608a-4322-99e5-5fe2de3e4245)
Visit node 4 Visit node 4

6.Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/1aa26350-057d-49cb-b00d-1e29071ac93b)
Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

### ALGORITHM:
1.Construct a Graph with Nodes and Edges

2.Depth First Search Uses Stack and Recursion

3.Insert a START node to the STACK

4.Find its Successors Or neighbors and Check whether the node is visited or not

5.If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

### PROGRAM:
```
Name: Chintha Naga Jyothi
Regno:212221230015
```
```
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
### Sample Input:
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/f18c03cb-2b44-4ed6-a1fc-e6c5a5a53f80)

### Sample Output:
![image](https://github.com/Nagajyothichinta/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/94191344/49ec0787-823b-4d75-9498-8ba0634122be)

### RESULT:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.





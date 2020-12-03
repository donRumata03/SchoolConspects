# DFS
    def dfs(v):

        mark[v] = True
        for u in neighbors(v):
            if not mark[v]:
                dfs(u)

# Color adj components:
    component_number = 0

    def dfs(v):
        mark[v] = True
        for u in neighbors(v):
            if not mark[v]:
                dfs(u)
        component[v] = component_number
    
    for v in all_vertexes:
        if not mark[v]:
            dfs(v)
            component_number += 1 // It`s the index of the component at the moment, but in the end it's equal to the total number of components


# The time of entrance and exit (time is a metaphor)

    def dfs(v):
        times_in[v] = time
        time += 1        
    
        mark[v] = True
        for u in neighbors(v):
            if not mark[v]:
                dfs(u)

        times_in[v] = time
        time += 1        

# Solving task about being parent using the above algorithm

# Topological sort

We have a set of rules about pairs of vertexes which state which one should be situated in the path before the other.
Run DFS with timing, then sort by exiting time.
If there are no cycles, the problem hasn't any solutions. However, using this algorithm, we'll get some answer. To verify it, we should check all the edges if their direction is appropriate or not.

# Checking if there are some cycles:
Mark vertexes as:
- Have never been there  (white)
- Is in the call stack   (grey)
- Has come out from them (black)

Cycle if came to grey vertex
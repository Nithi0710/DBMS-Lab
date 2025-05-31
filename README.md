# DBMS-Lab

def floyd_warshall(dist):
    n = len(dist)
    d = [row[:] for row in dist]

    for k in range(n):
        for i in range(n):
            for j in range(n):
                if d[i][k] + d[k][j] < d[i][j]:
                    d[i][j] = d[i][k] + d[k][j]
    return d
INF = float('inf')
dist_matrix = [
    [0,   3,   INF, 7],
    [8,   0,   2,   INF],
    [5,   INF, 0,   1],
    [2,   INF, INF, 0]
]
shortest = floyd_warshall(dist_matrix)
for row in shortest:
    print(row)
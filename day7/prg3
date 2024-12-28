#include <iostream>
#include <vector>
#include <queue>
using namespace std;

vector<int> bfsTraversal(int n, vector<vector<int>>& adj) {
    vector<int> result;    
    vector<bool> visited(n, false); 
    queue<int> q;        

    q.push(0);
    visited[0] = true;

    while (!q.empty()) {
        int current = q.front();
        q.pop();
        result.push_back(current);

        for (int neighbor : adj[current]) {
            if (!visited[neighbor]) {
                visited[neighbor] = true;
                q.push(neighbor);
            }
        }
    }

    return result;
}

int main() {
    vector<vector<int>> adj1 = {{2, 3, 1}, {0}, {0, 4}, {0}, {2}};
    vector<int> result1 = bfsTraversal(adj1.size(), adj1);
    cout << "BFS Traversal: ";
    for (int v : result1) cout << v << " ";
    cout << endl;

    vector<vector<int>> adj2 = {{1, 2}, {0, 2}, {0, 1, 3, 4}, {2}, {2}};
    vector<int> result2 = bfsTraversal(adj2.size(), adj2);
    cout << "BFS Traversal: ";
    for (int v : result2) cout << v << " ";
    cout << endl;
    vector<vector<int>> adj3 = {{1}, {0, 2, 3}, {1}, {1, 4}, {3}};
    vector<int> result3 = bfsTraversal(adj3.size(), adj3);
    cout << "BFS Traversal: ";
    for (int v : result3) cout << v << " ";
    cout << endl;

    return 0;
}

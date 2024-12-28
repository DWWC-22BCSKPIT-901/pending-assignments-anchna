#include <iostream>
#include <vector>
#include <queue>
#include <unordered_map>
#include <unordered_set>
using namespace std;

bool validPath(int n, vector<vector<int>>& edges, int source, int destination) {
    if (source == destination) return true;

    unordered_map<int, vector<int>> graph;
    for (const auto& edge : edges) {
        graph[edge[0]].push_back(edge[1]);
        graph[edge[1]].push_back(edge[0]);
    }

    queue<int> q;
    unordered_set<int> visited;

    q.push(source);
    visited.insert(source);

    while (!q.empty()) {
        int current = q.front();
        q.pop();

        for (int neighbor : graph[current]) {
            if (neighbor == destination) return true; 
            if (!visited.count(neighbor)) {
                visited.insert(neighbor);
                q.push(neighbor);
            }
        }
    }

    return false; 
}

int main() {
    int n1 = 3;
    vector<vector<int>> edges1 = {{0, 1}, {1, 2}, {2, 0}};
    int source1 = 0, destination1 = 2;
    cout << "Example 1 Output: " << (validPath(n1, edges1, source1, destination1) ? "true" : "false") << endl;

    int n2 = 6;
    vector<vector<int>> edges2 = {{0, 1}, {0, 2}, {3, 5}, {5, 4}, {4, 3}};
    int source2 = 0, destination2 = 5;
    cout << "Example 2 Output: " << (validPath(n2, edges2, source2, destination2) ? "true" : "false") << endl;

    return 0;
}
